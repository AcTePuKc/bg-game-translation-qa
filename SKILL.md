---
name: bg-game-translation-qa
description: Use this skill when translating, reviewing, editing, or QA-checking Bulgarian game localization files, including game mod translation tables, Unity text dumps, Unreal localization exports, JSON, CSV, TSV, INI, XML, PO, and locres-derived files.
---

# Bulgarian Game Localization QA

Use this skill for Bulgarian game localization work where preserving the file format is as important as improving the text. Make minimal, safe changes and prefer focused patches over rewriting whole files unless the user explicitly asks for a full rewrite.

## Core Workflow

1. Identify the file format and the translatable fields before editing.
2. Preserve all structure, ordering, delimiters, quoting, escaping, comments, keys, IDs, and metadata.
3. Translate or edit only user-facing text.
4. Preserve placeholders, formatting tags, variables, escape sequences, and line breaks exactly unless the user explicitly asks to change them.
5. Follow any project glossary, termbase, style guide, or existing translation memory provided by the user or present in the project.
6. Report uncertain strings separately instead of silently guessing.
7. Summarize what changed, what was left unchanged, and any risks or questions.

## Non-Translatable Content

Do not translate or normalize internal identifiers, enum names, filenames, file paths, class names, function names, object names, asset names, event names, console commands, config keys, IDs, or technical metadata unless the user explicitly marks them as player-facing text.

For structured files, keep row counts, key order, nesting, separators, and encoding intact. For CSV/TSV tables, preserve the exact column structure. For JSON/XML/INI/PO-style files, preserve syntax and escaping.

## Placeholders and Tags

Preserve placeholders and formatting tags byte-for-byte, including case, punctuation, nesting, spacing, and order. Do not translate text inside variables unless it is clearly player-facing display text.

Always protect patterns such as:

- `{PLAYER}`
- `{0}`
- `%s`
- `%d`
- `<color=...>`
- `</color>`
- `<b>`
- `</b>`
- `\n`
- `\t`
- `[br]`
- `[[...]]`
- `$VARIABLE`
- `${variable}`

Read `references/placeholders.md` when the task includes unfamiliar tokens, rich text, UI markup, scripting syntax, or format-specific placeholders.

## Bulgarian Localization Style

Use natural Bulgarian phrasing, not literal English word order. Keep UI text concise and readable, especially for buttons, menus, achievements, tooltips, and combat messages.

Prefer culturally appropriate Bulgarian translation over transliteration when possible, but keep established game terms and project glossary choices consistent. Preserve character voice in dialogue and avoid over-formalizing casual or humorous speech.

When speaker or player gender is unknown, avoid forced gendered phrasing where Bulgarian allows a neutral construction. Do not introduce Russian- or Ukrainian-sounding phrasing. Avoid unnecessary capitalization copied from English headings, item names, or UI labels unless the project style requires it.

Read `references/bg-text.md` for practical Bulgarian style guidance and `references/glossary-template.md` when creating or extending a project glossary.

## Relationship to bg-text

When the `bg-text` skill is available or the user asks to use it, use it as a companion reference for Bulgarian typography, clarity, punctuation, grammar, and general editorial quality. Apply this skill's game localization constraints first: never let typography or style cleanup alter protected structure, keys, IDs, placeholders, tags, escape sequences, line breaks, or project terminology.

For game files, treat `bg-text` as language-quality guidance, not permission to rewrite whole files or normalize engine-specific syntax.

## QA Checklist

Before final output, check for:

- broken, changed, reordered, or missing placeholders
- missing, malformed, or unbalanced formatting tags
- changed keys, IDs, filenames, paths, or metadata
- missing rows or changed table shape
- duplicate IDs introduced or missed
- untranslated English in translated fields
- Ukrainian leftovers
- Russian leftovers
- inconsistent glossary terms
- overly literal Bulgarian
- UI text that is obviously too long for its likely control

Read `references/qa-checklist.md` for a practical final review pass.

## Output Expectations

Prefer patch-style changes and focused corrections. Explain meaningful translation or QA changes briefly. List uncertain strings separately with the key/ID or location, the issue, and the safest suggested handling.

If the file is large, inspect enough surrounding context to avoid terminology drift, then edit only the requested scope. If a requested change would risk damaging structure or placeholders, stop and ask for clarification.
