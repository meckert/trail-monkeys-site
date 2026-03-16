Trail Monkeys Rosenheim — Static Website Prototype
====================================================

A local-first, plain HTML/CSS/JS static website for Trail Monkeys Rosenheim,
the kids' mountainbike training program of Trendsport TSV 1860 Rosenheim e.V.


PROJECT STRUCTURE
-----------------

trail-monkeys-site/
  index.html              Homepage (hero, intro, feature highlights)
  pages/
    training.html         Training groups, times, location, costs
    anmeldung.html        Registration (Google Form embed)
    galerie.html          Photo gallery with keyboard-accessible lightbox
    kontakt.html          Contact info, TSV link, Instagram
  assets/
    css/
      design-tokens.css   Color variables, typography tokens, spacing
      base.css            Reset, global element styles
      layout.css          Header, nav, hero, footer, page grid
      components.css      Buttons, cards, lightbox, form, gallery grid
    fonts/                Place woff2 web font files here (see FONTS below)
    img/                  Hero background and gallery images (see IMAGES below)
    logo/
      trail-monkeys-embedded.svg   Logo (base64-embedded PNG, ~810 KB)
  README.txt              This file
  QA_CHECKLIST.txt        Manual QA checks before publishing
  QA_REPORT.md            Status report and next steps


RUNNING LOCALLY
---------------

Option A — Python (recommended, no install required):

  cd trail-monkeys-site
  python3 -m http.server 8000

  Then open: http://localhost:8000

Option B — Open directly in browser:

  Open index.html in any modern browser (Firefox, Chrome, Safari, Edge).
  Note: some features (relative paths, iframe) may behave differently without
  a local server. Option A is preferred.


IMAGES (TODO)
-------------

No real photos are included in this prototype. To add them:

1. Add hero background images to assets/img/:
   - hero-bg.webp  (recommended: 1920x1080px or wider)
   - hero-bg.jpg   (JPEG fallback, same dimensions)

2. Add gallery photos to assets/img/:
   - foto-01.webp + foto-01.jpg
   - foto-02.webp + foto-02.jpg
   - ... (as many as needed)

3. In galerie.html, replace each <div class="gallery-placeholder"> block
   with a real <picture> element. Example:

   <picture>
     <source srcset="../assets/img/foto-01.webp" type="image/webp">
     <img src="../assets/img/foto-01.jpg"
          alt="Kinder fahren am Dirtpark Rosenheim"
          loading="lazy">
   </picture>

   Also update the data-full and data-caption attributes on the <figure>
   element to point to the full-resolution image URL.

4. In index.html, uncomment the <picture> block in the .hero-bg div and
   replace the placeholder once images are available.


FONTS (TODO)
------------

The site uses the system font stack by default. To use branded web fonts:

1. Place .woff2 files in assets/fonts/
2. Add @font-face declarations in assets/css/base.css (see comment at top)
3. Update --font-heading and --font-body in assets/css/design-tokens.css

Example @font-face block:

  @font-face {
    font-family: 'YourFont';
    src: url('../fonts/yourfont-bold.woff2') format('woff2');
    font-weight: 700;
    font-display: swap;
  }


GOOGLE FORM (TODO)
------------------

The registration form embed is a placeholder. To activate it:

1. Open your Google Form
2. Click Share > Embed > Copy the iframe src URL
   Format: https://docs.google.com/forms/d/e/[FORM_ID]/viewform?embedded=true
3. In pages/anmeldung.html, replace both occurrences of:
   REPLACE_WITH_REAL_FORM_ID
   with your actual form ID.


OTHER TODOs
-----------

- Training times (exact start/end times for each group):
  → Edit pages/training.html, look for [TODO: insert exact times]

- Gear list confirmation with trainers:
  → Edit pages/training.html, look for [TODO: verify gear list]

- Datenschutz (Privacy Policy) page:
  → Create pages/datenschutz.html and update footer links in all pages.
  → Required by German law (DSGVO / GDPR). Consult legal if needed.

- Impressum page:
  → Create pages/impressum.html with full legal notice.
  → Required by German law (TMG §5). Must include name and address.

- Final domain URL for JSON-LD in index.html:
  → Search for "https://trail-monkeys-rosenheim.de" in index.html


BROWSER SUPPORT
---------------

Targets modern evergreen browsers (Chrome, Firefox, Safari, Edge).
No IE11 support. Uses CSS custom properties, flexbox, CSS grid, aspect-ratio.


DEPENDENCIES
------------

None. Zero external CDNs, no npm, no build step required.
