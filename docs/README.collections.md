# README.collections.md — Project Collections & Resources

> **Dokument:** Kolekcje zasobów, linki, biblioteki i referencje projektu  
> **Projekt:** `piotroq/alubram-gmbh-wordpress` — ALUBRAM GMBH  
> **Wersja:** 1.0.0 | 2026-02-26  

---

## 1. Przegląd Kolekcji

Dokument agreguje wszystkie zewnętrzne zasoby, biblioteki, zdjęcia, fonty, narzędzia i referencje używane lub rekomendowane w projekcie. Każda kolekcja zawiera URL, opis i sposób użycia w projekcie.

---

## 2. Kolekcja: Dokumentacja Techniczna

### 2.1 WordPress & PHP

| Zasób | URL | Zastosowanie |
|-------|-----|-------------|
| WordPress Developer Docs | https://developer.wordpress.org/ | Główna dokumentacja WP API |
| WordPress Documentation | https://wordpress.org/documentation/ | User-facing docs, plugin info |
| WP Coding Standards | https://developer.wordpress.org/coding-standards/ | PHP/CSS/JS style guide |
| WP REST API | https://developer.wordpress.org/rest-api/ | REST endpoints |
| WP Hooks Reference | https://developer.wordpress.org/reference/hooks/ | `add_action`, `add_filter` |
| WP Functions Reference | https://developer.wordpress.org/reference/functions/ | Wszystkie WP functions |
| WP Theme Handbook | https://developer.wordpress.org/themes/ | Theme development guide |
| WP Plugin Handbook | https://developer.wordpress.org/plugins/ | Plugin development |
| ACF Documentation | https://www.advancedcustomfields.com/resources/ | ACF Pro fields, repeaters |
| PHP 8.2 Manual | https://www.php.net/manual/en/ | PHP language reference |
| PHP-CS-Fixer | https://cs.symfony.com/ | PSR-12 auto-fixer |
| PHPUnit | https://phpunit.de/ | Unit testing PHP |

### 2.2 Frontend & CSS

| Zasób | URL | Zastosowanie |
|-------|-----|-------------|
| Tailwind CSS Docs | https://tailwindcss.com/docs | Utility classes reference |
| Tailwind Play CDN | https://play.tailwindcss.com/ | Szybki prototyping |
| Tailwind Components | https://tailwindui.com/ | Premium UI components |
| Tailwind GitHub | https://github.com/tailwindlabs/tailwindcss | Source + changelog |
| MDN CSS Reference | https://developer.mozilla.org/en-US/docs/Web/CSS | CSS properties |
| CSS Tricks | https://css-tricks.com/ | Patterns, guides |
| Can I Use | https://caniuse.com/ | Browser compatibility |

### 2.3 TypeScript & JavaScript

| Zasób | URL | Zastosowanie |
|-------|-----|-------------|
| TypeScript Docs | https://www.typescriptlang.org/docs/ | TS language reference |
| TypeScript Playground | https://www.typescriptlang.org/play | Quick TS testing |
| MDN JavaScript | https://developer.mozilla.org/en-US/docs/Web/JavaScript | JS reference |
| ESLint Docs | https://eslint.org/docs/ | Linting configuration |

---

## 3. Kolekcja: UI Libraries

### 3.1 Animation — AOS (Animate On Scroll)

| Zasób | URL |
|-------|-----|
| Oficjalna strona | https://michalsnik.github.io/aos/ |
| GitHub Repository | https://github.com/michalsnik/aos |
| npm | https://www.npmjs.com/package/aos |
| CDN (jsDelivr CSS) | `https://cdn.jsdelivr.net/npm/aos@2.3.4/dist/aos.css` |
| CDN (jsDelivr JS) | `https://cdn.jsdelivr.net/npm/aos@2.3.4/dist/aos.js` |

**Implementacja w projekcie:**

```html
<!-- W <head> -->
<link rel="stylesheet"
      href="https://cdn.jsdelivr.net/npm/aos@2.3.4/dist/aos.css"
      media="print" onload="this.media='all'">

<!-- Przed </body> -->
<script src="https://cdn.jsdelivr.net/npm/aos@2.3.4/dist/aos.js" defer></script>
```

**AOS atrybuty używane w projekcie:**

