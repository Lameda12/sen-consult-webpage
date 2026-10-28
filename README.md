# Senior Consulting Agents: landing page

Install page for [senior-consulting-agents](https://github.com/Lameda12/senior-consulting-agents): 54 senior consulting agents, 11 commands and 2 skills for Claude Code, Codex, Gemini CLI, Cursor and any agent that supports Agent Skills.

One static `index.html`. No build step, no dependencies.

## Deploy

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/Lameda12/sen-consult-webpage)

Or from the CLI:

```bash
npx vercel --prod
```

Vercel detects a static site automatically. Leave Framework Preset as "Other" and the build command empty.

## Run locally

```bash
npx serve .
```

## Edit

Everything lives in `index.html`: commands and agents are plain arrays near the bottom of the `<script>` block. Update them when the main repo adds personas.

## License

MIT. Unofficial; not affiliated with or endorsed by any professional-services firm.
