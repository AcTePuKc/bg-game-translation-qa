# Bulgarian Game Localization Style

Use this reference for practical Bulgarian game localization choices. It is a starter guide, not a full grammar manual.

## General Style

- Prefer natural Bulgarian sentence flow over English word order.
- Keep UI labels short, clear, and action-oriented.
- Preserve the tone of the source: casual, dramatic, technical, archaic, comic, or military.
- Do not over-formalize dialogue unless the character or setting requires it.
- Avoid unnecessary transliteration when a clear Bulgarian equivalent exists.
- Keep established project terms consistent, even when another translation is also acceptable.

## Capitalization and Punctuation

- Avoid copying English Title Case into Bulgarian unless the project glossary requires it.
- Use normal Bulgarian capitalization for menu labels, quest names, item descriptions, and dialogue.
- Preserve intentional punctuation used for UI state, warnings, or character voice.
- Keep ellipses, dashes, and repeated punctuation only when they carry tone or timing.

## Gender and Address

- When player gender is unknown, prefer neutral constructions where possible.
- Avoid adding gendered adjectives or participles unless the string has gender context.
- Match formality to the game world and speaker relationship.
- Keep consistent address style within the same character, faction, or UI system.

## Game-Specific Translation

- Translate mechanics clearly before making them literary.
- For buttons and commands, prefer concise verbs or noun phrases.
- For tooltips, preserve cause, condition, value, and result.
- For quests and dialogue, preserve character voice and implied intent.
- Do not invent lore, faction names, item properties, or mechanics not present in the source.

## Common Risks

- Literal English syntax that sounds unnatural in Bulgarian.
- Translation ballast: literal fragments that are technically correct but unnecessary in Bulgarian UI text, such as redundant `through the air`, `into pieces`, `apart`, `nearby`, `on the ground`, or `in front of you`. Flag for manual review, not automatic removal.
- Russian or Ukrainian lexical leftovers in Bulgarian text.
- Overlong UI strings that will not fit buttons, tabs, or compact HUD elements.
- Inconsistent translations of repeated mechanics such as save, load, skill, perk, quest, damage, armor, health, stamina, mana, cooldown, and crafting.