```
data-aos="fade-up"          → sekcje, nagłówki
data-aos="fade-right"       → content (lewa strona)
data-aos="fade-left"        → obrazy (prawa strona)
data-aos="fade-down"        → hero eyebrow
data-aos="zoom-in-up"       → karty produktów
data-aos="zoom-in"          → ikony, badges
data-aos-delay="0|100|200|300|400"
data-aos-duration="600|800|1000|1200"
data-aos-easing="ease-in-out-cubic"
data-aos-once="true"        → zawsze (animacja tylko raz)
```

### 3.2 Slider — Swiper.js

| Zasób | URL |
|-------|-----|
| Oficjalna strona | https://swiperjs.com/ |
| GitHub Repository | https://github.com/nolimits4web/swiper |
| Dokumentacja API | https://swiperjs.com/swiper-api |
| CDN CSS | `https://cdn.jsdelivr.net/npm/swiper@11/swiper-bundle.min.css` |
| CDN JS | `https://cdn.jsdelivr.net/npm/swiper@11/swiper-bundle.min.js` |

**Konfiguracje Swiper w projekcie:**

```typescript
// Galeria produktów (product detail)
const productGallery = new Swiper('.alubram-product-gallery', {
  slidesPerView: 1,
  spaceBetween: 16,
  loop: true,
  thumbs: { swiper: productThumbsSwiper },
  pagination: { el: '.swiper-pagination', clickable: true },
  navigation: { nextEl: '.swiper-button-next', prevEl: '.swiper-button-prev' },
});

// Testimonials slider
const testimonials = new Swiper('.alubram-testimonials-swiper', {
  slidesPerView: 1,
  spaceBetween: 24,
  autoplay: { delay: 5000, disableOnInteraction: false },
  loop: true,
  breakpoints: {
    768: { slidesPerView: 2 },
    1024: { slidesPerView: 3 },
  },
  pagination: { el: '.swiper-pagination', clickable: true },
});

// Referenzen gallery
const referenzenSwiper = new Swiper('.alubram-referenzen-swiper', {
  slidesPerView: 1,
  spaceBetween: 20,
  loop: true,
  breakpoints: {
    640: { slidesPerView: 2 },
    1024: { slidesPerView: 3 },
  },
});
```

### 3.3 Icons — Material Design Icons (Google)

| Zasób | URL |
|-------|-----|
| Oficjalna strona | https://fonts.google.com/icons |
| GitHub Repository | https://github.com/google/material-design-icons |
| Icon Search | https://fonts.google.com/icons?icon.style=Outlined |
| CDN Import | Google Fonts CSS2 API |

**Implementacja:**

```html
<!-- Preload + import -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link rel="stylesheet"
      href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:opsz,wght,FILL,GRAD@20..48,100..700,0..1,-50..200"
      media="print" onload="this.media='all'">
```

**Konfiguracja wariantów:**

```css
/* Filled icons dla aktywnych stanów */
.material-symbols-outlined.icon-filled {
  font-variation-settings: 'FILL' 1, 'wght' 400, 'GRAD' 0, 'opsz' 24;
}

/* Ikony w nagłówkach (większe, lighter) */
.alubram-section-header .material-symbols-outlined {
  font-size: 48px;
  font-variation-settings: 'FILL' 0, 'wght' 300, 'GRAD' 0, 'opsz' 48;
  color: var(--color-accent);
}

/* Ikony w USP (średnie) */
.alubram-usp__icon .material-symbols-outlined {
  font-size: 32px;
  font-variation-settings: 'FILL' 0, 'wght' 400, 'GRAD' 0, 'opsz' 32;
}

/* Ikony inline (małe) */
.alubram-btn .material-symbols-outlined,
.alubram-breadcrumbs .material-symbols-outlined {
  font-size: 18px;
  font-variation-settings: 'FILL' 0, 'wght' 400, 'GRAD' 0, 'opsz' 20;
}
```

---

## 4. Kolekcja: Google Fonts

### 4.1 Używane kroje pisma

| Font | Wagi | Zastosowanie | Import String |
|------|------|-------------|--------------|
| **Montserrat** | 400, 500, 600, 700, 800, 900 | Headings (H1–H4), wordmark | `Montserrat:ital,wght@0,400;0,600;0,700;0,800;0,900` |
| **Inter** | 300, 400, 500, 600, 700 | Body text, UI elements | `Inter:wght@300;400;500;600;700` |
| **Playfair Display** | 400, 700 (+ italic) | Accent quotes, premium text | `Playfair+Display:ital,wght@0,400;0,700;1,400` |

**Google Fonts URL (production — pojedynczy request):**

