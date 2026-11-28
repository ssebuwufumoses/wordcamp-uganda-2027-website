# Components

Each component is made of normal core blocks. A `wcu-` class in the block's **Advanced → Additional CSS class(es)** field connects it to its styles in [`custom.css`](../src/styles/custom.css). Size, colour and spacing stay in the block settings, so they can be edited without CSS.

To find a component's CSS, search `custom.css` for its class name or its section comment.

## Site-wide

| Component | Classes | What it does |
| --- | --- | --- |
| Header | `wcu-site-header`, `wcu-mainbar`, `wcu-brand`, `wcu-mainnav` | Sticky header with logo, menu, search and ticket button |
| Ticket button | `wcu-header-cta`, `wcu-ticket-cta` | Ticket-stub button with side notches and perforation. Shine on hover/focus only |
| Header search | `wcu-header-search` | Core Search block, button-only. When it opens, the menu steps aside and the bar takes its place, so it never pushes the ticket button. On phones the open bar spans the header |
| Mobile menu | core Navigation overlay | White overlay. The current page is marked with an ink dot (yellow fails contrast on white) |
| Pattern band | `wcu-pattern-edge` | Thin strip of the official pattern artwork under heroes and above the footer |
| Page hero | `wcu-page-hero`, `wcu-crumbs` | Dark hero with breadcrumbs on inner pages. Uses the featured image when there is one |

## Home page

| Component | Classes | What it does |
| --- | --- | --- |
| Hero | `wcu-hero-cover`, `wcu-hero-copy`, `wcu-hero-ghost` | Small "WordCamp Uganda 2027" label (the page's only H1), then the big headline (H2), date pill "12–13 March 2027", venue line, the #WCUG hashtag, ticket and secondary buttons. Lives in the **Home – Hero** template part (see [performance.md](performance.md)) |
| The two days | `wcu-days-grid`, `wcu-day-card`, `wcu-stamp`, `wcu-stamp-photo` | Two postage-stamp cards with perforated edges and a postmark (decorative) |
| Get involved | `wcu-way-mosaic`, `wcu-way`, `wcu-way-meta`, `wcu-way-link` | Photo mosaic. The whole card is the link |
| Uniquely Uganda | `wcu-uniq`, `wcu-uniq-grid`, `wcu-uniq-tile`, `wcu-uniq-photo`, `wcu-uniq-link` | Travel tiles (visa, invitation letter, arrival, health, weather). Two per row on tablet, one on small phones |
| Sponsor logos | `wcu-sponsor-logos` | Rows of three logos. Height is capped per logo so wide and tall marks look balanced. Greyscale, colour on hover |
| Latest news | `wcu-news`, `wcu-news-card`, `wcu-news-photo` | Query Loop of the newest posts. Cards with a photo are cut to the outline of Uganda |

## Content pages

| Component | Classes | What it does |
| --- | --- | --- |
| FAQ | `wcu-faq` | Core Details blocks styled as an accordion, with a jump list on the FAQ page |
| Travel guides | (section "Travel guides") | Numbered steps, key-value lists, sticky side card |
| Sponsorship packages | (section "Sponsorship packages v2", "Compare table") | Package cards with a ticket tear-line, add-on cards and a comparison table that scrolls sideways on phones |
| Sponsors page | `wcu-sponsor-grid` | WordCamp Sponsors block shown as an open logo wall that matches the home page |
| Organizers | `wcu-team-section`, `wcu-org-*` | Team grid. The + on each tile opens a centred profile card made with `details`/`summary` (no JavaScript), see below |
| Single organizer | `wcu-pass`, `wcu-pass-stage` | Profile shown as an event pass |
| Blog cards | `wcu-post-grid`, `wcu-post-card`, `wcu-post-meta` | News archive cards |

## Organizer profile card

Each organiser tile is a core Details block (`wcu-org-pop`). Opening it shows the profile as a card in the middle of the screen.

- **Backdrop:** the page dims behind the card. There is no blur, because a blurred page is tiring to look at.
- **Closing:** the × sits on the card's own top-right corner (44px, with a white ring so it shows over any photo). Clicking the dimmed page also closes it.
- **Size:** `--wcu-card-w` and `--wcu-card-top` set the card's width and distance from the top. The × uses the same two values, so it always lands on the card's corner.
- **Photo fills the card:** the WordCamp avatar block writes a fixed `width:512px` on the photo frame. `min-width:100%` on `.wcu-drawer-photo` overrides it without `!important`, so the photo always spans the card.
- **No scrolling inside the card:** on smaller screens the photo shrinks first and the bio is capped (7 lines, 5 under 640px high, 3 under 520px, 2 under 420px). On very short screens (phones in landscape) the photo and the small "Organizing team" label are hidden. "View full profile" is always visible.
- **Tested at:** 1920×1080, 1536×735, 1366×768, 1280×600, 1024×768, 768×1024, 414×896, 375×667, 360×640, 320×568, 740×360 and 667×375.

## Decorative motifs

These carry the event's "travel" theme. All are decorative: they're hidden from screen readers or drawn in CSS, and motion is off with reduced motion.

- **Postage stamp:** perforated frame and postmark (The two days, letter cards)
- **Passport stamp:** tilted stamp (`wcu-btn-badge`)
- **Boarding pass:** notched stub with perforation
- **Ticket notch:** side notches on cards that carry the pattern artwork

## Icons

Icons are [Lucide](https://lucide.dev/) SVGs (ISC licence), stored as CSS custom properties (`--wcu-icon-*`) and drawn with CSS `mask`, so they take the text colour.
