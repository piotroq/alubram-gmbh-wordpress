# README.instructions.md — ALUBRAM GMBH WordPress Project

> **Dokument:** Kompletna instrukcja projektu — od setupu po deployment
> **Projekt:** `piotroq/alubram-gmbh-wordpress`
> **Klient:** ALUBRAM GMBH — Himberg bei Wien, Austria
> **Wersja:** 1.0.0 | 2026-02-26

---

## 📋 Spis Treści

1. [Wprowadzenie](#1-wprowadzenie)
2. [Stack Technologiczny](#2-stack-technologiczny)
3. [Struktura Projektu](#3-struktura-projektu)
4. [Lokalny Setup](#4-lokalny-setup)
5. [Konfiguracja WordPress](#5-konfiguracja-wordpress)
6. [Motyw alubramat-child](#6-motyw-alubramat-child)
7. [Generowanie Kodu](#7-generowanie-kodu)
8. [Testowanie i Quality Assurance](#8-testowanie-i-quality-assurance)
9. [Deployment](#9-deployment)
10. [Utrzymanie i Monitoring](#10-utrzymanie-i-monitoring)

---

## 1. Wprowadzenie

### 1.1 O Projekcie

**ALUBRAM GMBH** to austriacki producent premium aluminiowych ogrodzeń, bram, wiat garażowych (Carport) oraz zadaszeń. Projekt polega na stworzeniu nowoczesnej, szybkiej strony internetowej w języku niemieckim na CMS WordPress.

**Cele biznesowe:**
- Pozycjonowanie jako premium manufacturer na rynku DACH
- Generowanie leadów poprzez formularze kontaktowe
- Prezentacja produktów z galeriami i specyfikacjami
- Budowanie zaufania poprzez referencje i testimonials

**Cele techniczne:**
- PageSpeed Mobile ≥ 90/100
- PageSpeed Desktop ≥ 95/100
- Lighthouse SEO: 100/100
- Lighthouse Accessibility: ≥ 90/100
- Core Web Vitals: wszystkie GREEN

### 1.2 Informacje o Firmie

| Pole | Wartość |
|------|---------|
| **Nazwa** | ALUBRAM GMBH |
| **Branża** | Producent aluminiowych ogrodzeń, bram, Carport, zadaszeń |
| **Rynek** | DACH (Austria, Niemcy, Szwajcaria) |
| **Język** | Deutsch (de_AT) |
| **Siedziba** | Hintere Ortsstraße 31, 2325 Himberg bei Wien, Austria |
| **Kontakt** | +43 (0) 223 584 793 \| himberg@alubram.at |
| **Strona** | https://alubram.at |

### 1.3 Unique Selling Propositions (USPs)

```
✓ Direkt vom Hersteller — kein Zwischenhändler
✓ Lieferung in 3–6 Wochen garantiert
✓ 24 Stunden · 7 Tage erreichbar
✓ Alles aus einer Hand: Beratung → Planung → Lieferung → Montage
✓ Aluminium: rostfrei · wartungsfrei · witterungsbeständig
✓ Pulverbeschichtet — jahrzehntelange Haltbarkeit
```

---

## 2. Stack Technologiczny

### 2.1 Core Technologies

| Technologia | Wersja | Zastosowanie |
|-------------|--------|-------------|
| **WordPress** | 6.9+ | CMS |
| **PHP** | 8.2+ | Backend logic |
| **TypeScript** | 5.4+ | JavaScript z typami |
| **Tailwind CSS** | 3.4+ | Utility-first CSS |
| **MySQL** | 8.0+ / MariaDB 10.6+ | Database |

### 2.2 External Libraries

| Biblioteka | Wersja | CDN URL | Zastosowanie |
|------------|--------|---------|-------------|
| **AOS** | 2.3.4 | `cdn.jsdelivr.net/npm/aos@2.3.4` | Animate on Scroll |
| **Swiper** | 11.x | `cdn.jsdelivr.net/npm/swiper@11` | Sliders, galleries |
| **Material Icons** | latest | Google Fonts | Icon system |
| **Google Fonts** | latest | fonts.googleapis.com | Typography |

### 2.3 Required WordPress Plugins

**Obowiązkowe:**
- Yoast SEO (≥ 22.x) — SEO meta, schema, XML sitemap
- Contact Form 7 (≥ 5.9) — Formularze kontaktowe
- WP Rocket (≥ 3.16) — Cache, performance
- Imagify (≥ 2.2) — AVIF/WebP compression
- Borlabs Cookie (≥ 3.x) — DSGVO compliance
- Advanced Custom Fields Pro (≥ 6.3) — Custom meta fields
- Classic Editor (≥ 1.6) — Fallback editor

**Opcjonalne:**
- Polylang — Wielojęzyczność
- Gravity Forms — Zaawansowane formularze
- Redis Object Cache — Redis integration
- WooCommerce — E-commerce

---

## 3. Struktura Projektu

```
alubram-gmbh-wordpress/
│
├── .claude/                          ← AI Agents configuration
│   ├── agents/
│   │   ├── business-product/wordpress-master.md
│   │   ├── code-review/php-reviewer.md
│   │   ├── seo/seo-de-specialist.md
│   │   ├── design/ui-ux-designer.md
│   │   └── security/wp-security-auditor.md
│   └── settings.json
│
├── .cursorrules/                     ← Cursor AI IDE rules
│   ├── php.mdc
│   ├── typescript.mdc
│   ├── css.mdc
│   └── general.mdc
│
├── .github/
│   └── workflows/
│       ├── deploy.yml                ← CI/CD pipeline
│       ├── lint.yml                  ← PHP/JS linting
│       └── tests.yml                 ← PHPUnit + Jest
│
├── docs/                             ← Project documentation
│   ├── ARCHITECTURE.md
│   ├── BRAND-SETTINGS.md
│   ├── DESIGN-SYSTEM.md
│   ├── README.agents.md
│   ├── README.collections.md
│   └── analiza-elementów-logo-alubram.md
│
├── src/                              ← WordPress core (nie commitujemy)
│   ├── wp-admin/
│   ├── wp-includes/
│   └── wp-content/
│       └── themes/
│           ├── alubramat/            ← Parent theme (blank)
│           │   ├── style.css
│           │   ├── functions.php
│           │   └── index.php
│           │
│           └── alubramat-child/      ← Child theme (AKTYWNY)
│               ├── style.css         ← Brand variables + CSS
│               ├── functions.php     ← Bootstrap
│               ├── front-page.php    ← Homepage template
│               ├── page.php
│               ├── single.php
│               ├── archive.php
│               ├── header.php
│               ├── footer.php
│               ├── 404.php
│               │
│               ├── page-templates/
│               │   ├── page-uber-uns.php
│               │   ├── page-produkte.php
│               │   ├── page-referenzen.php
│               │   ├── page-leistungen.php
│               │   └── page-kontakt.php
│               │
│               ├── template-parts/
│               │   ├── sections/
│               │   │   ├── hero-homepage.php
│               │   │   ├── section-usps.php
│               │   │   ├── section-products-grid.php
│               │   │   ├── section-why-us.php
│               │   │   ├── section-process.php
│               │   │   ├── section-testimonials.php
│               │   │   ├── section-gallery.php
│               │   │   ├── section-stats-counter.php
│               │   │   ├── section-cta-banner.php
│               │   │   ├── section-faq.php
│               │   │   └── section-contact-form.php
│               │   │
│               │   ├── components/
│               │   │   ├── breadcrumbs.php
│               │   │   ├── product-card.php
│               │   │   ├── cta-button.php
│               │   │   └── pagination.php
│               │   │
│               │   └── global/
│               │       ├── header-nav.php
│               │       └── footer-widgets.php
│               │
│               ├── inc/
│               │   ├── custom-post-types.php
│               │   ├── taxonomies.php
│               │   ├── meta-boxes.php
│               │   ├── schema-markup.php
│               │   ├── enqueue.php
│               │   ├── nav-menus.php
│               │   ├── widgets.php
│               │   ├── shortcodes.php
│               │   └── ajax-handlers.php
│               │
│               ├── assets/
│               │   ├── css/
│               │   │   ├── tailwind.min.css
│               │   │   ├── aos.min.css
│               │   │   ├── swiper.min.css
│               │   │   └── custom/
│               │   │       ├── components.css
│               │   │       ├── animations.css
│               │   │       └── responsive.css
│               │   │
│               │   ├── js/
│               │   │   ├── aos.min.js
│               │   │   ├── swiper.min.js
│               │   │   └── custom/
│               │   │       ├── main.ts
│               │   │       ├── animations.ts
│               │   │       ├── counter.ts
│               │   │       └── forms.ts
│               │   │
│               │   └── images/
│               │       ├── logo.svg
│               │       ├── logo-white.svg
│               │       ├── favicon.ico
│               │       └── og-image.jpg
│               │
│               └── languages/
│                   ├── de_AT.po
│                   └── de_AT.mo
│
├── scripts/                          ← Build & automation scripts
│   ├── build.sh
│   ├── deploy.sh
│   └── optimize-images.sh
│
├── .gitignore
├── .gitattributes
├── README.md
├── TECHNICAL-SHEETS.md               ← Master instruction
├── ARCHITECTURE.md                   ← Technical architecture
├── BRAND-SETTINGS.md                 ← Brand identity
├── DESIGN-SYSTEM.md                  ← UI components
└── package.json
```

---

## 4. Lokalny Setup

### 4.1 Wymagania Systemowe

```bash
# Wymagane oprogramowanie
PHP >= 8.2
Node.js >= 20.x LTS
npm >= 10.x
Composer >= 2.7
MySQL 8.0 / MariaDB 10.6+
Git >= 2.40

# Opcjonalnie (recommended)
Docker >= 24.x
wp-cli >= 2.9
```

### 4.2 Krok po Kroku — Instalacja

```bash
# 1. Sklonuj repozytorium
git clone https://github.com/piotroq/alubram-gmbh-wordpress.git
cd alubram-gmbh-wordpress

# 2. Zainstaluj Node.js dependencies
npm install

# 3. Zainstaluj Composer dependencies (dla PHP linting)
composer install

# 4. Skonfiguruj lokalne środowisko WordPress
# Opcja A: wp-env (recommended)
npx @wordpress/env start

# Opcja B: XAMPP / MAMP
# - Skopiuj zawartość src/ do htdocs/
# - Skonfiguruj bazę danych
# - Uruchom WordPress installer

# 5. Build TypeScript
npm run build

# 6. Watch mode (development)
npm run watch

# 7. Build Tailwind CSS
npm run css:build
```

### 4.3 Konfiguracja Środowiska

**Stwórz plik `.env` (nie commitować do repozytorium):**

```bash
# .env
WP_ENV=development
WP_URL=http://localhost:8888
WP_ADMIN_USER=admin
WP_ADMIN_PASS=password123
DB_NAME=alubram_dev
DB_USER=root
DB_PASS=root
DB_HOST=localhost
```

### 4.4 Weryfikacja Instalacji

```bash
# Sprawdź wersje
php -v          # >= 8.2
node -v         # >= 20.x
npm -v          # >= 10.x
composer -V     # >= 2.7

# Test build
npm run build
npm run lint

# Dostęp do lokalnego WordPress
# http://localhost:8888
# http://localhost:8888/wp-admin
```

---

## 5. Konfiguracja WordPress

### 5.1 Instalacja WordPress

```bash
# Przez WP-CLI (recommended)
wp core download --locale=de_DE
wp config create --dbname=alubram_dev --dbuser=root --dbpass=root --dbhost=localhost
wp core install --url="http://localhost:8888" --title="ALUBRAM GMBH" --admin_user=admin --admin_password=password123 --admin_email=himberg@alubram.at --language=de_DE

# Przez przeglądarkę
# 1. Odwiedź http://localhost:8888
# 2. Wybierz język: Deutsch
# 3. Wypełnij formularz instalacyjny
```

### 5.2 Konfiguracja wp-config.php

```php
<?php
// alubram-gmbh-wordpress/src/wp-config.php

// Security keys (wygeneruj: https://api.wordpress.org/secret-key/1.1/salt/)
define('AUTH_KEY',         'put-your-unique-phrase-here');
define('SECURE_AUTH_KEY',  'put-your-unique-phrase-here');
define('LOGGED_IN_KEY',    'put-your-unique-phrase-here');
define('NONCE_KEY',        'put-your-unique-phrase-here');
define('AUTH_SALT',        'put-your-unique-phrase-here');
define('SECURE_AUTH_SALT', 'put-your-unique-phrase-here');
define('LOGGED_IN_SALT',   'put-your-unique-phrase-here');
define('NONCE_SALT',       'put-your-unique-phrase-here');

// Performance
define('WP_MEMORY_LIMIT', '256M');
define('WP_MAX_MEMORY_LIMIT', '512M');
define('WP_POST_REVISIONS', 5);
define('AUTOSAVE_INTERVAL', 300);

// Debug (tylko development!)
define('WP_DEBUG', true);
define('WP_DEBUG_LOG', true);
define('WP_DEBUG_DISPLAY', false);
define('SCRIPT_DEBUG', true);

// Localization
define('WPLANG', 'de_DE');

// ... reszta domyślnej konfiguracji
```

### 5.3 Instalacja Pluginów

```bash
# Przez WP-CLI
wp plugin install yoast-seo --activate
wp plugin install contact-form-7 --activate
wp plugin install advanced-custom-fields-pro --activate
wp plugin install wp-rocket --activate
wp plugin install imagify --activate
wp plugin install borlabs-cookie --activate
wp plugin install classic-editor --activate

# Przez WP-Admin:
# Plugins → Add New → Search & Install
```

### 5.4 Konfiguracja Permalinków

```bash
# Ustawienia → Permalinks
# Wybierz: Custom Structure → /%postname%/

# Przez WP-CLI:
wp rewrite structure '/%postname%/'
wp rewrite flush
```

---

## 6. Motyw alubramat-child

### 6.1 Aktywacja Motywu

```bash
# Przez WP-CLI
wp theme activate alubramat-child

# Przez WP-Admin:
# Appearance → Themes → Activate "Alubramat Child"
```

### 6.2 Struktura Plików Motywu

**Główne pliki:**

| Plik | Opis |
|------|------|
| `style.css` | CSS variables, brand colors, custom styles |
| `functions.php` | Bootstrap, includes, hooks |
| `front-page.php` | Homepage template |
| `page.php` | Generic page template |
| `header.php` | Site header + navigation |
| `footer.php` | Site footer + scripts |

### 6.3 Brand Colors — style.css

```css
/*
 * Theme Name: Alubramat Child
 * Template: alubramat
 * Version: 1.0.0
 * Author: Piotroq Dev
 */

:root {
  /* Primary Brand Colors */
  --color-primary: #1A1A2E;
  --color-primary-light: #16213E;
  --color-accent: #C8A96E;
  --color-accent-light: #E8D5A3;
  --color-accent-dark: #A07840;

  /* Secondary Colors */
  --color-secondary: #0F3460;
  --color-dark: #0D0D0D;
  --color-light: #F8F6F1;
  --color-white: #FFFFFF;

  /* Typography */
  --font-heading: 'Montserrat', sans-serif;
  --font-body: 'Inter', sans-serif;
  --font-accent: 'Playfair Display', serif;

  /* Spacing */
  --section-padding: 80px 0;
  --container-max: 1280px;
}
```

### 6.4 Enqueue Scripts — inc/enqueue.php

```php
<?php
/**
 * Enqueue all styles and scripts
 * @package alubramat-child
 */

if (!defined('ABSPATH')) { exit; }

add_action('wp_enqueue_scripts', function(): void {
    $assets = get_stylesheet_directory_uri() . '/assets';

    // Google Fonts (preconnect)
    add_action('wp_head', function(): void {
        echo '<link rel="preconnect" href="https://fonts.googleapis.com">';
        echo '<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>';
    }, 1);

    // Styles
    wp_enqueue_style('google-fonts', 'https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,400;0,600;0,700;0,800&family=Inter:wght@300;400;500;600&family=Playfair+Display:ital,wght@0,400;0,700&display=swap', [], null);
    wp_enqueue_style('material-icons', 'https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:opsz,wght,FILL,GRAD@20..48,100..700,0..1,-50..200', [], null);
    wp_enqueue_style('tailwind', $assets . '/css/tailwind.min.css', [], '3.4.0');
    wp_enqueue_style('aos', $assets . '/css/aos.min.css', [], '2.3.4');
    wp_enqueue_style('swiper', $assets . '/css/swiper.min.css', [], '11.0.0');
    wp_enqueue_style('alubramat-child-style', get_stylesheet_uri(), ['tailwind', 'aos', 'swiper'], '1.0.0');

    // Scripts
    wp_enqueue_script('aos', $assets . '/js/aos.min.js', [], '2.3.4', ['defer' => true]);
    wp_enqueue_script('swiper', $assets . '/js/swiper.min.js', [], '11.0.0', ['defer' => true]);
    wp_enqueue_script('alubramat-child-main', $assets . '/js/custom/main.min.js', ['aos', 'swiper'], '1.0.0', ['defer' => true]);

    // Localize script (PHP → JS)
    wp_localize_script('alubramat-child-main', 'alubramConfig', [
        'ajaxUrl' => admin_url('admin-ajax.php'),
        'nonce' => wp_create_nonce('alubram_ajax_nonce'),
        'siteUrl' => home_url('/'),
    ]);
});
```

---

## 7. Generowanie Kodu

### 7.1 AI Agents Workflow

Projekt używa AI agents do generowania kodu. Każdy agent ma specjalizację:

| Agent | Specjalizacja | Plik |
|-------|--------------|------|
| `wordpress-master` | WordPress development | `.claude/agents/business-product/wordpress-master.md` |
| `php-reviewer` | PHP code review | `.claude/agents/code-review/php-reviewer.md` |
| `seo-de-specialist` | SEO DE/AT | `.claude/agents/seo/seo-de-specialist.md` |
| `ui-ux-designer` | UI/UX design | `.claude/agents/design/ui-ux-designer.md` |
| `wp-security-auditor` | Security audit | `.claude/agents/security/wp-security-auditor.md` |

### 7.2 Przykładowy Prompt — Generowanie Template

```markdown
[TASK]: Wygeneruj kompletny plik `page-templates/page-kontakt.php`

[CONTEXT]:
- Strona kontaktowa z formularzem AJAX + Google Maps
- Formularz: Name, Email, Tel, PLZ, Nachricht, Produktinteresse, DSGVO checkbox
- Schema.org: LocalBusiness JSON-LD
- Sekcje: Hero z breadcrumbs, dane kontaktowe, formularz, mapa

[REQUIREMENTS]:
- PSR-12, strict_types=1
- DSGVO compliant (Google Maps za cookie consent)
- AOS animacje
- Mobile-first CSS
- AJAX submit + nonce WordPress
- Pełna walidacja client + server side

[EXPECTED OUTPUT]:
- Kompletny plik PHP (700+ linii)
- Inline komentarze
- PHPDoc dla funkcji
```

### 7.3 Standard Code Generation

**Każdy plik PHP template musi zawierać:**

```php
<?php
/**
 * Template Name: [Nazwa]
 * Template Post Type: page
 * @package alubramat-child
 * @version 1.0.0
 */

// Security check
if (!defined('ABSPATH')) {
    exit;
}

// Strict types
declare(strict_types=1);

get_header();
?>

<!-- HERO SECTION -->
<section class="alubram-hero" data-aos="fade-up">
    <div class="alubram-container">
        <?php get_template_part('template-parts/components/breadcrumbs'); ?>
        <h1><?php the_title(); ?></h1>
    </div>
</section>

<!-- MAIN CONTENT -->
<main class="alubram-main">
    <!-- Sections here -->
</main>

<?php get_footer(); ?>
```

---

## 8. Testowanie i Quality Assurance

### 8.1 PHP Linting

```bash
# PHP CodeSniffer (PSR-12 + WordPress)
composer run lint

# Auto-fix
composer run lint:fix

# PHPStan (static analysis)
vendor/bin/phpstan analyse src/alubramat-child --level=8
```

### 8.2 TypeScript/JavaScript Linting

```bash
# ESLint
npm run lint

# Auto-fix
npm run lint:fix

# Type check
npx tsc --noEmit
```

### 8.3 Performance Testing

```bash
# Lighthouse CLI
npm install -g lighthouse
lighthouse http://localhost:8888 --view

# PageSpeed Insights API
curl "https://www.googleapis.com/pagespeedonline/v5/runPagespeed?url=http://localhost:8888&strategy=mobile"
```

### 8.4 Accessibility Testing

```bash
# axe-core CLI
npm install -g @axe-core/cli
axe http://localhost:8888

# Lighthouse accessibility
lighthouse http://localhost:8888 --only-categories=accessibility
```

### 8.5 SEO Validation

```bash
# Schema.org Validator
https://validator.schema.org/

# Rich Results Test
https://search.google.com/test/rich-results

# Yoast SEO Analysis
# WP-Admin → SEO → General → Site analysis
```

### 8.6 Checklist Przed Deploy

```markdown
## Pre-Deploy Checklist

### Code Quality
- [ ] PHP linting passed (PSR-12)
- [ ] TypeScript compilation successful
- [ ] No console errors
- [ ] All images optimized (AVIF/WebP)

### Performance
- [ ] PageSpeed Mobile ≥ 90
- [ ] PageSpeed Desktop ≥ 95
- [ ] LCP < 2.5s
- [ ] CLS < 0.1
- [ ] INP < 100ms

### SEO
- [ ] Yoast SEO: all green
- [ ] Schema.org valid
- [ ] Meta titles/descriptions set
- [ ] XML sitemap generated
- [ ] Robots.txt configured

### Accessibility
- [ ] WCAG 2.1 AA passed
- [ ] All images have alt=""
- [ ] Keyboard navigation works
- [ ] Color contrast ≥ 4.5:1

### Security
- [ ] All inputs sanitized
- [ ] All outputs escaped
- [ ] Nonces on all forms
- [ ] No sensitive data in repo

### Content
- [ ] All content in German (DE)
- [ ] No placeholder text
- [ ] All links working
- [ ] Forms tested
```

---

## 9. Deployment

### 9.1 Środowiska

| Środowisko | URL | Branch | Deploy |
|-----------|-----|--------|--------|
| **Development** | `localhost:8888` | `feature/*` | Manual |
| **Staging** | `staging.alubram.at` | `develop` | Auto (GitHub Actions) |
| **Production** | `alubram.at` | `main` | Manual approval |

### 9.2 GitHub Actions CI/CD

**`.github/workflows/deploy.yml`:**

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

      - name: Setup PHP
        uses: shivammathur/setup-php@v2
        with:
          php-version: '8.2'

      - name: Setup Node.js
        uses: actions/setup-node@v4
        with:
          node-version: '20.x'

      - name: Install dependencies
        run: |
          npm install
          composer install --no-dev

      - name: Build TypeScript
        run: npm run build

      - name: Build CSS
        run: npm run css:build

      - name: Run tests
        run: npm run test

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
            npm run build
            wp cache flush
            wp cron event run --due-now
```

### 9.3 Manual Deployment

```bash
# 1. Build locally
npm run build
npm run css:build

# 2. Commit changes
git add .
git commit -m "feat: [description]"
git push origin main

# 3. Deploy to server (SSH)
ssh user@alubram.at
cd /var/www/html/wp-content/themes/alubramat-child
git pull origin main

# 4. Clear cache
wp cache flush
wp cron event run --due-now

# 5. Verify deployment
curl -I https://alubram.at
```

### 9.4 Backup Przed Deploy

```bash
# Database backup
wp db export backup-$(date +%Y%m%d).sql

# Files backup
tar -czf backup-files-$(date +%Y%m%d).tar.gz /var/www/html/wp-content/uploads

# Full backup (plugin)
# UpdraftPlus → Backup Now
```

---

## 10. Utrzymanie i Monitoring

### 10.1 Regularne Zadania

**Codziennie:**
- [ ] Sprawdź uptime (https://uptime.alubram.at)
- [ ] Review error logs (`wp-content/debug.log`)
- [ ] Monitoruj formularze kontaktowe

**Co tydzień:**
- [ ] Backup verification
- [ ] Security scan (Wordfence)
- [ ] Performance check (PageSpeed)
- [ ] Update plugins (test na staging)

**Co miesiąc:**
- [ ] Full security audit
- [ ] Content audit (aktualizacja produktów)
- [ ] SEO audit (Yoast, Search Console)
- [ ] Accessibility check

### 10.2 Monitoring Tools

| Narzędzie | URL | Zastosowanie |
|-----------|-----|-------------|
| **Google Analytics 4** | https://analytics.google.com/ | Traffic, conversions |
| **Google Search Console** | https://search.google.com/search-console | SEO, indeksowanie |
| **Uptime Robot** | https://uptimerobot.com/ | Uptime monitoring |
| **PageSpeed Insights** | https://pagespeed.web.dev/ | Performance |
| **Wordfence** | WP-Admin → Wordfence | Security firewall |

### 10.3 Error Handling

```php
// Custom error handler (functions.php)
add_action('wp_footer', function(): void {
    if (is_user_logged_in() && current_user_can('manage_options')) {
        echo '<div id="admin-debug-info" style="display:none;">';
        echo 'PHP: ' . PHP_VERSION . ' | WP: ' . get_bloginfo('version');
        echo ' | Theme: ' . wp_get_theme()->get('Version');
        echo '</div>';
    }
});

// AJAX error logging
add_action('wp_ajax_log_error', function(): void {
    check_ajax_referer('alubram_ajax_nonce', 'nonce');
    $error = sanitize_text_field($_POST['error'] ?? '');
    error_log('[ALUBRAM AJAX] ' . $error);
    wp_send_json_success();
});
```

### 10.4 Support Contacts

| Kontakt | Email | Telefon |
|---------|-------|---------|
| **Klient** | himberg@alubram.at | +43 223 584 793 |
| **Developer** | [your-email] | [your-phone] |
| **Hosting** | [hosting-support] | [hosting-phone] |

---

## 📎 Aneks

### A. Przydatne Komendy WP-CLI

```bash
# Database
wp db export
wp db import backup.sql
wp db optimize
wp db repair

# Cache
wp cache flush
wp transient delete --all
wp cron event run --due-now

# Users
wp user list
wp user create username email@example.com --role=administrator
wp user update username --role=editor

# Plugins
wp plugin list
wp plugin install plugin-name --activate
wp plugin delete plugin-name

# Themes
wp theme list
wp theme activate alubramat-child

# Search & Replace (ostrożnie!)
wp search-replace 'old-text' 'new-text' --dry-run
wp search-replace 'old-text' 'new-text' --skip-columns=guid
```

### B. Troubleshooting

**Problem: Strona ładuje się wolno**

```bash
# 1. Sprawdź query count
# Dodaj do wp-config.php:
define('SAVEQUERIES', true);

# 2. Włącz debug bar
wp plugin install debug-bar --activate

# 3. Sprawdź cache
wp cache flush
wp transient delete --all

# 4. Optymalizuj obrazy
wp media regenerate
```

**Problem: Błąd 500 po deploy**

```bash
# 1. Sprawdź error log
tail -f /var/log/apache2/error.log
# lub
tail -f wp-content/debug.log

# 2. Wyłącz wszystkie pluginy
wp plugin deactivate --all

# 3. Włącz debug mode
# wp-config.php:
define('WP_DEBUG', true);
define('WP_DEBUG_LOG', true);

# 4. Przywróć backup
wp db import backup-20260226.sql
```

---

*README.instructions.md — ALUBRAM GMBH WordPress Project | v1.0.0 | 2026-02-26*
