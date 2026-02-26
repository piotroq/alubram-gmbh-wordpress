# ARCHITECTURE.md — ALUBRAM GMBH WordPress Project

> **Dokument:** Architektura techniczna projektu  
> **Repozytorium:** `piotroq/alubram-gmbh-wordpress`  
> **Stack:** WordPress 6.9 · PHP 8.2+ · Tailwind CSS · TypeScript  
> **Środowisko produkcyjne:** https://alubram.at  
> **Wersja dokumentu:** 1.0.0 | 2026-02-26  

---

## 1. Przegląd Architektury

```
┌─────────────────────────────────────────────────────────────────────┐
│                         BROWSER / CLIENT                            │
│            HTML5 · CSS3 · ES6+ TypeScript · AOS · Swiper            │
└──────────────────────┬──────────────────────────────────────────────┘
                       │ HTTPS / HTTP/2
┌──────────────────────▼──────────────────────────────────────────────┐
│                  CDN / Reverse Proxy Layer                          │
│              Cloudflare (cache, WAF, DDOS, SSL)                     │
└──────────────────────┬──────────────────────────────────────────────┘
                       │
┌──────────────────────▼──────────────────────────────────────────────┐
│                    Web Server (Apache / Nginx)                      │
│               PHP 8.2 FPM · OPcache · mod_expires                  │
└──────────────────────┬──────────────────────────────────────────────┘
                       │
┌──────────────────────▼──────────────────────────────────────────────┐
│                      WordPress 6.9 Core                             │
│   Theme: alubramat (parent) + alubramat-child (active)             │
│   Plugins: Yoast SEO · CF7 · WP Rocket · ACF Pro · Borlabs         │
└──────────────────────┬──────────────────────────────────────────────┘
                       │
┌──────────────────────▼──────────────────────────────────────────────┐
│                    Database Layer                                   │
│          MySQL 8.0 / MariaDB 10.6 — WordPress Schema               │
│          Redis Object Cache (opcjonalnie dla performance)           │
└─────────────────────────────────────────────────────────────────────┘
```

---

## 2. Struktura Repozytorium

```
alubram-gmbh-wordpress/
│
├── .claude/                          ← Konfiguracja Claude AI agentów
│   └── agents/
│       └── ...
│
├── .cursorrules/                     ← Reguły Cursor AI IDE
│
├── .github/
│   ├── workflows/
│   │   ├── deploy.yml                ← CI/CD deploy do serwera
│   │   ├── lint.yml                  ← PHP_CodeSniffer + ESLint
│   │   └── tests.yml                 ← PHPUnit + Jest
│   └── PULL_REQUEST_TEMPLATE.md
│
├── src/                              ← Główny katalog źródeł motywu
│   ├── alubramat/                    ← Motyw PARENT (bazowy blank)
│   │   ├── style.css
│   │   ├── functions.php
│   │   └── index.php
│   │
│   └── alubramat-child/              ← Motyw CHILD (AKTYWNY — tutaj kod)
│       ├── style.css                 ← CSS variables + brand imports
│       ├── functions.php             ← Bootstrap includes + hooks
│       ├── front-page.php            ← Homepage template
│       ├── page.php                  ← Generic page template
│       ├── single.php                ← Blog single post
│       ├── archive.php               ← Blog archive
│       ├── header.php                ← Site header + nav
│       ├── footer.php                ← Site footer + scripts
│       ├── 404.php                   ← Error page
│       ├── search.php                ← Search results
│       │
│       ├── page-templates/
│       │   ├── page-uber-uns.php     ← Über uns
│       │   ├── page-produkte.php     ← Produktübersicht
│       │   ├── page-referenzen.php   ← Galerie / Referenzen
│       │   ├── page-leistungen.php   ← Leistungen
│       │   └── page-kontakt.php      ← Kontakt + Google Maps
│       │
│       ├── template-parts/
│       │   ├── sections/             ← Wielokrotnie używane sekcje
│       │   │   ├── hero-homepage.php
│       │   │   ├── section-usps.php
│       │   │   ├── section-products-grid.php
│       │   │   ├── section-why-us.php
│       │   │   ├── section-process.php
│       │   │   ├── section-testimonials.php
│       │   │   ├── section-gallery.php
│       │   │   ├── section-stats-counter.php
│       │   │   ├── section-cta-banner.php
│       │   │   ├── section-faq.php
│       │   │   └── section-contact-form.php
│       │   │
│       │   ├── components/           ← Atomowe komponenty UI
│       │   │   ├── breadcrumbs.php
│       │   │   ├── product-card.php
│       │   │   ├── cta-button.php
│       │   │   └── pagination.php
│       │   │
│       │   └── global/
│       │       ├── header-nav.php
│       │       └── footer-widgets.php
│       │
│       ├── inc/                      ← PHP logic includes
│       │   ├── custom-post-types.php ← CPT: alubram_product, alubram_reference, alubram_testimonial
│       │   ├── taxonomies.php        ← Taxonomie dla CPT
│       │   ├── meta-boxes.php        ← ACF/custom meta boxes
│       │   ├── schema-markup.php     ← JSON-LD generator functions
│       │   ├── enqueue.php           ← wp_enqueue_scripts/styles
│       │   ├── nav-menus.php         ← Rejestracja menu + logo support
│       │   ├── widgets.php           ← Sidebar/footer widgets
│       │   ├── shortcodes.php        ← [alubram_*] shortcodes
│       │   └── ajax-handlers.php     ← AJAX endpoints (formularz, konfigurator)
│       │
│       ├── assets/
│       │   ├── css/
│       │   │   ├── tailwind.min.css
│       │   │   ├── aos.min.css
│       │   │   ├── swiper.min.css
│       │   │   └── custom/
│       │   │       ├── components.css
│       │   │       ├── animations.css
│       │   │       └── responsive.css
│       │   │
│       │   ├── js/
│       │   │   ├── aos.min.js
│       │   │   ├── swiper.min.js
│       │   │   └── custom/
│       │   │       ├── main.ts       ← Entry point TypeScript
│       │   │       ├── animations.ts
│       │   │       ├── counter.ts
│       │   │       └── forms.ts
│       │   │
│       │   └── images/               ← Logo, icons, patterns, og-image
│       │
│       └── languages/
│           ├── de_AT.po
│           └── de_AT.mo
│
├── .gitignore
├── .gitattributes
├── README.md
├── TECHNICAL-SHEETS.md
├── ARCHITECTURE.md                   ← Ten plik
├── BRAND-SETTINGS.md
├── DESIGN-SYSTEM.md
├── README.agents.md
├── README.collections.md
└── analiza-elementów-logo-alubram.md
```