```
https://fonts.googleapis.com/css2?
  family=Inter:wght@300;400;500;600;700&
  family=Montserrat:ital,wght@0,400;0,500;0,600;0,700;0,800;0,900;1,400&
  family=Playfair+Display:ital,wght@0,400;0,700;1,400&
  display=swap
```

### 4.2 Lokalne hostowanie (DSGVO compliance)

Narzędzie do pobrania fontów lokalnie:

```
https://google-webfonts-helper.herokuapp.com/fonts
```

**Lokalizacja w motywie:**

```
alubramat-child/
└── assets/
    └── fonts/
        ├── montserrat/
        │   ├── montserrat-v26-latin-700.woff2
        │   ├── montserrat-v26-latin-800.woff2
        │   └── ...
        ├── inter/
        │   ├── inter-v13-latin-regular.woff2
        │   └── ...
        └── playfair-display/
            ├── playfair-display-v37-latin-regular.woff2
            └── ...
```

**CSS @font-face (lokalne fonty):**

```css
/* Montserrat 700 */
@font-face {
  font-family: 'Montserrat';
  font-style: normal;
  font-weight: 700;
  font-display: swap;
  src: local('Montserrat Bold'),
       url('../fonts/montserrat/montserrat-v26-latin-700.woff2') format('woff2');
}

/* Inter Regular */
@font-face {
  font-family: 'Inter';
  font-style: normal;
  font-weight: 400;
  font-display: swap;
  src: local('Inter'),
       url('../fonts/inter/inter-v13-latin-regular.woff2') format('woff2');
}
```

---

## 5. Kolekcja: Zdjęcia (Unsplash)

### 5.1 Rekomendowane kategorie i query strings

| Kategoria | Unsplash Query | Opis |
|-----------|---------------|------|
| Hero Homepage | `modern aluminum fence architecture` | Ogrodzenie na tle nowoczesnego domu |
| Hero Homepage (alt) | `luxury villa gate entrance modern` | Elegancka brama wjazdowa |
| Zäune & Zaunfelder | `metal fence modern minimalist garden` | Minimalistyczne ogrodzenie |
| Tore / Einfahrtstore | `automatic gate driveway modern home` | Brama wjazdowa automatyczna |
| Carports | `carport modern house architecture` | Wiata garażowa nowoczesna |
| Überdachungen | `patio pergola modern outdoor living` | Taras z zadaszeniem |
| Über uns | `metalwork factory workshop precision` | Hala produkcyjna metal |
| Team | `professional team industrial setting` | Profesjonalny team |
| Galerie (realizacje) | `modern house garden fence landscaping` | Dom z ogrodem i ogrodzeniem |
| Blog / Ratgeber | `home renovation planning architect` | Planowanie remontu |

### 5.2 Unsplash API URL format

```html
<!-- Format URL Unsplash (direct embed) -->
https://images.unsplash.com/photo-{PHOTO_ID}?
  w=1200         ← szerokość px
  &h=800         ← wysokość px (opcjonalne)
  &q=80          ← jakość 1-100
  &auto=format   ← auto WebP/AVIF
  &fit=crop      ← kadrowanie
  &crop=entropy  ← smart crop (entropia)

<!-- Przykład: -->
https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=1200&q=80&auto=format&fit=crop
```

### 5.3 Rekomendowane ID zdjęć (wstępna selekcja)

```
Nowoczesne ogrodzenia / bramy:
  photo-1558618666-fcd25c85cd64  → metalowe ogrodzenie minimalistyczne
  photo-1584184924103-e310d9dc82fc → brama wjazdowa luxury

Domy / architektura:
  photo-1564013799919-ab600027ffc6  → modern house garden
  photo-1600596542815-ffad4c1539a9  → luxury villa entrance
  photo-1568605114967-8130f3a36994  → modern house architecture

Metalwork / manufacturing:
  photo-1504917595217-d4dc5ebe6122  → metal manufacturing
  photo-1581091226825-a6a2a5aee158  → industrial workshop

Carport / pergola:
  photo-1570129477492-45c003edd2be  → carport modern
  photo-1416879595882-3373a0480b5b  → patio outdoor
```

> **Uwaga:** Zawsze weryfikuj zdjęcia przed użyciem produkcyjnym. Sprawdź licencję Unsplash dla użytku komercyjnego.

### 5.4 HTML Pattern — responsywny obraz

