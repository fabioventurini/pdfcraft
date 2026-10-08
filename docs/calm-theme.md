# Calm (Low Stimulation) theme

A third display theme, next to Light gray and Dark gray: the theme button in the tab strip, or
`view.theme.calm`. It persists like the other two, as a `ThemePreference`.

## Why it exists

Light gray and Dark gray are one design at two lightnesses: neutral greys, a saturated blue
accent, 6 px corners. Calm is a different tuning for sustained reading by people for whom that
signal is a cost — ADHD and autistic users in particular.

## What it changes

| | Dark gray | Calm |
|---|---|---|
| Chrome / panels | neutral `#26262a` | warm `#242422` |
| Pasteboard | `#19191c` | warm `#1a1a19` |
| Accent | saturated blue `#4b8bf5` | one soft blue `#85b7eb` |
| Page shadow | 120 alpha | 90 alpha |
| Corners | 6 px | 8 px |
| **The page** | white | **white — unchanged** |

The page stays white on purpose. This is a reading app; the document is content, not chrome, and
tinting it would change what the user is looking at rather than what surrounds it.

Unlike Light and Dark, Calm is never selected by `ThemePreference::System` — it is an explicit
choice, so the OS switching to dark mode cannot take it away or impose it.

## Where the values come from

The surface, text and accent tokens are the dark half of the INT Digital design system
(warm-neutral greys with a faint warm bias, one semantic accent, a dark theme designed in its own
right rather than inverted from the light one), and its rule that colour is never the sole
carrier of meaning.

## Adding to it

`Tokens::for_kind(ThemeKind::Calm)` in `crates/ui-egui/src/theme.rs` holds every value. Widgets
read `Tokens::get`, so nothing else needs touching.
