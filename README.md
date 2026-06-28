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

This skill can be used together with `bg-text`, but it should not depend on it. Use `bg-text` as a companion for Bulgarian typography, grammar, punctuation, and general editorial quality. The game localization rules in this skill take priority whenever file structure, placeholders, tags, keys, IDs, or project terminology could be affected.

## Files

```text
.
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── bg-text.md
    ├── glossary-template.md
    ├── placeholders.md
    └── qa-checklist.md
```

## Installation

Copy this folder to your Codex skills directory:

```powershell
Copy-Item -Path "." -Destination "$env:USERPROFILE\.codex\skills\bg-game-translation-qa" -Recurse
```

If the destination already exists, remove or replace it intentionally.

## Using Outside Codex

The skill format is Codex-specific, but the guidance is reusable. For other AI tools, copy the relevant instructions from `SKILL.md` together with the checklist and placeholder rules from `references/`.

Recommended prompt pattern:

```text
Use the rules from SKILL.md to review this Bulgarian game localization file.
Preserve all keys, IDs, placeholders, tags, line breaks, formatting, and file structure.
Translate or edit only user-facing text.
List uncertain strings separately.
```

## Validation

Run the Codex skill validator:

```powershell
python "$env:USERPROFILE\.codex\skills\.system\skill-creator\scripts\quick_validate.py" "$env:USERPROFILE\.codex\skills\bg-game-translation-qa"
```