---

## 3. WordPress Theme Architecture

### 3.1 Parent Theme — `alubramat`

Minimalny blank theme. Jego jedyną rolą jest dostarczenie punktu bazowego dla motywu potomnego.

```php
// alubramat/style.css
/*
 * Theme Name: Alubramat
 * Theme URI: https://alubram.at
 * Author: Piotroq Dev
 * Version: 1.0.0
 * License: Proprietary
 */
```

### 3.2 Child Theme — `alubramat-child` (AKTYWNY)

Wszystkie customizacje, templates i assety są tutaj. Parent nigdy nie jest modyfikowany.

```php
// alubramat-child/style.css
/*
 * Theme Name: Alubramat Child
 * Template: alubramat
 * Version: 1.0.0
 */
```

### 3.3 Hierarchia ładowania functions.php

```
WordPress → alubramat/functions.php (parent, minimal)
         → alubramat-child/functions.php
              ├── require_once 'inc/enqueue.php'
              ├── require_once 'inc/custom-post-types.php'
              ├── require_once 'inc/taxonomies.php'
              ├── require_once 'inc/meta-boxes.php'
              ├── require_once 'inc/nav-menus.php'
              ├── require_once 'inc/schema-markup.php'
              ├── require_once 'inc/shortcodes.php'
              ├── require_once 'inc/widgets.php'
              └── require_once 'inc/ajax-handlers.php'
```

---

## 4. Custom Post Types (CPT)

### 4.1 `alubram_product` — Produkte

```php
// Rejestracja: inc/custom-post-types.php
register_post_type('alubram_product', [
    'labels'      => [...],        // DE labels
    'public'      => true,
    'has_archive' => true,
    'rewrite'     => ['slug' => 'produkte'],
    'supports'    => ['title', 'editor', 'thumbnail', 'excerpt', 'custom-fields'],
    'menu_icon'   => 'dashicons-admin-generic',
    'show_in_rest'=> true,         // Gutenberg support
]);
```

**Meta pola (ACF Pro / custom meta-boxes):**

| Klucz | Typ | Opis |
|-------|-----|------|
| `_product_category` | select | Zäune / Tore / Carports / Überdachungen |
| `_product_material` | text | Aluminium, Stahl (domyślnie Aluminium) |
| `_delivery_time` | text | „3–6 Wochen" |
| `_warranty_years` | number | Lata gwarancji |
| `_price_from` | number | Cena od (EUR) |
| `_gallery_images` | gallery | ID załączników WP |
| `_technical_specs` | repeater | Tabela spec. technicznych |
| `_colors_available` | checkbox | Lista dostępnych kolorów RAL |

