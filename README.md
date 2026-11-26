# WordCamp Uganda 2027 website

Documentation and source for the [WordCamp Uganda 2027](https://uganda.wordcamp.org/2027/) website.

WordCamp Uganda 2027 is the 10th anniversary edition of Uganda's WordPress conference: **12–13 March 2027, Imperial Royale Hotel, Kampala**. The second day is Contributor Day.

I built the site on the official WordCamp.org platform with the WordPress block editor. Everything here describes the live site as it is, so other organisers can maintain it, and future WordCamp teams can reuse what works.

## What's in this repository

| Path | What it is |
| --- | --- |
| [`docs/`](docs/) | How the site is built and how to work on it |
| [`src/templates/`](src/templates/) | Block templates exported from the Site Editor |
| [`src/parts/`](src/parts/) | Header and footer template parts |
| [`src/patterns/`](src/patterns/) | Synced patterns used across pages |
| [`src/navigation/`](src/navigation/) | Main menu (Navigation block) |
| [`src/styles/global-styles.json`](src/styles/global-styles.json) | Global Styles: palette, fonts, element and block styles |
| [`src/styles/custom.css`](src/styles/custom.css) | Additional CSS from Global Styles, labelled by section |
| [`package.json`](package.json), [`.stylelintrc.json`](.stylelintrc.json) | CSS checks with the official WordPress stylelint config (`npm run lint:css`) |
| [`.github/`](.github/) | Security policy, pull request template, and the CSS check that runs on every pull request |

The files in `src/` are exports. The live site is the source of truth: changes are made in the Site Editor, then exported here.

## Documentation

1. [Platform and limits](docs/platform-limits.md): what WordCamp.org allows and what it doesn't
2. [Design system](docs/design-system.md): colours, type, spacing, pattern artwork and components
3. [Site structure](docs/site-structure.md): pages, menu, footer and templates
4. [Components](docs/components.md): the reusable building blocks and their class names
5. [Tickets](docs/tickets.md): CampTix setup and ticket page
6. [SEO and social sharing](docs/seo.md): Jetpack SEO and share images
7. [Accessibility](docs/accessibility.md): what's tested and how
8. [Maintaining the site](docs/maintaining.md): how to make changes safely and export them here

## Stack

- **Platform:** WordCamp.org (WordPress multisite run by the WordPress community)
- **Theme:** Twenty Twenty-Five (block theme), customised only through the Site Editor
- **Plugins in use (platform-provided):** CampTix for tickets, Jetpack for SEO, forms and social previews, WordCamp blocks for sponsors, organisers, sessions and speakers
- **Custom code:** no plugins and no custom JavaScript. Styling is Global Styles plus one Additional CSS stylesheet.

## Credits

The official WordCamp Uganda pattern artwork (the graphic design, not a block pattern) was designed by Kasirye Arthur. The organising team reviewed the site and suggested improvements. See [CREDITS.md](CREDITS.md).

## Licence

Copyright © 2026 Moses Ssebuwufu.

- Code (`src/`): [GPL-2.0-or-later](LICENSE), the same as WordPress.
- Documentation (`docs/`, this README): [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/).
- Photos, logos, sponsor logos and the WordCamp Uganda pattern artwork are **not** included and are not covered by these licences.
