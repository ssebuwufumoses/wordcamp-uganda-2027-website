# Maintaining the site

## Before you change anything

- Work in the Site Editor (Appearance → Editor) or the page editor. There are no theme files to edit.
- Check if a block setting can do it before adding CSS.
- Templates and template parts keep revisions, so a bad change can be rolled back.

## Editing Additional CSS safely

Additional CSS is stored inside Global Styles, together with the palette and fonts.

- Edit it in **Site Editor → Styles → Additional CSS**. The editor saves the whole Global Styles object, which is safe.
- If you update Global Styles through the REST API, always send the **full** `styles` and `settings` objects. Sending only `styles.css` replaces everything else and wipes the palette, fonts and element styles.
- After saving, check that colours, headings and buttons still look right on the home page.
- Add new rules under a labelled section comment, scoped to a `wcu-` class.

## Adding a section to a page

1. Build it with core blocks.
2. Set sizes, colours and spacing in block settings, using palette colours.
3. If it needs CSS, add a `wcu-` class in Advanced → Additional CSS class(es) and style only that class.
4. If the same section appears on more than one page, make it a synced pattern.
5. Check it at 240px and with the keyboard (see [accessibility.md](accessibility.md)).

## Content rules

- No em dashes in site text. Use a comma, colon or full stop.
- Prices in USD with the UGX amount alongside.
- Every new page and post gets a Jetpack SEO title and description (see [seo.md](seo.md)).
- Delete media that's no longer used.

## Exporting changes to this repository

The files in `src/` are exports of the live site. After a change on the site:

1. Copy the updated template or part from the Site Editor (⋮ → Code editor) into the matching file in `src/`.
2. For Global Styles, copy Additional CSS into `src/styles/custom.css`. Update `global-styles.json` if the palette, fonts or element styles changed.
3. Commit on a branch with a clear message, open a pull request and merge it.

## Checking the CSS

The CSS follows the [WordPress CSS coding standards](https://developer.wordpress.org/coding-standards/wordpress-coding-standards/css/), checked with the official `@wordpress/stylelint-config`.

```bash
npm ci
npm run lint:css        # check
npm run lint:css:fix    # fix formatting automatically
```

The config (`.stylelintrc.json`) changes three rules:

- `selector-class-pattern` is off, because the CSS has to target WordPress core and plugin class names such as `wp-block-button__link`, which don't follow the lowercase-hyphen pattern.
- `no-descending-specificity` and `no-duplicate-selectors` are warnings. The remaining cases are a selector that also appears inside a longer selector group. Reordering them would change which rule wins, so they're left as they are.

The same check runs automatically on every pull request that changes the CSS. Warnings don't fail it; errors do.

## Commit messages

This repository uses [Conventional Commits](https://www.conventionalcommits.org/):

| Type | Use for |
| --- | --- |
| `docs:` | Documentation changes |
| `feat:` | A new section, page or template exported from the site |
| `fix:` | A bug fix exported from the site |
| `style:` | Visual-only CSS changes |
| `chore:` | Repository housekeeping |

Example: `fix(tickets): stack coupon field on screens under 360px`