**Taxonomie:**
- `product_category` (hierarchiczna, jak category)
- `product_material`
- `product_color`

### 4.2 `alubram_reference` — Referenzen

**Meta pola:**

| Klucz | Typ | Opis |
|-------|-----|------|
| `_ref_location` | text | Lokalizacja realizacji (miasto, kraj) |
| `_ref_product_type` | select | Typ produktu |
| `_ref_year` | number | Rok realizacji |
| `_ref_gallery` | gallery | Zdjęcia realizacji |
| `_ref_client_name` | text | Opcjonalnie (anonimizowany) |

### 4.3 `alubram_testimonial` — Kundenmeinungen

**Meta pola:**

| Klucz | Typ | Opis |
|-------|-----|------|
| `_client_name` | text | Imię i nazwisko |
| `_client_location` | text | Miasto |
| `_rating` | number | Ocena 1–5 |
| `_review_text` | textarea | Treść opinii |
| `_product_purchased` | select | Produkt |

---

## 5. Template Hierarchy

```
Request URL                    → Template File
────────────────────────────────────────────────────────
/                              → front-page.php
/uber-uns/                     → page-templates/page-uber-uns.php
/produkte/                     → page-templates/page-produkte.php
/produkte/zaune-zaunfelder/    → taxonomy-product_category.php
/produkte/{slug}/              → single-alubram_product.php
/referenzen/                   → page-templates/page-referenzen.php
/leistungen/                   → page-templates/page-leistungen.php
/kontakt/                      → page-templates/page-kontakt.php
/ratgeber/                     → archive.php (post type: post)
/ratgeber/{slug}/              → single.php
/impressum/                    → page.php
/datenschutzerklarung/         → page.php
/agb/                          → page.php
404                            → 404.php
?s={query}                     → search.php
```

---

## 6. Asset Pipeline

### 6.1 CSS Pipeline

```
External CDN (Google Fonts, Material Icons)
    ↓ (DSGVO: lokalnie hostowane Google Fonts)
assets/css/tailwind.min.css     ← Tailwind Play CDN lub build
assets/css/aos.min.css          ← AOS v2
assets/css/swiper.min.css       ← Swiper.js
style.css (child theme)         ← :root variables + brand
assets/css/custom/components.css
assets/css/custom/animations.css
assets/css/custom/responsive.css
```

**Enqueue kolejność (priorytet):**
1. Google Fonts preconnect (`priority: 1` w `wp_head`)
2. Material Icons stylesheet
3. Tailwind CSS
4. AOS CSS
5. Swiper CSS
6. Child theme `style.css` (brand variables)
7. `components.css`
8. `animations.css`
9. `responsive.css`

### 6.2 JavaScript Pipeline

```
TypeScript źródła (assets/js/custom/*.ts)
    ↓ tsc / esbuild (build)
assets/js/custom/*.min.js (output)

Kolejność ładowania:
1. aos.min.js           (defer)
2. swiper.min.js        (defer)
3. main.min.js          (defer) — AOS.init(), sticky header, parallax
4. animations.min.js    (defer) — custom @keyframes triggers
5. counter.min.js       (defer) — count-up on scroll
6. forms.min.js         (defer) — AJAX contact form
```

### 6.3 TypeScript Config (`tsconfig.json`)

```json
{
  "compilerOptions": {
    "target": "ES6",
    "module": "ES6",
    "moduleResolution": "bundler",
    "strict": true,
    "outDir": "./assets/js/custom",
    "rootDir": "./assets/ts",
    "declaration": false,
    "sourceMap": false,
    "noUnusedLocals": true,
    "noUnusedParameters": true
  }
}
```

---

## 7. Database Schema (WP Custom Tables)

WordPress nie wymaga custom tabel — wszystko przechowywane w standardowym schemacie WP:

| Tabela WP | Dane |
|-----------|------|
| `wp_posts` | CPT: alubram_product, alubram_reference, alubram_testimonial |
| `wp_postmeta` | Wszystkie custom fields (ACF / meta-boxes) |
| `wp_terms` | Taxonomie: product_category, product_material, product_color, reference_type |
| `wp_term_taxonomy` | Powiązania taxonomy ↔ term |
| `wp_term_relationships` | Post ↔ Term |
| `wp_options` | Theme mods, plugin settings, transient cache |

