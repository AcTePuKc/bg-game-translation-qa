---
name: bg-game-translation-qa
description: Use when translating, reviewing, editing, or QA-checking Bulgarian game localization files while preserving structure, keys, IDs, placeholders, tags, and project terminology.
---

# bg-game-translation-qa — repo adapter skill

This repository keeps the canonical maintained skill at the root `SKILL.md`.

Use this repo-scoped adapter when an agent discovers skills from standard project folders such as `.agents/skills/`, `.claude/skills/`, `.cursor/skills/`, or `.gemini/skills/`.

Apply these defaults unless the user explicitly asks for a different workflow:

- Preserve all file structure, keys, IDs, row shape, ordering, delimiters, escaping, and metadata.
- Preserve placeholders, variables, formatting tags, escape sequences, and line breaks exactly.
- Translate or edit only user-facing text.
- Do not change internal identifiers, enum names, filenames, paths, class names, function names, object names, or technical metadata.
- Prefer natural Bulgarian over literal English word order while keeping project terminology consistent.
- Flag uncertain strings, possible translation ballast, and formal/informal address mismatches for manual review.
- Make minimal, focused, patch-style changes instead of rewriting whole files.

Load the maintained reference material from `../../../references/` as needed:

- `bg-text.md` for Bulgarian game localization style guidance
- `placeholders.md` for protected placeholder and tag patterns
- `qa-checklist.md` for final review
- `glossary-template.md` for project terminology tables

If both this adapter and the root `SKILL.md` are visible, prefer the root canonical file as the fuller maintained version.
