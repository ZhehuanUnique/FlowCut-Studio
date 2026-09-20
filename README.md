# FlowCut Studio

**Modular AI editing skills for cinematic intros, reverb-and-echo outros, and reusable video workflows.**

Version **0.1.0** · Two editing techniques, one orchestration skill, and an extension registry.

## Included skills

| ID | Name | Invocation | Purpose |
| --- | --- | --- | --- |
| Orchestrator | FlowCut Studio | `$flowcut-editing` | Select and compose registered techniques |
| FC-IN-001 | Iris Spin Intro | `$flowcut-intro-iris-spin` | A layered iris, spin, glare, and reveal opening |
| FC-OUT-001 | Reverb Echo Outro | `$flowcut-outro-reverb-echo` | A controlled audio tail using reverb followed by delay |

Each technique works independently. The orchestrator loads only the selected skills, preserves existing edits, and resolves timing conflicts before combining them. The existing FlowCut speech-editing skill is not overwritten or bundled here.

## Example requests

- “Use Iris Spin Intro on this clip. Leave the original file untouched.”
- “Use Reverb Echo Outro after a complete sentence, with a natural decay.”
- “Use FlowCut Studio to combine FC-IN-001 and FC-OUT-001 in a 15-second edit.”
- “Add this new transition to FlowCut Studio with its own name and stable ID.”

## Structure

```text
skills/
├── flowcut-editing/              Orchestrator, registry, extension guide
├── flowcut-intro-iris-spin/       Intro workflow and tested parameters
└── flowcut-outro-reverb-echo/     Outro workflow, audio routing, verification
```

The package name and display names are English. Detailed operating instructions are currently in Chinese, including the exact Chinese effect names shown in Jianying. Skill directory names and stable IDs do not change when a display name changes.

## Using the pack

Place the three folders inside `skills/` side by side in the skill directory supported by your assistant, following that tool's installation instructions. Automatic discovery, `$` invocation, and editor control depend on the host. In an environment without native skill support, the Markdown recipes remain readable instructions; they do not grant editing capabilities.

During creation, a separate local copy of these three skills was saved to the creator's assistant skill directory. Downloading this archive does not automatically install it on another computer.

This is a pack of instructions and recipes, **not a Jianying preset, editor plugin, or one-click rendering program**. Native reproduction requires an available editor connection and the named effects. Tested baseline: **Jianying Pro for Windows 11.5.0.14471**. Other editors may implement similar techniques, but matching names, controls, or appearance are not guaranteed.

The workflows use independent drafts and new output filenames. Original media and previous exports remain untouched. Publishing, purchasing effects, uploading private media, and syncing repositories are separate actions, not part of running these skills.

## Extending FlowCut Studio

Add a standalone skill folder, register its name, ID, and entry point in `skills/flowcut-editing/references/catalog.json`, and follow the [extension guide](skills/flowcut-editing/references/extension-guide.md). Existing techniques need not be rewritten. Test the new module independently and in combination before marking it verified.

The pack contains no source footage, tutorial recordings, private filesystem paths, account data, or caches. It documents observed techniques and tested adaptations; it does not redistribute the reference creator's media or Jianying effects. A license has not been selected for this release.

The layout uses independent skill directories with `SKILL.md` entry points. Skills can consist of instructions and resources without an MCP server; see the [official skill documentation](https://developers.openai.com/plugins/build/skills).