**Transient Cache** (optymalizacja zapytań):
```php
// Przykład cache'owania wyników CPT query
$products = get_transient('alubram_featured_products');
if (false === $products) {
    $products = new WP_Query([...]);
    set_transient('alubram_featured_products', $products, HOUR_IN_SECONDS * 6);
}
```

---

## 8. Security Architecture

### 8.1 Warstwy bezpieczeństwa

```
Layer 1: Cloudflare WAF          ← DDoS, Bot protection, IP blocking
Layer 2: Web Server              ← mod_security, fail2ban, .htaccess rules
Layer 3: WordPress               ← Nonce, capability checks, sanitize/escape
Layer 4: PHP Code                ← strict_types=1, PSR-12, input validation
```

### 8.2 WordPress Security Rules

```php
// Każdy plik template:
if (!defined('ABSPATH')) { exit; }

// Każdy output:
echo esc_html($text);
echo esc_url($url);
echo esc_attr($attr);
echo wp_kses_post($html);

// Każdy formularz:
wp_nonce_field('alubram_form_action', 'alubram_nonce');
// Weryfikacja:
if (!wp_verify_nonce($_POST['alubram_nonce'], 'alubram_form_action')) {
    wp_die('Security check failed', 'Error', ['response' => 403]);
}
```

### 8.3 `.htaccess` security rules

```apache
# Blokuj dostęp do plików systemowych
<FilesMatch "^(wp-config\.php|readme\.html|license\.txt)">
    Order Allow,Deny
    Deny from all
</FilesMatch>

# Blokuj XML-RPC
<Files xmlrpc.php>
    Order Deny,Allow
    Deny from all
</Files>

# Wyłącz listowanie katalogów
Options -Indexes

# Zabezpiecz wp-includes
<IfModule mod_rewrite.c>
    RewriteEngine On
    RewriteBase /
    RewriteRule ^wp-admin/includes/ - [F,L]
    RewriteRule !^wp-includes/ - [S=3]
    RewriteRule ^wp-includes/[^/]+\.php$ - [F,L]
    RewriteRule ^wp-includes/js/tinymce/langs/.+\.php - [F,L]
    RewriteRule ^wp-includes/theme-compat/ - [F,L]
</IfModule>
```

---

## 9. Performance Architecture

### 9.1 Cele — Core Web Vitals

| Metryka | Target | Strategia |
|---------|--------|-----------|
| LCP | < 2.5s | Hero image preload, critical CSS inline, WebP/AVIF |
| FID/INP | < 100ms | Defer JS, Web Worker dla heavy tasks |
| CLS | < 0.1 | Explicit `width`/`height` na img, font-display: swap |
| TTFB | < 200ms | Server-side caching (WP Rocket), OPcache, CDN |

### 9.2 Image Optimization Strategy

```html
<!-- Format: AVIF → WebP → JPEG/PNG (progressive fallback) -->
<picture>
  <source type="image/avif"
          srcset="image-600.avif 600w, image-1200.avif 1200w"
          sizes="(max-width: 768px) 100vw, 50vw">
  <source type="image/webp"
          srcset="image-600.webp 600w, image-1200.webp 1200w"
          sizes="(max-width: 768px) 100vw, 50vw">
  <img src="image-1200.jpg"
       width="1200" height="800"
       loading="lazy"
       decoding="async"
       alt="Aluminiumzaun beschreibender Alt-Text">
</picture>
```

### 9.3 Caching Strategy

```
Browser Cache (Cache-Control headers):
  - Static assets (CSS/JS/Images): max-age=31536000 (1 year)
  - HTML pages: no-cache (WP Rocket zarządza)

WP Rocket (Page Cache):
  - Cache lifetime: 10 hours
  - Exclude: /kontakt/, /konfigurator/, /wp-admin/

Redis Object Cache:
  - WP_Query results
  - get_option() calls
  - Taxonomy queries
  - Lifetime: 1 hour (produkty), 24 hours (statyczne opcje)

Cloudflare:
  - CDN dla static assets (CSS, JS, fonts)
  - Bypass cache dla: /?* (query strings), /wp-admin/
```

---

## 10. SEO Architecture

### 10.1 Technical SEO Hierarchy

```
Yoast SEO Plugin
├── XML Sitemap                   → /sitemap_index.xml
│   ├── pages-sitemap.xml
│   ├── alubram_product-sitemap.xml
│   ├── alubram_reference-sitemap.xml
│   └── post-sitemap.xml
├── Meta tags (title, description)
├── Canonical URLs
├── Robots meta
└── Breadcrumbs (Yoast schema)

Custom Schema.org JSON-LD (inc/schema-markup.php):
├── LocalBusiness + Manufacturer  → wszystkie strony
├── Product                       → single-alubram_product.php
├── BreadcrumbList                → wszystkie strony poza Homepage
├── FAQPage                       → strony produktów, leistungen
└── Organization                  → Homepage
```

