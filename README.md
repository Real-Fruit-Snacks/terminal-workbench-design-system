# Terminal Workbench — Style

A portable design system: calm graphite surfaces, restrained ANSI-style accents, monospace "manifest" labels, and mandatory dark + light modes. Distilled from the [Terminal Workbench Obsidian theme](https://github.com/Real-Fruit-Snacks/terminal-workbench) into a form any project can consume.

**Live demo:** https://real-fruit-snacks.github.io/style/

## What's here

| File | Purpose |
|---|---|
| [THEME-SPEC.md](THEME-SPEC.md) | The source of truth — philosophy, token tables (both modes), typography, shape, motion, and component patterns. Platform-agnostic; hand it to any tool, framework, or AI to reproduce the theme anywhere. |
| [tokens.css](tokens.css) | Drop-in CSS custom properties implementing the spec. Dark by default, light via `prefers-color-scheme` or `data-theme`. |
| [index.html](index.html) | The demo page — a living reference of every token and component, built on `tokens.css`. |

## Use it in a web project

Link the tokens:

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/Real-Fruit-Snacks/style@main/tokens.css">
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

## Use it anywhere else

For terminals, editors, dashboards, slide decks — anything that isn't CSS — give [THEME-SPEC.md](THEME-SPEC.md) to the tool or AI doing the work. Section 7 of the spec explains exactly which parts to hand over. The result should pass the spec's checklist: both modes, adequate contrast, quiet chrome, color spent only on signal.
