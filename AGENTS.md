# AGENTS.md

## Repository scope

`streetshots-talks` contains LaTeX Beamer source and assets for marketing slides and presentations about [Streetshots](https://streetshots.io) and [YouSpeed](https://youspeed.de).

| Sister repository | Responsibility |
| --- | --- |
| `streetshots-web` | Public website |
| `youspeed.de` | YouSpeed app code |
| `streetshots-inspector` | Server-side app code |
| `woladen.de-analytics` | Backend |
| `streetshots-survey` | Expert app code |

Keep presentation work in this repository. Use the relevant sister repository for changes to the site, apps, or backend.

## Repository layout

- `assets/` holds images, screenshots, and other media. Add a new file when updating an asset that a past talk uses. Keep the original path available to that talk.
- `talks/<event>/` holds the Beamer source and event-specific files for one presentation. Follow the existing `YYYY-MM-DD-<event>` directory pattern for new talks.
- `talks/shared/` holds reusable Beamer frames, themes, macros, and other common presentation files. Keep event-specific details in the individual talk directories.

## Preparing and reusing talks

- Create a separate copy under `talks/` for every delivery, even when presenting the same material again. Start from the closest existing deck and adapt the new copy to the event and audience.
- Preserve the version delivered at each event. When changing shared material would alter a past talk or prevent it from building, give the changed material a new path or keep the past talk's dependency with that talk.
- Reference common frames and assets using relative paths within the repository. When copying a deck, check that its references still resolve from the directory where it is compiled.

## Building and checking slides

- Compile the affected deck from its talk directory with the LaTeX engine specified by the deck. For a pdfLaTeX deck, use `latexmk -pdf -interaction=nonstopmode -halt-on-error <deck>.tex` with the actual entry-point filename.
- Review the rendered PDF for missing graphics, clipped or overflowing content, and correct event details. When editing a shared file, also check the decks that reference it.
- Keep temporary LaTeX output such as `.aux`, `.log`, `.nav`, `.snm`, and `.fls` files out of commits. Include a PDF when the task calls for a deliverable or archival copy.

## Git workflow

- Work on the current branch. Check `git status --short` before and after changes and preserve unrelated local modifications.
- Create or switch branches, commit, push, or open a pull request only when requested. Verify the remote default branch before using it.
- Merge, deploy, publish, or delete a branch only with explicit approval.
