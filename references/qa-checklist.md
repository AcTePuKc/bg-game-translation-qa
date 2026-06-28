# Bulgarian Game Localization QA Checklist

Use this checklist before returning edited or reviewed localization files.

## Structure and Data Integrity

- File syntax is valid for the format being edited.
- Keys, IDs, paths, filenames, object names, and metadata are unchanged.
- Row counts, column counts, separators, nesting, quoting, and escaping are preserved.
- No rows, entries, or message IDs were dropped.
- No duplicate IDs were introduced or overlooked when the task includes ID review.

## Placeholder and Tag Integrity

- All placeholders from the source remain present in the translated text.
- Placeholder spelling, case, punctuation, numbering, and order are preserved unless explicitly required otherwise.
- Rich text tags are present, balanced, and nested as before.
- Escape sequences such as `\n` and `\t` are preserved.
- UI markup such as `[br]`, `[[...]]`, `<color=...>`, and closing tags is intact.

## Bulgarian Quality

- The Bulgarian reads naturally and does not follow English word order mechanically.
- UI labels are concise and likely to fit their controls.
- Dialogue preserves character voice, register, humor, urgency, and emotional tone.
- Unknown player gender is handled without unnecessary forced gendering where possible.
- Capitalization follows Bulgarian norms unless project style says otherwise.
- Repeated mechanics, item types, factions, and menu labels match the glossary or existing project usage.

## Language Leftovers

- No untranslated English remains in translated fields unless intentionally preserved.
- No Ukrainian leftovers remain.
- No Russian leftovers remain.
- No mixed-language fragments were introduced.

## Final Report

- Summarize changed areas briefly.
- List uncertain strings separately with key/ID/location and reason.
- Mention any strings that may be too long for UI.
- Mention any glossary conflicts or missing glossary decisions.
