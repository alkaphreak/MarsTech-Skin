# Changelog

All notable changes to this project are documented here.
Format: [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [Unreleased]

### Added

- `DESIGN.md` §9: three content anti-patterns (invented content, fake success state, plain `1fr` grid
  tracks), taken from the Hallmark evaluation (MARSTECH-942)

### Changed

- `DESIGN.md`: "Bootstrap consumers" becomes "Leaving Bootstrap": sol4.space no longer loads Bootstrap and
  re-implements the class names its markup still uses on the tokens; `marstech.css` tools-menu comment
  no longer points at Bootstrap's collapse (MLS-271)

### Fixed

- `marstech.css`: long headings overflowed narrow screens and stray wide content scrolled the page sideways;
  `h1`-`h3` now wrap (`overflow-wrap: break-word`) and `html`, `body` set `overflow-x: clip`; `.panel`
  sets `color: var(--fg)` explicitly (MARSTECH-942)
- `marstech.css`: `:focus-visible` and `.input:focus` set `outline: none`, so the box-shadow focus ring vanished
  in forced-colors mode; they now keep a transparent 2px outline that the mode paints (MLS-271)
- `fonts.css`: the header comment closed early on `fonts/*/OFL.txt`, so browsers dropped the Oxanium 500
  `@font-face` rule (MARSTECH-897)
- `marstech.css`: a focused `.mt-clip` element lost its focus ring to the clip-path; the clip is now
  dropped on `:focus-visible` (MARSTECH-897)

### Added

- `tokens.css`: the 56 Open Design schema tokens for the "Glacier néon" direction (MARSTECH-851)
- `marstech.css`: link color, clipped corners and mono labels
- `DESIGN.md`: color roles, typography, components and anti-patterns
- `docs/preview/specimen.html` and its render `docs/images/overview.png`, shown in the README
- `fonts.css` and `fonts/`: self-hosted woff2 for Oxanium (500-700), IBM Plex Sans and JetBrains Mono
  (400-600), latin subset from Fontsource 5.3.0, each with its OFL license (MLS-250)
- `marstech.css`: `.mt-menu` tools menu (one row from 992px, vertical list behind the `.mt-menu-toggle`
  burger below) and leading icons in buttons; `DESIGN.md` documents both and the Bootstrap bridge
  used by sol4.space (MLS-250)