### 10.2 URL Structure (SEO-friendly slugs)

```
/ — Startseite
/uber-uns/
/produkte/
/produkte/zaune-zaunfelder/
/produkte/tore/
/produkte/carports/
/produkte/uberdachungen/
/produkte/sonderlosungen/
/referenzen/
/leistungen/
/ratgeber/
/ratgeber/{seo-slug}/
/kontakt/
/impressum/
/datenschutzerklarung/
/agb/
```

---

## 11. Deployment Architecture

### 11.1 Środowiska

| Środowisko | URL | Branch | Deploy |
|-----------|-----|--------|--------|
| **Development** | `localhost:8080` | `feature/*` | Manual |
| **Staging** | `staging.alubram.at` | `develop` | Auto (GitHub Actions) |
| **Production** | `alubram.at` | `main` | Manual approval |

### 11.2 GitHub Actions CI/CD (`.github/workflows/deploy.yml`)

```yaml
name: Deploy to Production

on:
  push:
    branches: [main]

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: PHP Lint (PSR-12)
        run: composer run lint
      - name: Build TypeScript
        run: npm run build
      - name: Deploy via SSH/rsync
        uses: appleboy/ssh-action@v1
        with:
          host: ${{ secrets.SSH_HOST }}
          username: ${{ secrets.SSH_USER }}
          key: ${{ secrets.SSH_PRIVATE_KEY }}
          script: |
            cd /var/www/html/wp-content/themes/alubramat-child
            git pull origin main
            composer install --no-dev
            wp cache flush
            wp cron event run --due-now
```

---

## 12. Plugin Dependencies

### Wymagane (required)

| Plugin | Wersja | Cel |
|--------|--------|-----|
| Yoast SEO | ≥ 22.x | SEO meta, schema, XML sitemap |
| Contact Form 7 | ≥ 5.9 | Formularze kontaktowe |
| WP Rocket | ≥ 3.16 | Cache, performance, lazy load |
| Imagify | ≥ 2.2 | AVIF/WebP konwersja, kompresja |
| Borlabs Cookie | ≥ 3.x | DSGVO Cookie Banner |
| Advanced Custom Fields Pro | ≥ 6.3 | Meta pola dla CPT |
| Classic Editor | ≥ 1.6 | Fallback editor |

### Opcjonalne

| Plugin | Wersja | Cel |
|--------|--------|-----|
| WP Fastest Cache | ≥ 1.2 | Alternatywa dla WP Rocket |
| Polylang | ≥ 3.6 | Wielojęzyczność (DE-AT / DE-DE) |
| Gravity Forms | ≥ 2.8 | Zaawansowane formularze (konfigurator) |
| Redis Object Cache | ≥ 2.5 | Redis integration |

---

## 13. Local Development Setup

```bash
# Wymagania
PHP >= 8.2
Node.js >= 20.x LTS
Composer >= 2.7
MySQL 8.0 / MariaDB 10.6
(opcjonalnie) Docker + wp-env

# Instalacja
git clone https://github.com/piotroq/alubram-gmbh-wordpress.git
cd alubram-gmbh-wordpress/src/alubramat-child

# Node dependencies
npm install

# Build TypeScript
npm run build

# Watch mode (development)
npm run watch

# PHP Codesniffer setup
composer install
composer run lint

# WordPress local environment (opcjonalnie wp-env)
npx @wordpress/env start
# WordPress dostępny na http://localhost:8888
# WP-Admin: http://localhost:8888/wp-admin (user: admin, pass: password)
```

---

## 14. Glossary

| Termin | Opis |
|--------|------|
| CPT | Custom Post Type — WordPress |
| ACF | Advanced Custom Fields — plugin do meta pól |
| DSGVO | Datenschutz-Grundverordnung (RODO po austr./niem.) |
| DACH | Deutschland, Österreich, Schweiz — rynek docelowy |
| AOS | Animate On Scroll — biblioteka animacji |
| LCP | Largest Contentful Paint — Core Web Vital |
| FID | First Input Delay — Core Web Vital |
| INP | Interaction to Next Paint — Core Web Vital |
| CLS | Cumulative Layout Shift — Core Web Vital |
| TTFB | Time To First Byte |
| JSON-LD | JSON for Linked Data — format Schema.org |
| USP | Unique Selling Proposition |

---

*ARCHITECTURE.md — ALUBRAM GMBH WordPress Project | v1.0.0 | 2026-02-26*
