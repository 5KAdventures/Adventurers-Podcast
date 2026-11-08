# podcast.5kadventures.net

Public page. No Cloudflare Access — this one is meant to be found.

```bash
npx wrangler deploy
```

Unlike the tool folders there is no `deploy.sh` and no dated builds:
`public/index.html` IS the page, edit it directly.

## Editing

- The intro sentence is wrapped in a big comment block marked
  "YOUR WORDS GO HERE". Keep it to about two lines.
- The **Adventurers Log** button is `href="#"` with a TODO above it.
  Replace it with the real URL once the Log is deployed
  (`https://log.5kadventures.net` if it follows the pattern).
- Background photo is `public/podcast-bg.webp`. To swap it, drop in a
  replacement at the same name — roughly 2000px wide, WebP, and check
  `object-position` in the CSS still keeps faces clear of the text.

Layout note: the content sits in the lower third on purpose, with the
gradient heaviest at the bottom, so the three faces stay visible rather
than being covered by the heading.
