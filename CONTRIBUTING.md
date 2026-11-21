# Contributing to prelum

Thank you for taking the time. Prelum is a small tool kept simple on purpose, so the best contributions are focused: a bug fixed, a theme refined, an example that shows a real use.

## Before you start

- **Bugs**: open an issue with the Markdown that triggers it (the smallest file you can make), the command you ran and what you expected. A screenshot of the PDF helps more than a description of it.
- **Ideas and new features**: open an issue first, before writing code. Prelum stays one package with few dependencies, so some good ideas will not fit, and it is better to find out early.
- **Themes**: improvements to `report` and `technical` are very welcome. Attach before and after images of the pages you changed.

## Setup

You need Node 22.12 or later and Chrome or Edge (or run `npx playwright install chromium` once).

```sh
git clone https://github.com/prelum/prelum.git
cd prelum
npm ci
npm run dev -- ~/notes/any.md         # runs the CLI straight from the TypeScript source
```

## Checks

These are what CI runs on every pull request. Run them before you push:

```sh
npm run lint        # Biome: formatting and lint (npm run fix applies the fixes)
npm run typecheck   # strict TypeScript
npm test            # vitest, including tests that open a real browser
```

If you changed a theme, also run `npm run examples` and commit the regenerated PDFs and previews: the diff then shows exactly which pages changed. Every pull request also gets the example PDFs as a CI artifact, for a closer look.

## Pull requests

- One change per pull request, branched from `main`. CI must pass before merging; `main` keeps a linear history.
- Titles and commits follow [Conventional Commits](https://www.conventionalcommits.org) (`fix:`, `feat:`, `docs:`, `chore:`…), in English, one line each.
- Small commits that each explain one step are preferred: the history is meant to be read.
- Add or update tests for what you change. A visual change is checked by looking at the PDF.

## Conventions

- **Code, names, commits and issues in English.** Terminal messages exist in English and Portuguese (`src/i18n.ts`).
- **Offline.** Nothing is fetched at runtime: fonts, Mermaid and themes ship with the package.
- **No CSS for the user.** Everything a user sets lives in the frontmatter; `--css` is an escape hatch, not the way.
- **Same input, same PDF.** Do not add anything that makes the output depend on the machine or the clock.
- **Tone.** Messages are calm and precise, with no emoji or exclamation marks. Warnings say what was handled; errors say what to do.

## License

By contributing, you agree that your contributions are licensed under the [MIT License](https://github.com/prelum/prelum/blob/main/LICENSE).
