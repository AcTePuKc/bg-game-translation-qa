# Placeholder and Formatting Patterns

Preserve placeholders, variables, tags, escape sequences, and markup exactly. Treat them as protected syntax, not translatable text.

## Common Patterns

| Pattern | Examples | Rule |
|---|---|---|
| Braced variables | `{PLAYER}`, `{QuestName}`, `{0}` | Keep exact spelling, case, braces, and order. |
| Positional formatters | `{0}`, `{1:N0}`, `%1$s` | Do not renumber or reorder unless the format explicitly supports it and the user asks. |
| C-style formatters | `%s`, `%d`, `%0.2f` | Keep exact formatter text. |
| Dollar variables | `$VARIABLE`, `${variable}` | Keep exact variable syntax and case. |
| Rich text tags | `<b>`, `</b>`, `<color=red>`, `<color=#FF0000>` | Preserve tag names, attributes, nesting, and closing tags. |
| Escapes | `\n`, `\t`, `\"`, `\\` | Preserve escape spelling and count. |
| Inline breaks | `[br]`, `<br>`, `<br/>` | Preserve unless explicitly asked to reflow. |
| Double brackets | `[[ITEM_NAME]]`, `[[...]]` | Preserve bracketed token exactly. |
| Engine tokens | `{player_name}`, `%damage%`, `@Input.Jump` | Treat as protected unless project docs say otherwise. |

## Review Procedure

1. Compare source and target placeholders before editing.
2. After editing, compare them again.
3. Confirm every opening tag still has the expected closing tag.
4. Confirm line breaks and tabs are unchanged unless the user requested layout changes.
5. Flag unfamiliar syntax instead of guessing whether it is safe to translate.

## Unsafe Changes

- Translating variable names inside placeholders.
- Changing `%d` to `%s` or altering numeric precision.
- Reordering placeholders in formats that may be positional or engine-specific.
- Normalizing tag case or attributes.
- Replacing escaped `\n` with a real line break unless the format requires it.
