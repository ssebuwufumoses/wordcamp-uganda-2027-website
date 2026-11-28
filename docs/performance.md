# Performance

Measured with [PageSpeed Insights](https://pagespeed.web.dev/) on the home page, 28 November 2026.

| | Performance | Accessibility | Best Practices | SEO |
| --- | --- | --- | --- | --- |
| Mobile | 93–96 | 100 | 100 | 100 |
| Desktop | 97 | 100 | 100 | 100 |

Agentic Browsing passes both checks (2/2).

Mobile Performance was 87 before the changes below, with Largest Contentful Paint (LCP) at 4.1 s. It's now about 2.8 s.

## What made the difference

### 1. The hero photo loads first

WordPress gives `fetchpriority="high"` to the first large image on a page and `loading="lazy"` to images further down. Two things stopped that from working here:

- **The header logo took the priority.** The logo image block used the full 480px file, so WordPress treated the logo as the most important image. The block now uses the **Medium** (300px) size. It still displays at 190px, so it looks the same.
- **Images saved directly in the Front Page template get no loading optimisation on WordCamp.org.** Images inside template parts do. So the home page content moved into two template parts: **Home – Hero** and **Home – Sections**. The layout is identical (every section was measured before and after), and both parts are edited in the Site Editor like the header and footer.

Now the hero photo has `fetchpriority="high"` and every image below it has `loading="lazy"`.

### 2. Smaller hero file

The hero photo is a WebP (`wordcamp-kampala-2026-hero.webp`) instead of a JPEG. The saving is small, because WordPress regenerates each size at its own quality setting.

### 3. Photos were checked for compression

Every photo on the home page was compared with a high-quality WebP (quality 85). Together they'd shrink only from about 830 KB to 686 KB, because they were already well compressed. That's not worth re-uploading and re-linking about 20 images, and bigger savings would mean lowering quality. New photos should be uploaded as WebP, about 1600px wide.

### 4. Jetpack image delivery on, static files off

Jetpack → Performance & speed has two switches. Tested on 28 November 2026:

| Setting | Effect | Keep it |
| --- | --- | --- |
| Images from Jetpack's network | Photos in page content are served from `i0.wp.com` as WebP, from the server nearest the visitor. Nothing looks different and every image loads | **On** |
| Speed up static file load times | Core CSS and JavaScript come from `c0.wp.com`. The CSS needed before the page can show then sits on a second server, and mobile Performance dropped from the 90s to 79 (Largest Contentful Paint 5.7 s) | **Off** |

With static files off again, mobile Performance went back to 90.

Images inside template parts (the home page, header and footer) still come from the site itself. Jetpack only rewrites images in page content.

## What's left, and why it can't reach 100

The remaining points are lost to files the platform loads on every WordCamp site:

| PageSpeed item | Cause | Can I fix it? |
| --- | --- | --- |
| Render-blocking requests (~0.9 s) | Jetpack sharing and social-icon CSS, core block CSS | No: plugins and core are managed by WordCamp.org |
| Reduce unused JavaScript (~140 KB) | WordCamp and Jetpack scripts | No |
| Font display (~0.2 s) | The theme's built-in Manrope font file | No: theme files can't be edited |
| Improve image delivery | Photos uploaded as JPEG | Yes: compress photos and upload WebP around 1600px wide |

Realistically, mobile tops out around 95–97 on this platform and desktop around 97–100.

## Reading the score correctly

- **The first test after a save is slow.** Saving a template, part or Global Styles clears the site's page cache, so the next visitor gets a freshly built page. A run straight after a save scored 71–79, and the same page scored 93–95 a minute later. Run the test twice and use the second result.
- **Mobile moves a few points between runs** even when nothing changed, because PageSpeed simulates a slow phone on a slow network. 93, 95 and 96 on the same day is normal.

## Keeping it fast

1. Compress photos and size them for their slot before upload (see [seo.md](seo.md#images)).
2. Keep new home page content inside the **Home – Hero** or **Home – Sections** template parts, not directly in the Front Page template.
3. For the image at the top of a page, use a size close to how big it shows. A full-size file in a small slot can steal the priority from the real main image.
4. Delete media that's no longer used, and CSS for classes that are no longer used (see [maintaining.md](maintaining.md)).
