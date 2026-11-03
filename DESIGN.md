# Design System: MarsTech-Skin (Glacier néon)

> Category: Themed & Unique
> Retro-futurist neon noir for the MarsTech projects: ice blue and silver on blue-black, a touch of neon pink,
> clipped corners, no glow. Chosen in MARSTECH-851 (proposal H5) on 2026-11-03.

Applies to sol4.space (marstech-link-spray, MLS), MarsTech-CV-Website and the Taskwarrior-Connector
Firefox popup. `tokens.css` is the source of truth for values; this file states the rules. Brand
extensions outside the Open Design schema are in `marstech.css`.

## 1. Visual Theme & Atmosphere

- Neon noir and HUD interfaces: Ghost in the Shell, Blade Runner, the wireframe screens of the
  Alien films. The aesthetic, not the Cyberpunk 2077 video game.
- Sober layout in the zed.dev spirit (MLS-248): lots of black, thin lines, one accent.
- Dark only. No light theme.

## 2. Color

| Role          | Token            | Value     | Use                                         |
|---------------|------------------|-----------|---------------------------------------------|
| Background    | `--bg`           | `#05070a` | page                                        |
| Surface       | `--surface`      | `#0a0e13` | cards, panels, popup body                   |
| Surface 2     | `--surface-warm` | `#0f141b` | code blocks, input wells                    |
| Text          | `--fg`           | `#c9d1d9` | body text (13.1:1 on bg)                    |
| Text 2        | `--fg-2`         | `#a9b4c0` | secondary text                              |
| Muted         | `--muted`        | `#8692a0` | captions, labels (6.1:1 on surface)         |
| Meta          | `--meta`         | `#76828f` | timestamps, ids (4.7:1 minimum)             |
| Border        | `--border`       | `#233140` | hairlines, card edges                       |
| Accent        | `--accent`       | `#7cc7ff` | primary button, active nav item, brand dot  |
| On accent     | `--accent-on`    | `#021220` | text on accent (10.3:1)                     |
| Link          | `--mt-link`      | `#ff6aa8` | links only (7.6:1 on bg)                    |
| Success       | `--success`      | `#5fd4a0` | status only                                 |
| Warning       | `--warn`         | `#ffcf4a` | due dates, alerts                           |
| Danger        | `--danger`       | `#ff6b6b` | errors, destructive actions                 |

- At most two visible uses of `--accent` per screen.
- Pink is for links and nothing else, so a pink word always means "clickable".
- Status colors never decorate: they carry a state.
- Banned: amber and green phosphor as brand colors, light backgrounds, purple-to-blue gradients.

## 3. Typography

- Display: **Oxanium** (headings, brand name, nav), letter-spacing `--tracking-display`, often uppercase.
- Body: **IBM Plex Sans**.
- Mono: **JetBrains Mono** (code, ids, URLs, labels).
- Fonts are served locally (woff2) in every project: no Google Fonts call at runtime.
- Scale: `--text-xs` 12 to `--text-4xl` 52. Body at `--text-base` 15, line-height 1.55.
- Banned: glitch text on content, VT323 or other pixel fonts for running text, Rajdhani (too close to 2077).

## 4. Spacing & Grid

- 4px base (`--space-1` to `--space-12`).
- Container `--container-max` 1120px, gutter 16px on phone.
- Touch targets at least 44px high.

## 5. Layout & Composition

- One column on phone (390px wide must work), up to two on desktop.
- Header: brand at left (`sol4.space` with the dot in `--accent`), mono nav at right.
- Each block may carry a mono uppercase label (`.mt-label`) above its content.

## 6. Components

Classes live in `marstech.css`; `prototypes/` shows them on the three products (validated 2026-11-03).
Clipped corners (`.mt-clip`) cut the top-left and bottom-right corners.

- **Header**: `.mt-header`, `.mt-brand` (dot in `--accent`), `.mt-nav` (current item in `--accent`).
- **Buttons**: `.btn` + `.btn-primary` (`--accent` fill, `.mt-clip`), `.btn-secondary`, `.btn-danger`,
  `.btn-ghost`; mono uppercase 12px, 44px high.
  Secondary: transparent, 1px `--border`, `--fg` text.
- **Inputs**: `.field-label`, `.input` (`--bg` fill, 1px `--border`, mono text, `--focus-ring` on focus,
  `--danger` border when `aria-invalid`), `.field-help`, `.field-error`.
- **Cards / panels**: `--surface`, 1px `--border`, `.mt-clip` corners, padding `--space-3` to `--space-4`.
- **Badges / tags**: mono 11px, 1px border, square corners; due date in `--warn`.
- **Code / terminal**: `--surface-warm`, mono 12.5px, prompt in `--accent`, comments in `--muted`.
- **Lists** (popup tasks): rows separated by 1px `--border`, square status dot in `--accent`.

## 7. Motion & Interaction

- Fast and quiet: `--motion-fast` 120ms for hover, `--motion-base` 200ms for state changes.
- No glow, no scanlines, no flicker. Honour `prefers-reduced-motion`.

## 8. Voice & Brand

- Short, technical, factual labels ("Raccourcir un lien", "200 OK").
- French UI text on French-facing pages; code and ids stay as they are.

## 9. Anti-patterns

- Neon on every element: the accent loses meaning past two uses per screen.
- Glow or blur shadows on text.
- Rounded corners mixed with clipped corners.
- Low-contrast grey on grey: every text pair must stay at 4.5:1 or more.
