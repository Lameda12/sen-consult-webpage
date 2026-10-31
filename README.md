# Firmcraft: landing page

Landing page for [Firmcraft](https://github.com/Lameda12/Firmcraft-skill): 13 B2B workflows, 54 specialist personas (7 of them sector personas) and 2 portable skills for Claude Code, Codex, Gemini CLI and other assistants that can load skills.

One static `index.html` plus a few local assets. No build step, no dependencies, no framework.

## Structure

| Path | What it is |
|---|---|
| `index.html` | The whole page: styles, inline SVG illustrations, markup and a small vanilla script |
| `assets/firmcraft-mascot.{webp,png}` | The beaver mascot from the product repo, resized, proportions unchanged |
| `assets/og.png` | 1200 x 630 social preview |
| `assets/favicon.svg` | Favicon |
| `vercel.json` | Hosting config (clean URLs and security headers), unchanged |

The three featured workflow thumbnails (management reporting, supplier risk, proposals) and the hero core are hand-written inline SVG. The hero trails are a small canvas flow-field (potential flow around a cylinder) that pauses when the hero is offscreen or the tab is hidden.

## Motion and accessibility

- Animations use transform and opacity (plus dash offsets on a few thin SVG lines) and pause when offscreen.
- Cursor tilt and hero parallax only run with a fine pointer; there is no scroll hijacking or custom cursor.
- `prefers-reduced-motion` gives a complete static page: no reveals, no animation, one painted frame of the flow field.
- Tabs and filters follow WAI-ARIA patterns (roving tabindex, arrow/Home/End keys), focus rings are always visible, and the library announces result counts.

## Content source of truth

Counts, workflow names, persona ids and install commands come from [Lameda12/Firmcraft-skill](https://github.com/Lameda12/Firmcraft-skill). The installed identifiers are still `senior-consulting-agents` and `consulting-deliverable-standards`; `/firmcraft:…` commands do not exist, so the page never shows them.

When the product repo changes, update these in `index.html`:

- the hero and section copy that mentions 13 workflows / 54 personas / 7 sector personas / 2 skills
- the `workflows` array (from the README's "All workflows" table)
- the `personas` array (ids and role titles from `agents/*.md`, grouped by `scripts/practices.json`)
- the install snippets

The example section uses the synthetic figures from the product README's quick start and is labeled illustrative.

## Run locally

```bash
npx serve .
```

Fonts (Geist, Geist Mono, Instrument Serif) load from Google Fonts with system fallbacks, so the page stays usable offline.

## Deploy

Vercel detects a static site automatically. Leave Framework Preset as "Other" and the build command empty.

```bash
npx vercel --prod
```

`og:image` and `twitter:image` use the relative path `assets/og.png`. Some crawlers need an absolute URL, so set it to your production domain once it is fixed.

## License

MIT. Unofficial; not affiliated with or endorsed by any professional-services firm. Outputs of the product are AI drafts for qualified review.
