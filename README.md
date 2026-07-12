<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Real-Fruit-Snacks/terminal-workbench-design-system/main/docs/assets/cover-dark.svg" />
  <img alt="Terminal Workbench — portable design system" src="https://raw.githubusercontent.com/Real-Fruit-Snacks/terminal-workbench-design-system/main/docs/assets/cover-light.svg" width="820" />
</picture>

<br/>

A portable design system: calm graphite surfaces, restrained ANSI-style accents, monospace "manifest" labels, and mandatory dark + light modes.

<br/>

[![License: MIT](https://img.shields.io/badge/License-MIT-f0c674?style=flat-square)](LICENSE)
&nbsp;![Version](https://img.shields.io/badge/version-1.2.0-6bdcff?style=flat-square)
&nbsp;![Modes](https://img.shields.io/badge/modes-dark%20%2B%20light-63f2ab?style=flat-square)

[Live demo](https://real-fruit-snacks.github.io/terminal-workbench-design-system/) · [Theme spec](THEME-SPEC.md) · [Notepad++ themes](https://github.com/Real-Fruit-Snacks/terminal-workbench-notepad-plus-plus) · [Report an issue](https://github.com/Real-Fruit-Snacks/terminal-workbench-design-system/issues)

</div>

---

## Overview

Terminal Workbench is a working surface for people who live in panes, shells, logs, and code — not retro green-on-black novelty. The interface stays quiet; signal (links, prompts, active elements, syntax) carries the color. Distilled from the [Terminal Workbench Obsidian theme](https://github.com/Real-Fruit-Snacks/terminal-workbench) into a form any project can consume.

| File | Purpose |
|---|---|
| [THEME-SPEC.md](THEME-SPEC.md) | The source of truth — philosophy, token tables (both modes), typography, shape, motion, and component patterns. Platform-agnostic; hand it to any tool, framework, or AI to reproduce the theme anywhere. |
| [tokens.css](tokens.css) | Drop-in CSS custom properties implementing the spec. Dark by default, light via `prefers-color-scheme` or `data-theme`. |
| [fonts.css](fonts.css) | Optional `@font-face` loader for [Terminal Workbench Mono](https://github.com/Real-Fruit-Snacks/terminal-workbench-mono), the system's official monospace (served via jsDelivr from that repo). |
| [index.html](index.html) | The demo page — a living reference of every token and component, built on `tokens.css`. |

## Use it in a web project

Link the tokens:

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/Real-Fruit-Snacks/terminal-workbench-design-system@main/fonts.css">
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/Real-Fruit-Snacks/terminal-workbench-design-system@main/tokens.css">
```

Build on the variables:

```css
body {
  background: var(--twb-bg-0);
  color: var(--twb-text-normal);
  font: 15px/1.7 var(--twb-font-ui);
}
```

### Modes

Dark is the default. Light mode applies automatically from the system preference, or force either mode:

```html
<html data-theme="light">  <!-- or "dark" -->
```

### Changing the accent

Override `--twb-accent` (and `--twb-accent-alt` / `--twb-warm` if you like) — every derived tint (selection, focus ring, tags, highlights) re-derives automatically in browsers with `color-mix` support:

```css
:root { --twb-accent: #7aa2f7; }
```

## Official typeface

[Terminal Workbench Mono](https://github.com/Real-Fruit-Snacks/terminal-workbench-mono)
is the official `--twb-font-mono` face — a clean geometric monospace with a
slashed zero, coding ligatures and a full terminal pack, built for this
system. `fonts.css` loads it on the web; grab the TTFs from its
[releases](https://github.com/Real-Fruit-Snacks/terminal-workbench-mono/releases)
for terminals and editors.

## Use it anywhere else

For terminals, editors, dashboards, slide decks — anything that isn't CSS — give [THEME-SPEC.md](THEME-SPEC.md) to the tool or AI doing the work. Section 7 of the spec explains exactly which parts to hand over. The result should pass the spec's checklist: both modes, adequate contrast, quiet chrome, color spent only on signal.

## Host it yourself

Everything the site needs is in this repo — `index.html`, `tokens.css`, and `THEME-SPEC.md`. Serve the repo root from any static host:

- **GitHub Pages:** Settings → Pages → deploy from `main`, root folder.
- **GitLab Pages:** the included [.gitlab-ci.yml](.gitlab-ci.yml) publishes the site on every push to the default branch.
- **Anything else:** copy the files to any static web server; there is no build step.

## License

[MIT](LICENSE)
