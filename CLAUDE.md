# LegalTech starter

The person working here is a law student or a lawyer, usually with no coding
background. Explain what you do in plain words, one step at a time, and in the
language they write to you in (often Ukrainian).

## What we build

A public personal site in `site/`, published with GitHub Pages by
`.github/workflows/pages.yml` on every push to `main`. The site is plain HTML
and CSS: no build step, no framework, no server.

Typical goals: a bilingual (Ukrainian / English) business card, a practice-area
page, a guide for a community, or a small tool that runs in the browser
(a deadline calculator, a time tracker, a checklist).

## Rules that always apply

- **Not legal advice.** Every page that explains law carries a visible line:
  "This is general information, not legal advice." Keep it in both languages.
- **No real client data.** Never put real names, cases, documents, emails or
  phone numbers of clients into the repository. The site is public. Use made-up
  examples and say so.
- **No secrets.** No API keys or passwords in any file. A tool that needs an
  AI model behind it does not belong on GitHub Pages; say so and suggest a
  Claude artifact instead.
- **Facts need sources.** Any statement about a law, a deadline, a fee or a
  government process links to the official source (uscis.gov, ilga.gov,
  illinoiscourts.gov and similar). If you cannot find one, say it is
  unverified instead of writing it as fact.
- **Accessible and mobile first.** Real headings, alt text on images, readable
  contrast, works on a phone.
- Keep the footer credit in `site/index.html`.

## Plugins

This project turns on plugins from
[kulykivska/claude-plugins](https://github.com/kulykivska/claude-plugins)
(see `.claude/settings.json`). Use them at these moments:

| Moment | Use |
|---|---|
| Writing or editing any text on the site | `humanizer` skill, then show the before/after |
| Before publishing a page that mentions a person, a company or the law | `legal-reviewer` subagent |
| Any legal or factual claim | `fact-checker` subagent |
| A question that needs research | `researcher` subagent |
| After the first deploy | `/seo-audit` on the live URL |
| Before every push | the pre-push review gate runs on its own; let it finish |

If those plugins are not available in this session (claude.ai/code web
sessions do not load plugins), read the same instructions straight from the
repository and follow them as written:

- humanizer: https://raw.githubusercontent.com/kulykivska/claude-plugins/main/content/skills/humanizer/SKILL.md
- legal-reviewer: https://raw.githubusercontent.com/kulykivska/claude-plugins/main/brand/agents/legal-reviewer.md
  and its policy https://raw.githubusercontent.com/kulykivska/claude-plugins/main/brand/references/contract-safety.md
- fact-checker: https://raw.githubusercontent.com/kulykivska/claude-plugins/main/content/agents/fact-checker.md
- researcher: https://raw.githubusercontent.com/kulykivska/claude-plugins/main/research/agents/researcher.md
- seo-audit: https://raw.githubusercontent.com/kulykivska/claude-plugins/main/seo/skills/seo-audit/SKILL.md

## Publishing

1. Commit and push to `main`.
2. The first time only: in the repository on GitHub, open Settings, then Pages,
   and set Source to "GitHub Actions".
3. The Actions tab shows the deploy; the site appears at
   `https://<username>.github.io/<repository>/`.
4. Search engines take days to list a new site. Searching for the person's
   full name works first.
