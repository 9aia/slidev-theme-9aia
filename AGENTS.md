# slidev-theme-9aia — agent/dev map

The 9aia design language as a Slidev theme — VitePress-styled
decks (dark scheme, Inter/JetBrains Mono). Self-linked into its
own devDependencies (`link:.`) so `slidev example.md` resolves it.

## Layout

| Path | Role |
| --- | --- |
| `layouts/` | Slidev layouts — `cover`, `intro`, `section`, `statement`, `fact`, `quote`, `end` |
| `components/` | Vue components (`Badge.vue`) |
| `styles/` | `vars.css` tokens, `base.css`, `layouts.css`, `index.ts` aggregator |
| `global-top.vue` / `global-bottom.vue` | chrome injected on every slide |
| `layoutHelper.ts` | layout selection helpers |
| `example.md` | dev fixture deck — the `dev`/`export` target, not docs |

## Commands

```bash
pnpm install
pnpm run dev      # slidev example.md --open
pnpm run export   # slidev export example.md (PDF/PPTX/PNG)
```

## Rules

- English everywhere; conventional commits.
- `example.md` is the dev fixture, not a docs worktree —
  `cypera.toml` exempts the docs-site contract rules.

## Boundary

This repo owns the Slidev theme only. Sibling
`vitepress-theme-9aia` is the VitePress counterpart; the theme is
consumed by presentation decks across the org.
