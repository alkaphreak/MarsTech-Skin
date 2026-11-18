# Changelog

All notable changes to this project are documented here.
Format: [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [Unreleased]

### Changed

- `DESIGN.md`: "Bootstrap consumers" becomes "Leaving Bootstrap": sol4.space no longer loads Bootstrap and
  re-implements the class names its markup still uses on the tokens; `marstech.css` tools-menu comment
  no longer points at Bootstrap's collapse (MLS-271)

### Fixed

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
