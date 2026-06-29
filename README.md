# bg-game-translation-qa

Codex Skill for Bulgarian game localization QA.

Use this skill when translating, reviewing, editing, or QA-checking Bulgarian game localization files for game mods and similar projects. It focuses on preserving file structure, keys, IDs, placeholders, tags, line breaks, and project terminology while improving Bulgarian translation quality.

## What It Covers

- Unity text dumps and localization exports
- Unreal localization exports and locres-derived text
- JSON, CSV, TSV, INI, XML, and PO files
- Game mod translation tables and text dumps
- Placeholder, tag, glossary, and style QA

## Skill Behavior

The skill instructs Codex to:

- preserve all structure, keys, IDs, placeholders, formatting tags, and line breaks
- translate only user-facing text
- avoid changing internal identifiers, enum names, filenames, paths, class names, function names, and technical metadata
- prefer natural Bulgarian over literal English word order
- follow project glossaries when available
- report uncertain strings separately instead of silently guessing
- make minimal, safe, patch-style changes

## Relationship to `bg-text`

This skill can be used together with [`bg-text`](https://github.com/AcTePuKc/bg-text), but it should not depend on it. Use `bg-text` as a companion for Bulgarian typography, grammar, punctuation, and general editorial quality. The game localization rules in this skill take priority whenever file structure, placeholders, tags, keys, IDs, or project terminology could be affected.

## Files

```text
.
├── SKILL.md
├── .agents/
│   └── skills/bg-game-translation-qa/SKILL.md
├── .claude/
│   └── skills/bg-game-translation-qa/SKILL.md
├── .cursor/
│   └── skills/bg-game-translation-qa/SKILL.md
├── .gemini/
│   └── skills/bg-game-translation-qa/SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── bg-text.md
    ├── glossary-template.md
    ├── placeholders.md
    └── qa-checklist.md
```

The root `SKILL.md` is the canonical Codex skill. The `.agents`, `.claude`, `.cursor`, and `.gemini` files are lightweight repo-scoped adapters for tools that scan those folders.

## Installation

Copy this folder to your Codex skills directory:

```powershell
Copy-Item -Path "." -Destination "$env:USERPROFILE\.codex\skills\bg-game-translation-qa" -Recurse
```

If the destination already exists, remove or replace it intentionally.

## Using Outside Codex

The canonical skill is written for Codex, but this repository also includes lightweight adapter entrypoints for agents that scan `.agents`, `.claude`, `.cursor`, or `.gemini` folders.

For tools without skill support, copy the relevant instructions from `SKILL.md` together with the checklist and placeholder rules from `references/`.

Recommended prompt pattern:

```text
Use the rules from SKILL.md to review this Bulgarian game localization file.
Preserve all keys, IDs, placeholders, tags, line breaks, formatting, and file structure.
Translate or edit only user-facing text.
List uncertain strings separately.
```

## Validation and Sanity Checks

For Codex, run the skill validator against the installed skill:

```powershell
python "$env:USERPROFILE\.codex\skills\.system\skill-creator\scripts\quick_validate.py" "$env:USERPROFILE\.codex\skills\bg-game-translation-qa"
```

For non-Codex adapters, there is no shared validator in this repository. Before publishing, check that:

- the root `SKILL.md` remains the canonical source of truth
- `.agents`, `.claude`, `.cursor`, and `.gemini` adapter files are intentionally identical
- adapter paths to `../../../references/` still resolve from each adapter folder
- no adapter weakens the structure, key, placeholder, tag, or minimal-edit safety rules

## License

MIT
