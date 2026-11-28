# SEO and social sharing

SEO uses **Jetpack**, which is active on WordCamp.org. There's no other SEO plugin.

## Per page and post

Each page and post has, in the editor sidebar under Jetpack SEO:

| Field | Meta key | Guideline |
| --- | --- | --- |
| SEO title | `jetpack_seo_html_title` | Under 60 characters. Lead with the page topic, end with "WordCamp Uganda 2027" where it fits |
| Meta description | `advanced_seo_description` | 140–160 characters. Say what the page answers, include "Kampala" or "2027" where natural |
| Hide from search | `jetpack_seo_noindex` | Only for utility pages |

The same description is used for social previews (Open Graph and X cards) when the page has no custom excerpt.

## Home page

Set in Jetpack settings, not on the page itself:

- **Title** (`advanced_seo_title_formats`, front page): `WordCamp Uganda 2027 (WCUG) | WordPress Uganda Tech Conference`. 62 characters, so it shows in full.
- **Description** (`advanced_seo_front_page_description`): `#WCUG / WCUganda: the WordPress Uganda community’s tech conference, 12–13 March 2027 at Imperial Royale Hotel, Kampala. Talks, workshops and Contributor Day.` 157 characters.
- **Share image:** `wordcamp-uganda-2027-share.jpg`, 2400×1260 (1.91:1), a photo with the event name, dates, venue and the pattern artwork band at the bottom. It's the home page's featured image, which Jetpack uses for `og:image`.

## Keywords

| Keyword | Why |
| --- | --- |
| WordCamp Uganda | What most people type, usually without the year. Google matches it inside "WordCamp Uganda 2027" |
| WCUG, #WCUG | Short form: WC for WordCamp, UG for Uganda. Also the event hashtag |
| WCUganda | Another short form people search |
| WordPress Uganda | People looking for the community, not only the event |
| WordPress conference Uganda, tech conference Uganda, WordPress Kampala | People looking for tech events in Uganda |
| Contributor Day | The second day |

They're used in titles, headings, descriptions and visible text where they read naturally, never stuffed. Google ignores meta keyword lists, and a page packed with keywords ranks lower, not higher.

The home page **H1** is "WordCamp Uganda 2027", a small label above the big headline. The big headline ("A decade of WordPress community in Uganda") is an H2 with the same look, so the page's main heading carries the event name and there's still only one H1.

**#WCUG** also appears on the page itself, in the hero next to the date and venue, because search engines weigh visible text more than meta tags.

## Getting into search results

Good titles don't help until Google has indexed the site. After launch, or after big changes:

1. In Google Search Console (the site is already verified), use **URL Inspection → Request indexing** on the home page and the main pages.
2. Submit the sitemap `https://uganda.wordcamp.org/2027/sitemap.xml`. It's Jetpack's sitemap: `wp-sitemap.xml` doesn't exist on WordCamp.org. I submitted it on 28 November 2026. "Couldn't fetch" straight after submitting is normal, and Google retries on its own.
3. Get links: WordCamp Central's announcement post, the Meetup pages, event listings and organisers' posts using #WCUG with a link to the site.

## Who built the site

So search engines and AI tools can answer "who designed or developed the WordCamp Uganda website", the credit is public on the site's own domain. My organiser profile (`/organizer/moses-ssebuwufu/`) lists me in the **Website Team** and says I designed and developed the event website. [CREDITS.md](../CREDITS.md) says the same. There's no hidden text: Google treats text shown only to search engines as spam.

## Images

- Photos are compressed and sized for their slot before upload.
- Give every content image alt text. Leave alt empty on decorative images.
- Unused media is deleted, so the media library stays small.

## Refreshing a stale preview

Social apps cache previews. After changing a title, description or share image:

- **Facebook / WhatsApp:** open the [Sharing Debugger](https://developers.facebook.com/tools/debug/), paste the URL and click **Scrape Again**. WhatsApp uses the same cache.
- **LinkedIn:** use the [Post Inspector](https://www.linkedin.com/post-inspector/).
- **Quick test:** share the URL with `?v=2` at the end. A new URL gets a fresh preview.
