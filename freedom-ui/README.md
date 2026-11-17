# Freedom UI reference pack

What you need to rebuild the look of **Freedom**, a personal OS that runs in the browser: screenshots of every
main surface, the design tokens, the liquid-glass CSS, app icons and the hub and app structure.

**About the screenshots.** They were captured from a local build at 2x with Playwright. Every data call was stubbed
with **made-up sample data**, names are swapped for placeholders, and most apps show their empty states. Use them for
layout, type, colour and glass, not content.

## What's here

| Folder | What |
|---|---|
| [screenshots/](screenshots/) | PNGs at 2x. Phone is 390x844, desktop 1440x900. |
| [tokens/shell.css](tokens/shell.css) | The shell's tokens (dark by default, `data-look="light"` for light), sizes and the liquid-glass recipe. Start here. |
| [tokens/classic.css](tokens/classic.css) | The classic pages' tokens: deep blue light and dark, plus four palettes (Forest, Plum, Burgundy, Ember). |
| [tokens/tokens.json](tokens/tokens.json) | The same classic tokens as JSON. |
| [icons/apps/](icons/apps/) | App and hub tiles as SVG: a white Phosphor fill glyph on a 135° two-stop gradient, 64px grid, radius 14. |
| [icons/logos/](icons/logos/) | The Freedom key logo (SVG, 512 PNG, maskable PNG). |
| [structure/](structure/) | A sample of the apps (`apps.json`), hubs and their tabs (`hubs.json`), and the two spaces (`modes.json`). |

## The system in one page

**Two front ends.**
1. **The shell (`/next/`)** is the front door. On a phone it's an iPhone-style home screen: a status bar, a widget
   grid, a Search pill, an AI button and a four-app dock. Swipe left of home for the A to Z page; app pages
   follow to the right. On a laptop (900px and wider) it's one page: a thin left rail (logo, home, dock apps,
   Everything, Search, bell, Settings, avatar), a big greeting under a small FREEDOM eyebrow, the space pill
   top right, and widget cards on a 12-column grid with no holes. Apps open in a window over the home screen.
2. **Classic pages (`/apps/`, `/myday/`, `/settings/`, `/new/`)** are generated HTML with a left nav on desktop and
   a bottom tab bar on phones. Each app is its own page at `/apps/<slug>/`.

**Spaces (modes).** Personal is white glass on a cool grey mesh (light look, accent `#C7CCD3`). Work is dark with
amber (`#F5B700`) on an amber-to-black mesh. Each space has its own apps, widgets, wallpaper and accent; the pill
switches between them. Personal's apps are grouped Health, Wealth, Retail, Wise, Family, Play and Everyday, A to Z
inside each.

**Hubs.** Related apps share one icon: a hub page with tabs across the top. See [hubs.json](structure/hubs.json).

**Widgets.** Small (4 of 12 columns on desktop), medium (8) and large. Every card has a coloured glyph and label top
left, optional meta top right, a big number or list in the middle and a muted footnote at the bottom. Empty states are
a calm sentence, never an error box.

**Type.** Geist 400 to 800 for everything, Geist Mono 500 for figures. The greeting is about 56px/800 with tight
tracking, widget numbers about 40px/700, body 15px/1.35.

**Icons.** Phosphor 2.1.1: regular for UI, fill inside app tiles, bold in the rail. Tiles get a gloss: a white
gradient over the top half, an inner highlight and a soft drop shadow (`.os-tile` in `tokens/shell.css`).

**Liquid glass.** Every container (widgets, dock, pill, sheets, menus, rail, desktop cards) is frosted glass over
the wallpaper:

```css
background: linear-gradient(160deg, var(--lg-sheen), transparent 42%), var(--tile);
border: 1px solid var(--lg-edge);
backdrop-filter: blur(24px) saturate(175%);
box-shadow: inset 0 1px 0 var(--lg-hi), 0 12px 30px -16px var(--lg-drop), 0 1px 2px rgba(0,0,0,.05);
```

Dark: `--tile: rgba(18,20,30,.42)`, edge `rgba(255,255,255,.16)`, top highlight `.24`, sheen `.1`. Light:
`--tile: rgba(255,255,255,.62)`, edge white `.85`, highlight `.95`, sheen `.55`, drop `rgba(40,52,80,.2)`. Widget
radius `clamp(20px, 6.2vw, 26px)`, dock radius 38px. Solid fills come back under `prefers-reduced-transparency`.

**Classic colours.** Light `--bg #f5f6f8`, `--surface #fdfdfe`, `--ink #14171d`, accent deep blue `#1e3a8a`. Dark
`--bg #0f1115`, `--surface #171a20`, `--ink #f0f2f5`, accent `#7fa2f5`. Good, warning and critical each have a tint.
The shell's system colours follow iOS: red `#ff453a`, blue `#0a84ff`, green `#30d158`, yellow `#ffd60a`.

## Screenshot index

- `01` to `11`: the shell. Personal light, Personal dark, Work, A to Z, Control Centre, Search, the AI chat, the
  space menu, edit mode, Settings and an app open (To-do). Each comes as `-phone` and `-desktop`.
- `20`, `21`, `23`, `25`, `26`: classic pages (Apps grid, My Day, Settings, What's new, Archive), light and dark.
- `30` onwards: a hub and everyday apps (`-phone-light`, `-phone-dark`, `-desktop`).
