# slidev-theme-9aia

[VitePress](https://vitepress.dev)-styled [Slidev](https://sli.dev) theme used across 9aia presentations — same palette, typography, and components as the documentation sites, so decks stay consistent with the docs.

- VitePress color palette (indigo brand, `#bd34fe → #41d1ff` hero gradient)
- Inter + JetBrains Mono
- Dark-first, with a complete light palette (`colorSchema: 'light'` to switch)
- Extra layouts: `cover`, `intro`, `section`, `quote`, `statement`, `fact`, `end`
- `<Badge>` component, matching the VitePress badge

## Install

Install straight from this repository — no npm publish needed:

```bash
# pnpm
pnpm add -D @slidev/cli github:9aia/slidev-theme-9aia

# npm
npm i -D @slidev/cli github:9aia/slidev-theme-9aia

# bun
bun add -d @slidev/cli github:9aia/slidev-theme-9aia
```

Pin a tag or commit for reproducibility:

```bash
pnpm add -D github:9aia/slidev-theme-9aia#v0.1.0
```

## Use

Set the theme in your `slides.md` frontmatter:

```md
---
theme: 9aia
---

# Your first slide
```

Then run:

```bash
pnpm slidev slides.md
```

## Layouts

All [built-in Slidev layouts](https://sli.dev/builtin/layouts) (`default`, `center`, `two-cols`, `image-*`, …) work and inherit the styling. The theme additionally provides:

| Layout | Use |
| ------ | --- |
| `cover` | Title slide with the VitePress hero gradient |
| `intro` | Centered intro, solid title |
| `section` | Section divider with a gradient accent bar |
| `quote` | Large quote with a brand left border |
| `statement` | Centered statement |
| `fact` | Centered big figure |
| `end` | Closing slide with gradient title |

`cover` and `intro` accept a `background` frontmatter field (image URL or CSS color).

## Components

`<Badge>` renders a VitePress-style badge:

```md
<Badge type="tip">stable</Badge>
<Badge type="warning">beta</Badge>
<Badge type="danger">deprecated</Badge>
<Badge type="info">v1.2</Badge>
```

## Customize

All VitePress variables are exposed and can be overridden from your deck's `style.css` or a `styles/` entry:

```css
:root {
  --vp-c-brand-1: #3451b2;
}

.dark {
  --vp-c-bg: #1b1b1f;
}
```

`--slidev-theme-primary` is mapped to `--vp-c-brand-1`.

## Develop

```bash
pnpm install
pnpm dev        # previews example.md
pnpm export     # exports example.md to PDF
```

## License

[MIT](./LICENSE)