```html
<picture>
  <source
    type="image/avif"
    srcset="https://images.unsplash.com/photo-{ID}?w=400&q=80&auto=format&fm=avif 400w,
            https://images.unsplash.com/photo-{ID}?w=800&q=80&auto=format&fm=avif 800w,
            https://images.unsplash.com/photo-{ID}?w=1200&q=80&auto=format&fm=avif 1200w,
            https://images.unsplash.com/photo-{ID}?w=1920&q=80&auto=format&fm=avif 1920w"
    sizes="(max-width: 640px) 100vw, (max-width: 1024px) 50vw, 33vw">

  <source
    type="image/webp"
    srcset="https://images.unsplash.com/photo-{ID}?w=400&q=80&auto=format&fm=webp 400w,
            https://images.unsplash.com/photo-{ID}?w=800&q=80&auto=format&fm=webp 800w,
            https://images.unsplash.com/photo-{ID}?w=1200&q=80&auto=format&fm=webp 1200w"
    sizes="(max-width: 640px) 100vw, (max-width: 1024px) 50vw, 33vw">

  <img
    src="https://images.unsplash.com/photo-{ID}?w=1200&q=80&auto=format&fit=crop"
    srcset="https://images.unsplash.com/photo-{ID}?w=400&q=80 400w,
            https://images.unsplash.com/photo-{ID}?w=800&q=80 800w,
            https://images.unsplash.com/photo-{ID}?w=1200&q=80 1200w"
    sizes="(max-width: 640px) 100vw, (max-width: 1024px) 50vw, 33vw"
    alt="[OPISOWY ALT PO NIEMIECKU]"
    loading="lazy"
    decoding="async"
    width="1200"
    height="800">
</picture>
```

---

## 6. Kolekcja: Design Inspiracje

### 6.1 Strony referencyjne

| Strona | URL | Element do inspiracji |
|--------|-----|----------------------|
| **Arrea.at** | https://arrea.at/ | Autoplay video w sekcjach, dynamika hero, typografia |
| **Selt.com** | https://www.selt.com/home-de | Premium menu design, sekcje produktów, fonts |
| **MB Veranda** | https://mbveranda.de/ | Ogólny wygląd wizualny, sekcje produktów |

### 6.2 Elementy do zaczerpnięcia

**Z arrea.at:**
- Fullscreen hero z autoplay background video
- Płynne przejścia między sekcjami (smooth scroll + parallax)
- Mega menu z podglądem produktów
- Dynamiczne typograficzne animacje

**Z selt.com/home-de:**
- Sticky header z eleganckim przejściem transparent→solid
- Typografia: duże litery + fine details
- Sekcja produktów z hover reveal
- Minimalistyczna layout structure

**Z mbveranda.de:**
- Sekcja „Warum wir" z ikonami
- Proces krok po kroku (Beratung→Montage)
- Galeria realizacji masonry grid
- Footer z pełną informacją o firmie

---

## 7. Kolekcja: SEO & Performance Tools

### 7.1 SEO Tools

| Narzędzie | URL | Zastosowanie |
|-----------|-----|-------------|
| PageSpeed Insights | https://pagespeed.web.dev/ | Core Web Vitals, LCP/CLS/INP |
| Google Search Console | https://search.google.com/search-console | Indeksowanie, klikalność |
| Lighthouse (Chrome) | DevTools → Lighthouse | Audit SEO, Accessibility, Perf |
| Schema.org Validator | https://validator.schema.org/ | Test JSON-LD markup |
| Rich Results Test | https://search.google.com/test/rich-results | Test structured data |
| SEMrush | https://www.semrush.com/ | Keyword research DE/AT |
| Ahrefs | https://ahrefs.com/ | Backlinks, keyword difficulty |
| Screaming Frog | https://www.screamingfrog.co.uk/ | Site crawl, broken links |

### 7.2 Performance Tools

| Narzędzie | URL | Zastosowanie |
|-----------|-----|-------------|
| WebPageTest | https://www.webpagetest.org/ | Detailed performance waterfall |
| GTmetrix | https://gtmetrix.com/ | Performance scoring |
| Chrome DevTools | DevTools → Performance | JS profiling, rendering |
| Squoosh | https://squoosh.app/ | Image optimization (AVIF/WebP) |
| ImageOptim | https://imageoptim.com/ | Bulk image compression |
| Cloudinary | https://cloudinary.com/ | Cloud image CDN + optimization |

### 7.3 Accessibility Tools

