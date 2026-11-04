# legaltech-starter

A starting point for lawyers and law students who want their own live website,
or a small legal tool, built with Claude Code and no coding background.

What you get:

- `site/index.html`: a bilingual (English / Ukrainian) business-card page to
  rewrite with Claude.
- A GitHub Pages deploy: every push to `main` publishes the site.
- `CLAUDE.md`: rules Claude follows here (not-legal-advice line, no real client
  data, sources for every legal claim).
- `.claude/settings.json`: turns on plugins from
  [kulykivska/claude-plugins](https://github.com/kulykivska/claude-plugins) that
  check facts, review text for legal risk, take the AI tone out of writing,
  audit SEO and block secrets or personal data before a push.

## Start in five minutes

1. Click **Use this template**, then **Create a new repository**. Name it after
   yourself, for example `olena-kovalenko`.
2. Open it in Claude Code. In the desktop app or the terminal:
   `git clone https://github.com/<you>/<repo>.git && cd <repo> && claude`
3. When Claude Code asks whether to trust the folder and install the project's
   plugins, say yes. Or paste the setup prompt below.
4. Ask Claude: "Make this my site. Here is my name, my bio and my contacts: ..."
5. Ask Claude to commit and push. Then on GitHub: Settings, Pages, Source:
   **GitHub Actions**. Your site is at `https://<you>.github.io/<repo>/`.

### Setup prompt: let Claude do it

```text
Set up this project's plugins from kulykivska/claude-plugins.
1. Check that `claude`, `git` and `python3` are available. If python3 is missing,
   skip guardrails and pre-push-review and tell me why.
2. Run `claude plugin marketplace add kulykivska/claude-plugins`.
3. Install each of these with `--scope project`:
   content@personal, brand@personal, seo@personal, research@personal,
   guardrails@personal, pre-push-review@personal.
4. Run `claude plugin list` and show me what is enabled.
5. Tell me to restart Claude Code so the plugins load, then give me three things
   to try: humanize my bio, legal-review my site text, fact-check one claim.
```

**On claude.ai/code in the browser** plugins do not load. Nothing breaks:
`CLAUDE.md` tells Claude to read the same instructions straight from the
plugins repository.

## Rules worth saying out loud

- The site is public. No real client names, documents or contacts.
- A page that explains law says it is general information, not legal advice.
- No API keys in the site. A tool that needs AI inside it is a Claude artifact,
  not a GitHub Pages page.

## Ideas to build next

- A case brief in IRAC form from pasted text (as a Claude artifact)
- A deadline calculator for a court or an immigration form
- A bilingual intake checklist for a community clinic, with made-up data only
- A time tracker for clinic hours

If something here helped, a star on
[claude-plugins](https://github.com/kulykivska/claude-plugins) tells me to keep
building tools for lawyers.

## License

MIT
