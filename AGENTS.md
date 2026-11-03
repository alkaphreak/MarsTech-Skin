# AGENTS.md — MarsTech-Skin

> AI agent instructions for MarsTech-Skin, the MarsTech design system. Maintainer: Alkaphreak (Stephane Robin).
> Based on the Marstech-Configs AGENTS.md standard (MARSTECH-643).

---

## Stack

- Plain CSS custom properties and Markdown. No build, no package, no JavaScript runtime.
- Format: Open Design design system (`DESIGN.md` + `tokens.css`, schema `TOKEN_SCHEMA`, 56 tokens).

---

## Codebase Map

```
MarsTech-Skin/
├── tokens.css      # Source of truth for values, exactly the Open Design schema tokens
├── marstech.css    # Brand extensions outside the schema (--mt-*), .mt-clip, .mt-label
├── DESIGN.md       # Rules: color roles, typography, components, anti-patterns
└── docs/adr/       # Design decisions (MADR)
```

**Consumers**: marstech-link-spray (sol4.space, MLS-250), MarsTech-CV-Website, Taskwarrior-Connector
popup (MARSTECH-729). A token rename breaks them: list it in `CHANGELOG.md`.

**Architecture decisions**: `docs/adr/` (MADR, copy `0000-template.md`). Read the ADRs before changing
the direction; record a new decision there, not only in the ticket.

---

## Rules

- `tokens.css` holds the schema tokens only, no others. Anything else goes in `marstech.css` with the
  `--mt-` prefix (Open Design rejects unknown tokens outside its brand extensions).
- Every text/background pair stays at 4.5:1 or more (WCAG AA). Check it with a script, not by eye,
  and give the ratio in the commit or PR.
- At most two visible uses of `--accent` per screen; pink (`--mt-link`) is for links only.
- Dark only, no glow, no scanlines, no rounded corners mixed with clipped ones (see `DESIGN.md` §9).
- Fonts are OFL: when woff2 files are added, ship each font's license file next to it.

---

## AI Exclusions

Respect `.aiignore`. Never auto-scan `private/`, `archive/`, `.local/`.

---

## Terminal Commands

- Always use **absolute paths**; shell is zsh on macOS
- Prefix CLI commands with `rtk` (token proxy)

---

## External Integrations

- **YouTrack**: `https://marstech.myjetbrains.com/youtrack`, project MARSTECH, auth via `$YOUTRACK_TOKEN`
- **Open Design**: desktop app on the MacBook Pro; import this folder as a local design system

---

## Related Tickets

- [MARSTECH-851](https://marstech.myjetbrains.com/youtrack/issue/MARSTECH-851) — creation of this design system
- [MARSTECH-636](https://marstech.myjetbrains.com/youtrack/issue/MARSTECH-636) — Open Design evaluation
- [MLS-250](https://marstech.myjetbrains.com/youtrack/issue/MLS-250) — sol4.space redesign, first consumer
- [MLS-248](https://marstech.myjetbrains.com/youtrack/issue/MLS-248) — zed.dev-inspired layout direction

---

_Last updated: 2026-11-03 by Claude Code — repository creation (MARSTECH-851)_
