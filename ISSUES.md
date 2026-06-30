# Site Issues

Compiled from a full scan of all HTML and CSS files in this repo.

---

## eddiegoldsteinmagic/

### Broken / Wrong Internal Links

- [x] **`index.html:99`** — "Enter" button links to `./home.html` but should link to `shows.html` (home.html content was moved there)
- [x] **`poi.html:72`** — MadHatter banner `<a href>` points to `http://eddiegoldsteinmagic.com` instead of `index.html`
- [x] **`about.html:190`** — "Magic in Bali" image link points to `http://eddiegoldsteinmagic.com/bali-video/` (external WP page that no longer applies); should link to `resources.html`

### External Images (WP Uploads) — Should Be Local

**Logo (spacer.png)** — present on every page:
- [x] `about.html` `contact.html` `home.html` `index.html` `poi.html` `resources.html` `shows.html` — logo `src` points to `http://eddiegoldsteinmagic.com/wp-content/uploads/2014/04/spacer.png` *(logo_container div removed entirely from all pages)*

**MadHatter Banner** — present on every page except `index.html`:
- [x] `about.html` `contact.html` `poi.html` `resources.html` `shows.html` — replaced with `images/hero-image.jpg`

**About page biography photos** — all images and their wrapping `<a href>` links are external:
- [x] `about.html` — all 11 biography images replaced with local `images/about-*.jpg` files

### External Links in CSS

- [x] **`css/styles.css:1459`** — Divi preloader GIF replaced with `background: none`
- [ ] **`css/styles.css` (lines 9–397)** — 40+ `@font-face` declarations load from `https://fonts.gstatic.com`; fonts could be self-hosted if offline/fast-load behavior is needed

---

## eddiegoldstein/

### External Images — Should Be Local

**Logo** — present on every page:
- [x] All pages — `logo_container` div removed entirely; logo was already hidden via CSS

**CSS wood-plank background:**
- [x] **`css/styles.css:11`** — updated to `url("../images/wood-bg.jpg")`

### Broken Contact Form (contact.html)

- [ ] **`contact.html`** — still contains 1 WP plugin reference (CAPTCHA iframe from `https://eddiegoldstein.com/wp-content/plugins/contact-form-manager/...`); form has no backend action so submissions go nowhere — replace with a working solution (e.g., mailto link, Formspree, or similar)

### External Font Loads

- [ ] **All pages** — Google Fonts CSS linked from `https://fonts.googleapis.com/css?family=Open+Sans:...`; fonts could be self-hosted if needed

### Nav Link

- [ ] **All pages** — "The Other Me" nav item links to `http://www.EddieGoldsteinMagic.com` (HTTP, not HTTPS); verify correct URL and consider upgrading to `https://`
