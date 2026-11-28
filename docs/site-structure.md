# Site structure

## Main menu

The menu follows the order a visitor's questions come in: what is it, how do I go, how do I get there, how can I take part, who supports it, what's new.

| Item | Links to | Sub-items |
| --- | --- | --- |
| About | `/about/` | About WordCamp Uganda, Organizers, FAQ, Contact, Code of Conduct |
| Attend | `/tickets/` | Tickets, Attendees |
| Contributor Day | `/contributor-day/` | (top level, it's a separate day with its own audience) |
| Travel | `/location/` | Venue & Travel, Discover Kampala, Visas & entry, Invitation letter, Arriving by air, Arriving by road, Health & safety |
| Open calls | `/get-involved/` | Call for Speakers, Sponsors, Volunteers, Media Partners |
| Sponsors | `/sponsors/` | |
| News | `/blog/` | |

The header also has a search button and a **Get tickets** button. Source: [`src/navigation/main-menu.html`](../src/navigation/main-menu.html), [`src/parts/header.html`](../src/parts/header.html).

## Footer

| Column | Links |
| --- | --- |
| Explore | Tickets, Venue & Travel, FAQ, Contributor Day, News |
| Get involved | Open calls (`/get-involved/`), Sponsors, Contact us, WordCamp Central ↗, WordPress.org ↗ |
| Bottom bar | Privacy (WordPress.org policy), Code of Conduct |

The footer only lists the pages people look for at the end of a page. Everything else is one click away in the menu.

## Pages

| Page | Slug | Notes |
| --- | --- | --- |
| Home | `/` | Front Page template |
| About WordCamp Uganda | `/about/` | |
| Organizers | `/organizers/` | `page-no-title` template, Organizers dynamic grid (synced pattern). I'm listed in the **Website Team** |
| FAQ | `/faq/` | |
| Contact | `/contact/` | Jetpack form |
| Code of Conduct | `/code-of-conduct/` | |
| Tickets | `/tickets/` | CampTix, see [tickets.md](tickets.md) |
| Attendees | `/attendees/` | CampTix attendee list |
| Contributor Day | `/contributor-day/` | |
| Venue & Travel | `/location/` | Parent of the travel guides |
| ↳ Visas & entry | `/location/visa/` | |
| ↳ Visa invitation letter | `/location/visa-letter/` | |
| ↳ Arriving by air | `/location/arriving-by-air/` | |
| ↳ Arriving by road | `/location/arriving-by-road/` | |
| ↳ Health & safety | `/location/health-safety/` | |
| Discover Kampala | `/kampala/` | |
| Get involved | `/get-involved/` | Hub linking to the four open calls |
| Sponsors | `/sponsors/` | WordCamp Sponsors block |
| Schedule | `/schedule/` | Platform page |
| Sessions | `/sessions/` | Platform page |
| Blog | `/blog/` | Posts page (Blog Home template) |
| Leave Feedback | `/feedback/` | Platform page |
| Offline | `/offline/` | Platform page shown when a visitor has no connection |

## Posts

The four open calls are posts using the **Post — Full-width landing** template:

- Call for Speakers
- Call for Sponsors (sponsorship packages and comparison table)
- Call for Volunteers
- Call for Media Partners

## Templates

| Template | File | Used for |
| --- | --- | --- |
| Front Page | `front-page.html` | Home page. Only places the header, the two home template parts and the footer |
| Pages | `page.html` | Default page, with page hero and the pattern artwork band |
| Single Posts | `single.html` | News posts |
| Post — Full-width landing | `single-landing.html` | Open calls |
| Blog Home | `home.html` | `/blog/` |
| All Archives | `archive.html` | Categories, dates |
| Organizer team | `taxonomy-wcb_organizer_team.html` | Organiser team archives |
| Single Organizer | `single-wcb_organizer.html` | Organiser profiles |
| Search Results | `search.html` | Site search |
| Page: 404 | `404.html` | Not found |

## Template parts

| Part | File | What it holds |
| --- | --- | --- |
| Header | `header.html` | Utility bar, logo, menu, search and ticket button |
| Footer | `footer.html` | Footer columns and bottom bar |
| Home – Hero | `home-hero.html` | The home page hero |
| Home – Sections | `home-sections.html` | Every home page section after the hero |

The home page content sits in two template parts instead of directly in the Front Page template. On WordCamp.org, images inside template parts get WordPress's loading optimisation (priority for the hero photo, lazy loading for the rest) and images saved directly in a template don't. See [performance.md](performance.md).

To edit the home page, open **Site Editor → Patterns → Template parts → Home – Hero** or **Home – Sections**, or click into them on the Front Page template.

## Home page sections

In order: Hero (Home – Hero part) → Pattern edge → Voices → The two days → Get involved → Meetup communities route → Uniquely Uganda → Our Partners (sponsor logos) → Latest news (all in the Home – Sections part).

## Synced patterns

| Pattern | Used on |
| --- | --- |
| Meetup communities route | Home – Sections template part |
| Organizers dynamic grid | Organizers page, Single Organizer template |