| Narzędzie | URL | Zastosowanie |
|-----------|-----|-------------|
| axe DevTools | https://www.deque.com/axe/ | WCAG 2.1 automated testing |
| WAVE | https://wave.webaim.org/ | Visual accessibility feedback |
| Contrast Checker | https://webaim.org/resources/contrastchecker/ | Color contrast WCAG |
| Screen Reader | NVDA / VoiceOver | Manual accessibility test |

---

## 8. Kolekcja: Schema.org References

| Schema Type | URL | Zastosowanie w projekcie |
|-------------|-----|-------------------------|
| LocalBusiness | https://schema.org/LocalBusiness | Homepage, kontakt |
| Manufacturer | https://schema.org/Manufacturer | Homepage (extends LocalBusiness) |
| Product | https://schema.org/Product | Strony produktów CPT |
| BreadcrumbList | https://schema.org/BreadcrumbList | Breadcrumbs na wszystkich stronach |
| FAQPage | https://schema.org/FAQPage | Sekcja FAQ na stronach produktów |
| Organization | https://schema.org/Organization | Homepage footer |
| PostalAddress | https://schema.org/PostalAddress | Dane adresowe (w LocalBusiness) |
| ImageObject | https://schema.org/ImageObject | Zdjęcia produktów |
| AggregateRating | https://schema.org/AggregateRating | Opinie klientów (jeśli wystarczająco dużo) |
| OfferCatalog | https://schema.org/OfferCatalog | Katalog produktów |
| BlogPosting | https://schema.org/BlogPosting | Artykuły na blogu Ratgeber |

---

## 9. Kolekcja: WordPress Plugins

### 9.1 Wymagane (required)

| Plugin | Wersja | URL | Opis |
|--------|--------|-----|------|
| Yoast SEO | ≥ 22.x | https://yoast.com/wordpress/plugins/seo/ | SEO meta, schema, sitemap |
| Contact Form 7 | ≥ 5.9 | https://contactform7.com/ | Formularze kontaktowe |
| WP Rocket | ≥ 3.16 | https://wp-rocket.me/ | Cache + performance (premium) |
| Imagify | ≥ 2.2 | https://imagify.io/ | AVIF/WebP + kompresja |
| Borlabs Cookie | ≥ 3.x | https://borlabs.io/borlabs-cookie/ | DSGVO Cookie Banner |
| Advanced Custom Fields Pro | ≥ 6.3 | https://www.advancedcustomfields.com/ | Meta pola CPT (premium) |
| Classic Editor | ≥ 1.6 | https://wordpress.org/plugins/classic-editor/ | Klasyczny edytor |

### 9.2 Opcjonalne

| Plugin | URL | Opis |
|--------|-----|------|
| Polylang | https://polylang.pro/ | Wielojęzyczność |
| WP Fastest Cache | https://www.wpfastestcache.com/ | Darmowy cache (alt. WP Rocket) |
| Redis Object Cache | https://wordpress.org/plugins/redis-cache/ | Redis integration |
| Gravity Forms | https://www.gravityforms.com/ | Zaawansowane formularze |
| RankMath | https://rankmath.com/ | Alt. dla Yoast SEO |
| WooCommerce | https://woocommerce.com/ | Sklep (konfigurator, zamówienia) |

---

## 10. Kolekcja: Development Tools

### 10.1 Local Development

| Narzędzie | URL | Zastosowanie |
|-----------|-----|-------------|
| wp-env | https://developer.wordpress.org/block-editor/reference-guides/packages/packages-env/ | WP lokalne środowisko |
| XAMPP | https://www.apachefriends.org/ | Apache + MySQL + PHP |
| Vite | https://vitejs.dev/ | Build tool dla TS/CSS |
| esbuild | https://esbuild.github.io/ | Ultra-fast JS/TS bundler |
| PHP_CodeSniffer | https://github.com/squizlabs/PHP_CodeSniffer | PSR-12 linting |
| PHPUnit | https://phpunit.de/ | PHP unit testing |
| Jest | https://jestjs.io/ | JS/TS testing |

### 10.2 VS Code Extensions (recommended)

```json
{
  "recommendations": [
    "bmewburn.vscode-intelephense-client",
    "bradlc.vscode-tailwindcss",
    "esbenp.prettier-vscode",
    "ms-vscode.vscode-typescript-next",
    "neilbrayfield.php-docblocker",
    "kokororin.vscode-phpfmt",
    "vitest.explorer",
    "usernamehw.errorlens",
    "eamodio.gitlens"
  ]
}
```

---

## 11. Kolekcja: Colory RAL (aluminium produkty)

Standardowe kolory RAL dostępne dla produktów ALUBRAM (pulverbeschichtet):

| Kolor | RAL | HEX (przybliżony) | Nazwa DE |
|-------|-----|------------------|----------|
| Anthrazitgrau | RAL 7016 | `#293133` | Anthrazitgrau — bestseller |
| Schwarzgrau | RAL 7021 | `#2D3235` | Schwarzgrau |
| Tiefschwarz | RAL 9005 | `#0A0A0A` | Tiefschwarz |
| Reinweiß | RAL 9010 | `#F4F4F4` | Reinweiß |
| Weißaluminium | RAL 9006 | `#A5A5A5` | Weißaluminium / Silber |
| Goldmetallic | RAL 9007 | `#8E8279` | Graualuminium |
| Bronzemetallic | RAL 8017 | `#44292B` | Schokoladenbraun |
| Moosgrün | RAL 6005 | `#2F4538` | Moosgrün |
| Basaltgrau | RAL 7012 | `#4D5457` | Basaltgrau |
| DB 703 (Deutsche Bahn) | DB 703 | `#605C4E` | Eisenglimmer |

> Pełna lista kolorów RAL: https://www.ralcolorchart.com/ral-classic

---

## 12. Kolekcja: Pliki konfiguracyjne projektu

### 12.1 `.gitignore` — co ignorujemy

```gitignore
# WordPress core (nie commitujemy core WP)
/wp-admin/
/wp-includes/
/wp-*.php
/index.php
/xmlrpc.php
/license.txt
/readme.html

# WordPress uploads (media)
/wp-content/uploads/

# Config z danymi dostępowymi
wp-config.php
.env
.env.local

# Build outputs
/src/alubramat-child/assets/js/custom/*.min.js
/src/alubramat-child/assets/css/tailwind.min.css

# Node / Composer
node_modules/
vendor/

# IDE
.idea/
.vscode/settings.json
*.code-workspace

# OS
.DS_Store
Thumbs.db
```

### 12.2 `package.json` — scripts

```json
{
  "name": "alubram-gmbh-wordpress",
  "version": "1.0.0",
  "private": true,
  "scripts": {
    "build": "tsc && npm run css:build",
    "watch": "tsc --watch",
    "css:build": "tailwindcss -i ./src/alubramat-child/style.css -o ./src/alubramat-child/assets/css/tailwind.min.css --minify",
    "css:watch": "tailwindcss -i ./src/alubramat-child/style.css -o ./src/alubramat-child/assets/css/tailwind.min.css --watch",
    "lint": "eslint ./src/alubramat-child/assets/ts/**/*.ts",
    "lint:fix": "eslint ./src/alubramat-child/assets/ts/**/*.ts --fix",
    "test": "jest"
  },
  "devDependencies": {
    "typescript": "^5.4.0",
    "tailwindcss": "^3.4.0",
    "@types/aos": "^3.0.7",
    "eslint": "^8.57.0",
    "@typescript-eslint/eslint-plugin": "^7.0.0",
    "@typescript-eslint/parser": "^7.0.0",
    "jest": "^29.0.0",
    "ts-jest": "^29.0.0"
  }
}
```

---

## 13. Kolekcja: Kontakty i Dostępy

| Zasób | Dane |
|-------|------|
| **Klient** | Herr Szpak Irek — ALUBRAM GMBH |
| **Email (główny)** | himberg@alubram.at |
| **Email (Wien)** | wien@alubram.at |
| **Tel 1** | +43 (0) 223 584 793 |
| **Tel 2** | +43 664 437 3954 |
| **Adres** | Hintere Ortsstraße 31, 2325 Himberg bei Wien, AT |
| **Strona prod.** | https://alubram.at |
| **GitHub Repo** | https://github.com/piotroq/alubram-gmbh-wordpress |

> ⚠️ Dane dostępowe do serwera (FTP/SSH, WP-Admin, DB) przechowywać wyłącznie w `.env` lub menedżerze haseł — **NIGDY w repozytorium**.

---

## 14. Changelog Collections

| Wersja | Data | Zmiana |
|--------|------|--------|
| 1.0.0 | 2026-02-26 | Inicjalna wersja — wszystkie kolekcje zebrane |

---

*README.collections.md — ALUBRAM GMBH WordPress Project | v1.0.0 | 2026-02-26*  
*Repozytorium: piotroq/alubram-gmbh-wordpress*
