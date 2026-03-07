# 📋 ALUBRAM GMBH — Kompletny Plan Projektu WordPress

> **Dokument:** Masterplan projektu strony internetowej  
> **Klient:** ALUBRAM GMBH — Himberg bei Wien, Austria  
> **Repozytorium:** `piotroq/alubram-gmbh-wordpress`  
> **Wersja:** 2.0.0 | 2026-03-07  
> **Autor:** Piotroq Dev + Claude Opus 4.6  
> **Status:** ⬜ Planning Phase  

---

## 📑 Spis Treści

1. [Executive Summary](#1-executive-summary)
2. [Analiza Firmy i Rynku](#2-analiza-firmy-i-rynku)
3. [Stack Technologiczny i Narzędzia](#3-stack-technologiczny-i-narzędzia)
4. [Środowisko Deweloperskie i AI Toolchain](#4-środowisko-deweloperskie-i-ai-toolchain)
5. [Architektura Motywu WordPress](#5-architektura-motywu-wordpress)
6. [Struktura Strony (Sitemap SEO)](#6-struktura-strony-sitemap-seo)
7. [Design System i Brand Identity](#7-design-system-i-brand-identity)
8. [Fazy Projektu — Szczegółowy Roadmap](#8-fazy-projektu--szczegółowy-roadmap)
   - [FAZA 1: Discovery & Planning](#faza-1-discovery--planning-tygodnie-1-2)
   - [FAZA 2: Środowisko i Infrastruktura](#faza-2-środowisko-i-infrastruktura-tydzień-2-3)
   - [FAZA 3: Theme Foundation](#faza-3-theme-foundation-tygodnie-3-4)
   - [FAZA 4: Core Templates](#faza-4-core-templates-tygodnie-5-7)
   - [FAZA 5: Homepage & Sekcje](#faza-5-homepage--sekcje-tygodnie-7-8)
   - [FAZA 6: Strony Produktowe & CPT](#faza-6-strony-produktowe--cpt-tygodnie-8-9)
   - [FAZA 7: Strony Informacyjne](#faza-7-strony-informacyjne-tygodnie-9-10)
   - [FAZA 8: Interaktywność i Formularze](#faza-8-interaktywność-i-formularze-tydzień-10-11)
   - [FAZA 9: SEO, Performance & DSGVO](#faza-9-seo-performance--dsgvo-tygodnie-11-12)
   - [FAZA 10: Testing & QA](#faza-10-testing--qa-tygodnie-12-13)
   - [FAZA 11: Deployment & Go-Live](#faza-11-deployment--go-live-tydzień-14)
   - [FAZA 12: Post-Launch & Monitoring](#faza-12-post-launch--monitoring-tygodnie-15-16)
9. [Rekomendacje Narzędzi AI/Dev](#9-rekomendacje-narzędzi-aidev)
10. [KPIs i Metryki Sukcesu](#10-kpis-i-metryki-sukcesu)
11. [Zarządzanie Ryzykiem](#11-zarządzanie-ryzykiem)
12. [Harmonogram Git Flow](#12-harmonogram-git-flow)
13. [Checklist Pre-Launch](#13-checklist-pre-launch)

---

## 1. Executive Summary

### 1.1 Cel Projektu

Zaprojektowanie i wdrożenie premium strony internetowej dla **ALUBRAM GMBH** — austriackiego producenta aluminiowych ogrodzeń, bram, wiat garażowych (Carport) i zadaszeń. Strona targetuje rynek DACH (Austria, Niemcy, Szwajcaria) wyłącznie w języku niemieckim, z naciskiem na generowanie leadów, pozycjonowanie SEO i budowanie wizerunku marki premium.

### 1.2 Kluczowe Założenia

| Parametr | Wartość |
|----------|---------|
| **CMS** | WordPress 6.9 (Gutenberg + Classic Editor) |
| **Język strony** | Niemiecki (de_AT) |
| **Motyw** | Custom parent `alubramat` + child `alubramat-child` |
| **Framework CSS** | Tailwind CSS |
| **Animacje** | AOS.js |
| **Ikony** | Material Design Icons (Google) |
| **Slider/Galeria** | Swiper.js |
| **Strategia** | Mobile-first, Performance-first |
| **PageSpeed Target** | Mobile ≥ 90, Desktop ≥ 95 |
| **Timeline** | 14–16 tygodni |
| **Deploy produkcyjny** | https://alubram.at |
| **Deploy dev** | Docker Compose (LocalWP / wp-env) |

### 1.3 USP Firmy (Unique Selling Propositions)

1. **Direkt vom Hersteller** — bez pośredników, bezpośrednio od producenta
2. **Lieferung in 3–6 Wochen** — gwarantowana dostawa
3. **Geöffnet 24/7** — dostępność całodobowa
4. **Alles aus einer Hand** — Beratung → Planung → Lieferung → Montage
5. **Aluminium: rostfrei, wartungsfrei, witterungsbeständig** — premium jakość, pulverbeschichtet

---

## 2. Analiza Firmy i Rynku

### 2.1 Dane Firmy

| Pole | Wartość |
|------|---------|
| **Nazwa** | ALUBRAM GMBH |
| **Branża** | Producent aluminiowych produktów ogrodzeniowych i zadaszeń |
| **Siedziba** | Hintere Ortsstraße 31, 2325 Himberg bei Wien, Austria |
| **Telefon** | +43 (0) 223 584 793 / +43 664 437 3954 |
| **Email** | himberg@alubram.at / wien@alubram.at |
| **WWW** | https://alubram.at |
| **Osoba kontaktowa** | Herr Szpak Irek |

### 2.2 Portfolio Produktów

| Kategoria DE | Opis | URL Slug |
|--------------|------|----------|
| **Zäune & Zaunfelder** | Panele ogrodzeniowe aluminiowe | `/produkte/zaune-zaunfelder/` |
| **Tore & Einfahrtstore** | Bramy wjazdowe, suwane, furtki | `/produkte/tore/` |
| **Carports** | Wiaty garażowe aluminiowe | `/produkte/carports/` |
| **Überdachungen** | Zadaszenia, pergole, tarasy | `/produkte/uberdachungen/` |
| **Sonderlösungen** | Rozwiązania na zamówienie | `/produkte/sonderlosungen/` |

### 2.3 Rynek Docelowy

- **Główny:** Austria (Wiedeń i okolice, Dolna Austria)
- **Rozszerzony:** Niemcy (południowe), Szwajcaria
- **Persona:** Właściciele domów jednorodzinnych, architekci, firmy budowlane, deweloperzy
- **Język:** Wyłącznie niemiecki (de_AT / de_DE)

### 2.4 Analiza Konkurencji — Inspiracje Wizualne

| Strona | Co nas inspiruje |
|--------|-----------------|
| [arrea.at](https://arrea.at/) | Autoplay wideo w sekcjach, dynamika, efekty parallax |
| [selt.com/home-de](https://www.selt.com/home-de) | Ładne menu, układ sekcji, premium fonty, przejrzysty layout |
| [mbveranda.de](https://mbveranda.de/) | Ogólny wygląd wizualny, premium prezentacja produktów |

---

## 3. Stack Technologiczny i Narzędzia

### 3.1 Core Stack

| Warstwa | Technologia | Wersja |
|---------|-------------|--------|
| **CMS** | WordPress | 6.9 |
| **Edytor** | Gutenberg + Classic Editor | Latest |
| **PHP** | PHP | 8.2+ (strict_types=1, PSR-12) |
| **JavaScript** | TypeScript / ES6+ | 5.x |
| **CSS Framework** | Tailwind CSS | 3.x (Play CDN → build produkcyjny) |
| **Animacje** | AOS.js | 2.x |
| **Slider** | Swiper.js | 11.x |
| **Ikony** | Material Design Icons (Google) | Latest |
| **Fonty** | Google Fonts (Inter, Montserrat, Playfair Display) | Latest |
| **Baza danych** | MySQL 8.0 / MariaDB 10.6+ | — |

### 3.2 Narzędzia Deweloperskie

| Narzędzie | Zastosowanie |
|-----------|-------------|
| **VS Code** | Główny edytor kodu (+ extensions: PHP Intelephense, Tailwind IntelliSense, WordPress Snippets) |
| **Git + GitHub** | Version control, Git Flow branching |
| **LocalWP** | Lokalne środowisko WordPress (szybki start) |
| **Docker Compose** | Alternatywne środowisko dev (WordPress + MySQL + phpMyAdmin) |
| **Node.js 20 LTS** | Build tools, npm scripts, TypeScript compilation |
| **Composer 2.7+** | PHP dependency management |
| **WP-CLI** | WordPress zarządzanie z CLI |
| **Git Bash** | Skrypty automatyzujące (EOF heredoc scripts) |

### 3.3 Pluginy WordPress (obowiązkowe)

| Plugin | Zastosowanie | Priorytet |
|--------|-------------|-----------|
| **Yoast SEO** (lub RankMath) | SEO meta, sitemap XML, breadcrumbs | 🔴 Krytyczny |
| **Contact Form 7** | Formularze kontaktowe | 🔴 Krytyczny |
| **Advanced Custom Fields (ACF) Pro** | Meta pola dla CPT | 🔴 Krytyczny |
| **WP Rocket** (lub W3 Total Cache) | Cache, performance | 🔴 Krytyczny |
| **Imagify** (lub ShortPixel) | Kompresja, konwersja .avif/.webp | 🟠 Wysoki |
| **Borlabs Cookie** | DSGVO Cookie Banner | 🔴 Krytyczny |
| **Classic Editor** | Wsparcie klasycznego edytora | 🟡 Średni |
| **Wordfence** | Bezpieczeństwo | 🟠 Wysoki |
| **UpdraftPlus** | Backupy | 🟠 Wysoki |

---

## 4. Środowisko Deweloperskie i AI Toolchain

### 4.1 Lokalne Środowisko (Docker Compose)

```yaml
# docker-compose.yml — Środowisko deweloperskie
version: '3.8'
services:
  wordpress:
    image: wordpress:6.9-php8.2-apache
    ports:
      - "8080:80"
    environment:
      WORDPRESS_DB_HOST: db
      WORDPRESS_DB_USER: wordpress
      WORDPRESS_DB_PASSWORD: wordpress
      WORDPRESS_DB_NAME: alubram_dev
      WORDPRESS_DEBUG: 1
    volumes:
      - ./src/wp-content/themes:/var/www/html/wp-content/themes
      - ./src/wp-content/plugins:/var/www/html/wp-content/plugins
      - ./src/wp-content/uploads:/var/www/html/wp-content/uploads
    depends_on:
      - db

  db:
    image: mysql:8.0
    environment:
      MYSQL_DATABASE: alubram_dev
      MYSQL_USER: wordpress
      MYSQL_PASSWORD: wordpress
      MYSQL_ROOT_PASSWORD: rootpassword
    volumes:
      - db_data:/var/lib/mysql

  phpmyadmin:
    image: phpmyadmin:latest
    ports:
      - "8081:80"
    environment:
      PMA_HOST: db
    depends_on:
      - db

volumes:
  db_data:
```

**Dostęp:**
- WordPress: `http://localhost:8080`
- WP-Admin: `http://localhost:8080/wp-admin`
- phpMyAdmin: `http://localhost:8081`

### 4.2 AI Toolchain — Modele i Zastosowania

#### Modele Cloud (główne)

| Model | Zastosowanie | Priorytet |
|-------|-------------|-----------|
| **Claude Opus 4.6** | Złożone szablony PHP, architektura, code review, dokumentacja, planowanie | 🔴 Główny |
| **Claude Sonnet 4.6** | Szybkie generowanie kodu, shortcody, CSS, pojedyncze sekcje | 🟠 Szybki |
| **Claude Code** | Agentic coding, automatyzacja, iteracja na plikach | 🟠 Terminal |

#### Modele Ollama (lokalne) — Rekomendowane do zadań

| Model | Parametry | Zastosowanie w projekcie |
|-------|-----------|--------------------------|
| **qwen3-coder-next:cloud** | Cloud | ⭐ **Główny lokalny coder** — generowanie PHP templates, TypeScript, CSS |
| **qwen3-coder:480b-cloud** | Cloud | Zaawansowane generowanie kodu, pair-programming |
| **qwen3.5:397b-cloud** | Cloud | Planowanie, analiza, copywriting SEO DE |
| **deepseek-v3.2:cloud** | Cloud | Generowanie kodu PHP/JS, debugging |
| **devstral-small-2:24b-cloud** | Cloud | Code review, szybkie poprawki |
| **codestral:latest** | 12 GB | **Offline coder** — generowanie kodu bez internetu |
| **deepseek-coder-v2:16b** | 8.9 GB | Lokalne generowanie kodu, debugging |
| **qwen2.5-coder:7b** | 4.7 GB | Szybkie snippety, autouzupełnianie |
| **deepseek-coder:6.7b** | 3.8 GB | Lekki coder do szybkich tasków |
| **phind-codellama:latest** | 19 GB | Złożone problemy kodowe, debugging |

#### Modele pomocnicze

| Model | Zastosowanie |
|-------|-------------|
| **qwen3-vl:235b-cloud** | Analiza screenshotów stron konkurencji, wizualna inspekcja |
| **llava-llama3:latest** | Lokalna analiza obrazów/screenshotów |
| **minicpm-v:latest** | Szybka analiza wizualna |
| **deepseek-r1:8b** | Reasoning, planowanie architektury, analiza problemów |
| **aya:8b** | Wielojęzyczność — generowanie treści DE |
| **dolphin3:latest** | Uncensored model — brainstorming, kreatywne pomysły |

#### Modele embedding (RAG / wyszukiwanie kontekstu)

| Model | Zastosowanie |
|-------|-------------|
| **bge-m3:latest** | Embedding dokumentacji projektu → RAG |
| **mxbai-embed-large:latest** | Embedding kodu → semantic search |
| **nomic-embed-text:latest** | Lekki embedding tekstu |

### 4.3 Dodatkowe Narzędzia — Rekomendacje

| Narzędzie | Zastosowanie | Link |
|-----------|-------------|------|
| **OpenWebUI** | Interfejs webowy dla Ollama, zarządzanie modelami, chat | https://openwebui.com |
| **OpenCode** | CLI narzędzie do AI-assisted coding | https://github.com/opencode-ai/opencode |
| **Claude Code** | Agentic coding w terminalu | `npm install -g @anthropic-ai/claude-code` |
| **Aider** | AI pair-programming w terminalu (obsługa wielu modeli) | https://aider.chat |
| **Continue.dev** | VS Code extension — AI autocomplete z Ollama | https://continue.dev |
| **Cursor** | AI-native code editor (alternatywa dla VS Code) | https://cursor.com |
| **Cline** | VS Code extension — autonomous coding agent | https://github.com/cline/cline |
| **Windsurf** | AI-powered IDE z flow state | https://windsurf.com |
| **Repomix** | Pakowanie repo do jednego pliku dla kontekstu LLM | https://repomix.com |
| **WP-CLI** | WordPress management z linii poleceń | https://wp-cli.org |
| **n8n** | Automatyzacja workflow (self-hosted) | https://n8n.io |
| **Playwright** | E2E testing, screenshoty stron | https://playwright.dev |
| **Lighthouse CI** | Automatyczne audyty performance | https://github.com/GoogleChrome/lighthouse-ci |
| **Screaming Frog** | SEO crawler / audyt | https://www.screamingfrog.co.uk |

### 4.4 Skrypt Inicjalizacji Projektu (Git Bash EOF)

```bash
#!/bin/bash
# === ALUBRAM GMBH — Project Bootstrap Script ===
# Uruchom: bash init-project.sh

set -euo pipefail

PROJECT_DIR="alubram-gmbh-wordpress"
THEME_PARENT="alubramat"
THEME_CHILD="alubramat-child"

echo "🚀 Inicjalizacja projektu ALUBRAM GMBH..."

# 1. Klonowanie repozytorium
if [ ! -d "$PROJECT_DIR" ]; then
  git clone https://github.com/piotroq/alubram-gmbh-wordpress.git
fi
cd "$PROJECT_DIR"

# 2. Instalacja dependencies
echo "📦 Instalacja npm dependencies..."
npm install

echo "📦 Instalacja composer dependencies..."
composer install

# 3. Tworzenie struktury motywu parent
echo "🎨 Tworzenie motywu parent: $THEME_PARENT..."
PARENT_DIR="src/wp-content/themes/$THEME_PARENT"
mkdir -p "$PARENT_DIR"

cat > "$PARENT_DIR/style.css" << 'EOFCSS'
/*
 * Theme Name: Alubramat
 * Theme URI: https://alubram.at
 * Author: Piotroq Dev
 * Author URI: https://github.com/piotroq
 * Description: Premium WordPress theme for ALUBRAM GMBH - aluminum fences, gates, carports manufacturer.
 * Version: 1.0.0
 * License: Proprietary
 * Text Domain: alubramat
 */
EOFCSS

cat > "$PARENT_DIR/index.php" << 'EOFPHP'
<?php
/**
 * Silence is golden.
 * All rendering happens in child theme.
 */
if (!defined('ABSPATH')) { exit; }
get_header();
the_content();
get_footer();
EOFPHP

cat > "$PARENT_DIR/functions.php" << 'EOFPHP'
<?php
declare(strict_types=1);
if (!defined('ABSPATH')) { exit; }

/**
 * Alubramat Parent Theme — Minimal Setup
 * All customizations go in child theme.
 */
function alubramat_parent_setup(): void {
    add_theme_support('title-tag');
    add_theme_support('post-thumbnails');
    add_theme_support('html5', ['search-form', 'comment-form', 'gallery', 'caption']);
    add_theme_support('custom-logo');
}
add_action('after_setup_theme', 'alubramat_parent_setup');
EOFPHP

# 4. Tworzenie struktury motywu child
echo "👶 Tworzenie motywu child: $THEME_CHILD..."
CHILD_DIR="src/wp-content/themes/$THEME_CHILD"
mkdir -p "$CHILD_DIR"/{page-templates,template-parts/{sections,components,global},inc,assets/{css/custom,js/custom,ts,images},languages}

cat > "$CHILD_DIR/style.css" << 'EOFCSS'
/*
 * Theme Name: Alubramat Child
 * Template: alubramat
 * Theme URI: https://alubram.at
 * Author: Piotroq Dev
 * Version: 1.0.0
 * Text Domain: alubramat-child
 */

/* === ALUBRAM GMBH Brand Variables === */
:root {
  --color-primary: #1A1A2E;
  --color-primary-light: #16213E;
  --color-accent: #C8A96E;
  --color-accent-light: #E8D5A3;
  --color-accent-dark: #A07840;
  --color-secondary: #0F3460;
  --color-dark: #0D0D0D;
  --color-light: #F8F6F1;
  --color-white: #FFFFFF;
  --color-gray-100: #F5F5F5;
  --color-gray-200: #E8E8E8;
  --color-gray-500: #9E9E9E;
  --color-gray-800: #2D2D2D;
  --color-aluminum: #8D9DB6;
  --color-aluminum-light: #B8C5D6;
  --color-aluminum-dark: #5A6A7E;
  --font-heading: 'Montserrat', 'Raleway', sans-serif;
  --font-body: 'Inter', 'Open Sans', sans-serif;
  --font-accent: 'Playfair Display', serif;
  --section-padding: 80px 0;
  --section-padding-mobile: 50px 0;
  --container-max: 1280px;
  --border-radius: 4px;
  --border-radius-lg: 12px;
  --shadow-sm: 0 2px 8px rgba(0,0,0,0.08);
  --shadow-md: 0 8px 30px rgba(0,0,0,0.12);
  --shadow-lg: 0 20px 60px rgba(0,0,0,0.18);
  --shadow-gold: 0 4px 20px rgba(200,169,110,0.3);
  --transition-fast: 0.2s ease;
  --transition-base: 0.35s ease;
  --transition-slow: 0.6s cubic-bezier(0.4, 0, 0.2, 1);
  --gradient-primary: linear-gradient(135deg, #1A1A2E 0%, #0F3460 100%);
  --gradient-gold: linear-gradient(135deg, #C8A96E 0%, #E8D5A3 50%, #A07840 100%);
  --gradient-overlay: linear-gradient(180deg, rgba(26,26,46,0.4) 0%, rgba(26,26,46,0.85) 100%);
  --gradient-hero: linear-gradient(135deg, rgba(15,52,96,0.9) 0%, rgba(26,26,46,0.95) 100%);
}
EOFCSS

# 5. Git setup
echo "📌 Git configuration..."
git checkout -b develop 2>/dev/null || git checkout develop
git add .
git commit -m "feat: initialize theme structure for alubramat + alubramat-child"

echo ""
echo "✅ Projekt ALUBRAM GMBH zainicjalizowany!"
echo "   Parent theme: $PARENT_DIR"
echo "   Child theme:  $CHILD_DIR"
echo ""
echo "Następne kroki:"
echo "   1. docker compose up -d"
echo "   2. Otwórz http://localhost:8080/wp-admin"
echo "   3. Aktywuj motyw 'Alubramat Child'"
echo "   4. Zainstaluj pluginy (ACF Pro, Yoast SEO, Contact Form 7)"
```

---

## 5. Architektura Motywu WordPress

### 5.1 Hierarchia Motywów

```
WordPress Engine
└── alubramat/                    ← Parent theme (MINIMALNY)
    ├── style.css                 ← Deklaracja motywu
    ├── functions.php             ← add_theme_support() only
    ├── index.php                 ← Fallback template
    └── screenshot.png
    
└── alubramat-child/              ← Child theme (AKTYWNY — cała logika tutaj)
    ├── style.css                 ← :root variables + brand CSS
    ├── functions.php             ← Master include file
    │
    ├── header.php                ← Sticky header + topbar + nav
    ├── footer.php                ← Footer widgets + legal links + scripts
    ├── front-page.php            ← Homepage (11 sekcji)
    ├── page.php                  ← Default page template
    ├── single.php                ← Single blog post
    ├── archive.php               ← Blog archive
    ├── 404.php                   ← Error page
    ├── search.php                ← Search results
    ├── sidebar.php               ← Sidebar widgets
    │
    ├── page-templates/           ← Custom Page Templates
    │   ├── page-uber-uns.php
    │   ├── page-produkte.php
    │   ├── page-referenzen.php
    │   ├── page-leistungen.php
    │   └── page-kontakt.php
    │
    ├── template-parts/
    │   ├── sections/             ← Reusable homepage/page sections
    │   │   ├── hero-homepage.php
    │   │   ├── section-usps.php
    │   │   ├── section-products-grid.php
    │   │   ├── section-why-us.php
    │   │   ├── section-process.php
    │   │   ├── section-testimonials.php
    │   │   ├── section-gallery.php
    │   │   ├── section-stats-counter.php
    │   │   ├── section-cta-banner.php
    │   │   ├── section-faq.php
    │   │   └── section-contact-form.php
    │   ├── components/           ← Micro-components
    │   │   ├── breadcrumbs.php
    │   │   ├── product-card.php
    │   │   ├── cta-button.php
    │   │   └── pagination.php
    │   └── global/
    │       ├── header-nav.php
    │       └── footer-widgets.php
    │
    ├── inc/                      ← PHP includes (logika biznesowa)
    │   ├── custom-post-types.php ← CPT: alubram_product, alubram_reference, alubram_testimonial
    │   ├── taxonomies.php        ← Taxonomie produktowe
    │   ├── meta-boxes.php        ← Custom meta fields
    │   ├── schema-markup.php     ← JSON-LD generator
    │   ├── enqueue.php           ← wp_enqueue_scripts/styles
    │   ├── nav-menus.php         ← Menu registration
    │   ├── widgets.php           ← Widget areas
    │   ├── shortcodes.php        ← [alubram_*] shortcodes
    │   └── ajax-handlers.php     ← AJAX form handlers
    │
    ├── assets/
    │   ├── css/
    │   │   ├── tailwind.min.css
    │   │   ├── aos.min.css
    │   │   ├── swiper.min.css
    │   │   └── custom/
    │   │       ├── components.css
    │   │       ├── animations.css
    │   │       └── responsive.css
    │   ├── js/
    │   │   ├── aos.min.js
    │   │   ├── swiper.min.js
    │   │   └── custom/
    │   │       ├── main.js       ← Compiled from .ts
    │   │       ├── animations.js
    │   │       ├── counter.js
    │   │       └── forms.js
    │   ├── ts/                   ← TypeScript sources
    │   │   ├── main.ts
    │   │   ├── animations.ts
    │   │   ├── counter.ts
    │   │   └── forms.ts
    │   └── images/
    │       ├── logo.svg
    │       ├── logo-white.svg
    │       ├── og-image.jpg
    │       └── patterns/
    │
    └── languages/
        ├── de_AT.po
        └── de_AT.mo
```

### 5.2 Ładowanie functions.php

```
WordPress → alubramat/functions.php (parent — minimal)
         → alubramat-child/functions.php
              ├── require_once get_stylesheet_directory() . '/inc/enqueue.php'
              ├── require_once get_stylesheet_directory() . '/inc/custom-post-types.php'
              ├── require_once get_stylesheet_directory() . '/inc/taxonomies.php'
              ├── require_once get_stylesheet_directory() . '/inc/meta-boxes.php'
              ├── require_once get_stylesheet_directory() . '/inc/nav-menus.php'
              ├── require_once get_stylesheet_directory() . '/inc/schema-markup.php'
              ├── require_once get_stylesheet_directory() . '/inc/shortcodes.php'
              ├── require_once get_stylesheet_directory() . '/inc/widgets.php'
              └── require_once get_stylesheet_directory() . '/inc/ajax-handlers.php'
```

### 5.3 Custom Post Types (CPT)

| CPT | Slug | Pola Custom | Taxonomie |
|-----|------|-------------|-----------|
| **Produkte** | `alubram_product` | `_product_category`, `_product_material`, `_delivery_time`, `_warranty_years`, `_price_from`, `_gallery_images`, `_technical_specs`, `_colors_available` | `product_category`, `product_material`, `product_color` |
| **Referenzen** | `alubram_reference` | `_ref_location`, `_ref_product_type`, `_ref_year`, `_ref_gallery`, `_ref_client_name` | `reference_type`, `reference_location` |
| **Testimonials** | `alubram_testimonial` | `_client_name`, `_client_location`, `_rating` (1-5), `_review_text`, `_product_purchased` | — |

---

## 6. Struktura Strony (Sitemap SEO)

```
🏠 Startseite (Homepage)                    /
├── 📋 Über uns                              /uber-uns/
├── 🏭 Produkte                              /produkte/
│   ├── 🔩 Zäune & Zaunfelder               /produkte/zaune-zaunfelder/
│   ├── 🚪 Tore & Einfahrtstore             /produkte/tore/
│   ├── 🅿️ Carports                          /produkte/carports/
│   ├── 🏗️ Überdachungen & Terrassendächer   /produkte/uberdachungen/
│   └── ⚙️ Sonderlösungen                    /produkte/sonderlosungen/
├── 📸 Referenzen / Galerie                  /referenzen/
├── 🛠️ Leistungen                            /leistungen/
├── 📐 Konfigurator (opcjonalnie)            /konfigurator/
├── 📝 Blog / Ratgeber                       /ratgeber/
│   └── 📄 Einzelner Beitrag                /ratgeber/{slug}/
├── 📞 Kontakt                               /kontakt/
├── ⚖️ Impressum                              /impressum/
├── 🔒 Datenschutzerklärung                  /datenschutzerklarung/
└── 📜 AGB                                   /agb/
```

### 6.1 Mapa Szablonów → Plików PHP

| Strona | Szablon PHP | Sekcje |
|--------|------------|--------|
| **Homepage** | `front-page.php` | 11 sekcji (Hero, USPs, Produkte, Warum, Prozess, Galerie, Über uns, Testimonials, CTA, Blog, Kontakt) |
| **Über uns** | `page-templates/page-uber-uns.php` | Hero, Geschichte, Team, Werte, Zahlen, CTA |
| **Produkte (archiwum)** | `page-templates/page-produkte.php` | Hero, Kategorie-Grid, Filter, Produkte-Liste |
| **Einzelprodukt** | `single-alubram_product.php` | Hero, Beschreibung, Vorteile, Galerie, Farben, FAQ, CTA |
| **Referenzen** | `page-templates/page-referenzen.php` | Hero, Masonry Gallery, Filter, Lightbox |
| **Leistungen** | `page-templates/page-leistungen.php` | Hero, Services Grid, Prozess, CTA |
| **Kontakt** | `page-templates/page-kontakt.php` | Hero, Formular, Karte, Öffnungszeiten |
| **Blog Archiv** | `archive.php` | Posts Grid, Sidebar, Pagination |
| **Blog Single** | `single.php` | Content, Related Posts, CTA |
| **Default Page** | `page.php` | Breadcrumbs, Content, CTA |

---

## 7. Design System i Brand Identity

### 7.1 Paleta Kolorów

| Token | Hex | Użycie |
|-------|-----|--------|
| `--color-primary` | `#1A1A2E` | Dark Navy — tło header/footer, główne elementy |
| `--color-primary-light` | `#16213E` | Dark Blue — wariant tła |
| `--color-accent` | `#C8A96E` | Gold/Champagne — CTA buttony, akcenty premium |
| `--color-accent-light` | `#E8D5A3` | Light Gold — hover stany, subteksty |
| `--color-accent-dark` | `#A07840` | Dark Gold — aktywne stany |
| `--color-secondary` | `#0F3460` | Deep Blue — sekcje alternatywne |
| `--color-dark` | `#0D0D0D` | Almost Black — tekst główny |
| `--color-light` | `#F8F6F1` | Warm White — tło sekcji jasnych |
| `--color-aluminum` | `#8D9DB6` | Aluminum — metaliczne akcenty |

### 7.2 Typografia

| Rola | Font | Waga | Zastosowanie |
|------|------|------|-------------|
| **Nagłówki** | Montserrat | 600, 700, 800 | H1–H3, tytuły sekcji |
| **Body** | Inter | 400, 500, 600 | Tekst główny, paragrafy |
| **Akcent** | Playfair Display | 400i, 600 | Cytaty, wyróżnienia, "premium feel" |

### 7.3 Efekty i Animacje

| Efekt | Implementacja | Kontekst |
|-------|---------------|----------|
| **AOS fade-up** | `data-aos="fade-up"` | Wejście sekcji na scroll |
| **AOS zoom-in** | `data-aos="zoom-in-up"` | Karty produktowe |
| **Parallax** | Vanilla JS `data-parallax` | Hero, tła sekcji |
| **Counter animation** | IntersectionObserver + requestAnimationFrame | Sekcja statystyk |
| **Card hover lift** | CSS `transform: translateY(-8px)` | Karty, przyciski |
| **Gold shimmer** | CSS `::after` + gradient translate | CTA button hover |
| **Sticky header** | JS scroll listener (transparent → solid) | Navigation bar |
| **Smooth scroll** | CSS `scroll-behavior: smooth` | Anchor links |

---

## 8. Fazy Projektu — Szczegółowy Roadmap

### FAZA 1: Discovery & Planning (Tygodnie 1-2)

> **Cel:** Zebranie wymagań, analiza konkurencji, finalizacja planu projektu  
> **Status:** ⬜ Not Started  
> **Odpowiedzialny:** PM + Developer  

#### Zadania

| # | Zadanie | Priorytet | Narzędzie | Status |
|---|---------|-----------|-----------|--------|
| 1.1 | ✅ Analiza obecnej strony alubram.at (audit) | 🔴 | Claude Opus, Screaming Frog | ⬜ |
| 1.2 | ✅ Analiza konkurencji (arrea.at, selt.com, mbveranda.de) — screenshoty, UX, SEO | 🔴 | qwen3-vl (wizualna), Playwright | ⬜ |
| 1.3 | ✅ Finalizacja brand identity (kolory, fonty, tone of voice) | 🔴 | Claude Opus, Figma | ⬜ |
| 1.4 | ✅ Keyword research DE (SEMrush / Ahrefs / Ubersuggest) | 🔴 | Ahrefs MCP, Claude | ⬜ |
| 1.5 | ✅ Sitemap & Information Architecture — finalna wersja | 🟠 | Claude, Mermaid Chart | ⬜ |
| 1.6 | ✅ Content strategy — plan treści per strona (słowa kluczowe, długość, CTA) | 🟠 | qwen3.5:397b, Claude | ⬜ |
| 1.7 | ✅ Wireframy (low-fidelity) — mobile + desktop | 🟡 | Figma, Canva MCP | ⬜ |
| 1.8 | ✅ Finalizacja tech stack i konfiguracja narzędzi | 🟠 | — | ⬜ |
| 1.9 | ✅ Dokument planistyczny projektu (ten plik) | 🔴 | Claude Opus | ✅ |

#### Deliverables Fazy 1
- [x] ALUBRAM-GMBH-PLAN-PROJEKTU.md (ten dokument)
- [ ] BRAND-SETTINGS.md — finalna wersja
- [ ] SEO-STRATEGY-ALUBRAM.md — keyword map
- [ ] PAGES-WIREFRAMES.md — wireframy wszystkich stron
- [ ] ARCHITECTURE.md — finalna architektura

#### Milestone M1: Discovery Complete
- **Termin:** Tydzień 2, Dzień 5
- **Kryteria:** Wszystkie deliverables zatwierdzone, sitemap finalna, keyword map gotowy

---

### FAZA 2: Środowisko i Infrastruktura (Tydzień 2-3)

> **Cel:** Skonfigurowanie lokalnego środowiska dev, repozytorium, Docker, CI/CD  
> **Status:** ⬜ Not Started  
> **Odpowiedzialny:** Developer  

#### Zadania

| # | Zadanie | Priorytet | Narzędzie | Status |
|---|---------|-----------|-----------|--------|
| 2.1 | Konfiguracja Docker Compose (WordPress + MySQL + phpMyAdmin) | 🔴 | Docker, Git Bash | ⬜ |
| 2.2 | Konfiguracja LocalWP (alternatywne środowisko) | 🟡 | LocalWP | ⬜ |
| 2.3 | Inicjalizacja repozytorium Git (branches: main, develop, feature/*) | 🔴 | Git, GitHub | ⬜ |
| 2.4 | Konfiguracja `.gitignore` (WordPress-specific) | 🔴 | Git | ⬜ |
| 2.5 | Tworzenie struktury folderów motywu parent `alubramat` | 🔴 | Git Bash EOF script | ⬜ |
| 2.6 | Tworzenie struktury folderów motywu child `alubramat-child` | 🔴 | Git Bash EOF script | ⬜ |
| 2.7 | Konfiguracja `package.json` (npm scripts, TypeScript, build) | 🟠 | Node.js | ⬜ |
| 2.8 | Konfiguracja `tsconfig.json` | 🟠 | TypeScript | ⬜ |
| 2.9 | Instalacja WordPress 6.9 + aktywacja motywu child | 🔴 | WP-CLI / Docker | ⬜ |
| 2.10 | Instalacja obowiązkowych pluginów (Yoast, CF7, ACF Pro, WP Rocket, Borlabs) | 🔴 | WP-CLI | ⬜ |
| 2.11 | Konfiguracja Ollama + OpenWebUI (lokalne modele AI) | 🟡 | Ollama, OpenWebUI | ⬜ |
| 2.12 | Konfiguracja Claude Code / OpenCode / Aider | 🟡 | npm, pip | ⬜ |

#### Skrypt instalacji pluginów (WP-CLI)

```bash
#!/bin/bash
# install-plugins.sh
wp plugin install wordpress-seo --activate
wp plugin install contact-form-7 --activate
wp plugin install classic-editor --activate
wp plugin install wordfence --activate
wp plugin install updraftplus --activate
# ACF Pro, WP Rocket, Borlabs Cookie — wymagają licencji (ręczna instalacja)
echo "⚠️  Zainstaluj ręcznie: ACF Pro, WP Rocket, Borlabs Cookie, Imagify"
```

#### Deliverables Fazy 2
- [ ] Działające środowisko Docker Compose na localhost:8080
- [ ] Repozytorium GitHub z branches: main, develop
- [ ] Motyw parent + child zainstalowane i aktywne
- [ ] Pluginy zainstalowane i skonfigurowane
- [ ] AI toolchain skonfigurowany (Ollama + OpenWebUI)

#### Milestone M2: Infrastructure Ready
- **Termin:** Tydzień 3, Dzień 2
- **Kryteria:** WordPress działa na Docker, motyw child aktywny, pluginy zainstalowane

---

### FAZA 3: Theme Foundation (Tygodnie 3-4)

> **Cel:** Zbudowanie fundamentów motywu — style.css, functions.php, header.php, footer.php, enqueue assets  
> **Status:** ⬜ Not Started  
> **Odpowiedzialny:** Developer  

#### Zadania

| # | Zadanie | Priorytet | Model AI | Status |
|---|---------|-----------|----------|--------|
| 3.1 | **`style.css`** — `:root` variables, reset, base typography, brand colors | 🔴 | Claude Opus | ⬜ |
| 3.2 | **`functions.php`** — master include, theme setup, image sizes | 🔴 | Claude Opus | ⬜ |
| 3.3 | **`inc/enqueue.php`** — Google Fonts, Material Icons, Tailwind, AOS, Swiper, custom CSS/JS | 🔴 | Claude Sonnet | ⬜ |
| 3.4 | **`inc/nav-menus.php`** — rejestracja menu (primary, footer, legal) | 🟠 | Claude Sonnet | ⬜ |
| 3.5 | **`header.php`** — sticky header, topbar (telefon/email), logo SVG, mobile hamburger, mega-menu Produkte | 🔴 | Claude Opus | ⬜ |
| 3.6 | **`footer.php`** — 4-kolumnowy footer, social links, legal menu, copyright, back-to-top | 🔴 | Claude Opus | ⬜ |
| 3.7 | **`assets/css/custom/components.css`** — buttons, cards, badges, form elements | 🟠 | qwen3-coder-next | ⬜ |
| 3.8 | **`assets/css/custom/animations.css`** — @keyframes (shimmer, float, pulse-gold, count-up) | 🟠 | Claude Sonnet | ⬜ |
| 3.9 | **`assets/css/custom/responsive.css`** — mobile-first media queries | 🟠 | Claude Sonnet | ⬜ |
| 3.10 | **`assets/ts/main.ts`** — AOS init, sticky header, parallax, smooth scroll | 🟠 | qwen3-coder-next | ⬜ |
| 3.11 | **`inc/widgets.php`** — sidebar + footer widget areas | 🟡 | Claude Sonnet | ⬜ |
| 3.12 | **`template-parts/components/breadcrumbs.php`** — Breadcrumbs component (Yoast lub custom) | 🟠 | Claude Sonnet | ⬜ |
| 3.13 | **`template-parts/components/cta-button.php`** — reusable CTA button component | 🟡 | Claude Sonnet | ⬜ |

#### Deliverables Fazy 3
- [ ] `style.css` — kompletny z `:root` variables
- [ ] `functions.php` — z require_once dla wszystkich inc/
- [ ] `header.php` + `footer.php` — responsywne, sticky, z animacjami
- [ ] `inc/enqueue.php` — wszystkie assets załadowane prawidłowo
- [ ] Komplet plików CSS custom (components, animations, responsive)
- [ ] `main.ts` — skompilowany do main.js

#### Milestone M3: Theme Foundation Complete
- **Termin:** Tydzień 4, Dzień 5
- **Kryteria:** Header/footer działają, style załadowane, AOS działa, responsywność OK

---

### FAZA 4: Core Templates (Tygodnie 5-7)

> **Cel:** Rejestracja CPT, tworzenie shortcodes, budowanie core templates  
> **Status:** ⬜ Not Started  

#### Zadania

| # | Zadanie | Priorytet | Model AI | Status |
|---|---------|-----------|----------|--------|
| 4.1 | **`inc/custom-post-types.php`** — CPT: alubram_product, alubram_reference, alubram_testimonial | 🔴 | Claude Opus | ⬜ |
| 4.2 | **`inc/taxonomies.php`** — product_category, product_material, product_color, reference_type | 🔴 | Claude Opus | ⬜ |
| 4.3 | **`inc/meta-boxes.php`** — custom fields dla CPT (lub ACF Pro config) | 🔴 | Claude Opus | ⬜ |
| 4.4 | **`inc/schema-markup.php`** — JSON-LD generator (LocalBusiness, Product, FAQPage, BreadcrumbList) | 🟠 | Claude Opus | ⬜ |
| 4.5 | **`inc/shortcodes.php`** — [alubram_cta], [alubram_usps], [alubram_products], [alubram_counter], etc. | 🟠 | qwen3-coder-next | ⬜ |
| 4.6 | **`inc/ajax-handlers.php`** — AJAX contact form handler, nonce verification | 🟠 | Claude Opus | ⬜ |
| 4.7 | **`template-parts/components/product-card.php`** — reusable product card | 🟠 | Claude Sonnet | ⬜ |
| 4.8 | **`template-parts/components/pagination.php`** — styled pagination | 🟡 | Claude Sonnet | ⬜ |
| 4.9 | **`page.php`** — default page template z breadcrumbs | 🟠 | Claude Sonnet | ⬜ |
| 4.10 | **`404.php`** — custom 404 page | 🟡 | Claude Sonnet | ⬜ |
| 4.11 | **`search.php`** — search results page | 🟡 | Claude Sonnet | ⬜ |

#### Deliverables Fazy 4
- [ ] 3 CPT zarejestrowane i działające w WP-Admin
- [ ] Taxonomie przypisane do CPT
- [ ] Meta-boxy lub ACF grupy pól skonfigurowane
- [ ] Schema.org JSON-LD generator
- [ ] 10+ shortcodes zarejestrowanych
- [ ] AJAX form handler z nonce

#### Milestone M4: Core Templates Complete
- **Termin:** Tydzień 7, Dzień 3
- **Kryteria:** CPT działają, shortcodes renderują, AJAX form działa

---

### FAZA 5: Homepage & Sekcje (Tygodnie 7-8)

> **Cel:** Zbudowanie kompletnej strony głównej z 11 sekcjami  
> **Status:** ⬜ Not Started  

#### Zadania — 11 Sekcji Homepage

| # | Sekcja | Plik | Priorytet | Status |
|---|--------|------|-----------|--------|
| 5.1 | **Hero Section** — fullscreen parallax/video, H1, 2x CTA, USP badges | `hero-homepage.php` | 🔴 | ⬜ |
| 5.2 | **USP Bar** — 4 ikony MDI z kluczowymi zaletami, AOS fade-in | `section-usps.php` | 🔴 | ⬜ |
| 5.3 | **Produkte Übersicht** — grid 4-5 kategorii z hover effects | `section-products-grid.php` | 🔴 | ⬜ |
| 5.4 | **Warum ALUBRAM** — why us + counter animation (Jahre, Projekte, Kunden) | `section-why-us.php` | 🟠 | ⬜ |
| 5.5 | **Unser Prozess** — 4-step: Beratung → Planung → Lieferung → Montage | `section-process.php` | 🟠 | ⬜ |
| 5.6 | **Referenzen Galerie** — masonry grid + Swiper lightbox | `section-gallery.php` | 🟠 | ⬜ |
| 5.7 | **Über uns Teaser** — company story + parallax image | inline w `front-page.php` | 🟡 | ⬜ |
| 5.8 | **Kundenmeinungen** — testimonials Swiper slider | `section-testimonials.php` | 🟠 | ⬜ |
| 5.9 | **CTA Banner** — fullwidth gradient + inline contact form | `section-cta-banner.php` | 🔴 | ⬜ |
| 5.10 | **Aktuelles Blog** — 3 najnowsze wpisy z thumbnails | inline w `front-page.php` | 🟡 | ⬜ |
| 5.11 | **Kontakt Teaser** — mapa Google + dane kontaktowe | `section-contact-form.php` | 🟠 | ⬜ |
| 5.12 | **`front-page.php`** — MASTER template łączący wszystkie sekcje | `front-page.php` | 🔴 | ⬜ |

#### Deliverables Fazy 5
- [ ] `front-page.php` — kompletny z 11 sekcjami
- [ ] 11 plików `template-parts/sections/`
- [ ] `assets/ts/counter.ts` — counter animation script
- [ ] Wszystkie sekcje z AOS animacjami
- [ ] Responsywność mobile/tablet/desktop zweryfikowana
- [ ] Schema.org JSON-LD na homepage

#### Milestone M5: Homepage Complete
- **Termin:** Tydzień 8, Dzień 5
- **Kryteria:** Wszystkie 11 sekcji zaimplementowane, AOS działa, mobile responsive, LCP < 2.5s

---

### FAZA 6: Strony Produktowe & CPT (Tygodnie 8-9)

> **Cel:** Strony produktowe — archiwum, single product, kategorie  
> **Status:** ⬜ Not Started  

#### Zadania

| # | Zadanie | Plik | Priorytet | Status |
|---|---------|------|-----------|--------|
| 6.1 | **Produkte Archiv** — grid z filtrami kategorii | `page-produkte.php` | 🔴 | ⬜ |
| 6.2 | **Single Product** — pełny szablon z 7 sekcjami (hero, opis, zalety, galeria, kolory, FAQ, CTA) | `single-alubram_product.php` | 🔴 | ⬜ |
| 6.3 | **Kategoria: Zäune** — landing page z filtrem | category archive | 🟠 | ⬜ |
| 6.4 | **Kategoria: Tore** — landing page | category archive | 🟠 | ⬜ |
| 6.5 | **Kategoria: Carports** — landing page | category archive | 🟠 | ⬜ |
| 6.6 | **Kategoria: Überdachungen** — landing page | category archive | 🟠 | ⬜ |
| 6.7 | Populacja treści produktów (min. 3-5 produktów per kategoria) | WP-Admin / WP-CLI | 🟠 | ⬜ |
| 6.8 | Swiper gallery na single product | `assets/ts/` | 🟠 | ⬜ |
| 6.9 | Schema.org Product JSON-LD na each single product | `inc/schema-markup.php` | 🟠 | ⬜ |

#### Deliverables Fazy 6
- [ ] `page-produkte.php` — archiwum produktów z filtrami
- [ ] `single-alubram_product.php` — kompletny szablon single product
- [ ] 15-25 produktów demo z treścią SEO DE
- [ ] Schema.org Product markup na każdym produkcie

#### Milestone M6: Product Pages Complete
- **Termin:** Tydzień 9, Dzień 5
- **Kryteria:** Archiwum + single product gotowe, treści załadowane, galerie działają

---

### FAZA 7: Strony Informacyjne (Tygodnie 9-10)

> **Cel:** Strony Über uns, Leistungen, Referenzen, Kontakt, Blog  
> **Status:** ⬜ Not Started  

#### Zadania

| # | Zadanie | Plik | Priorytet | Status |
|---|---------|------|-----------|--------|
| 7.1 | **Über uns** — Historia, Team, Werte, Zahlen & Fakten, CTA | `page-uber-uns.php` | 🟠 | ⬜ |
| 7.2 | **Leistungen** — Services grid, Prozess timeline, CTA | `page-leistungen.php` | 🟠 | ⬜ |
| 7.3 | **Referenzen** — Masonry gallery + filtry + lightbox | `page-referenzen.php` | 🟠 | ⬜ |
| 7.4 | **Kontakt** — Formularz, mapa Google, Öffnungszeiten, Anfahrt | `page-kontakt.php` | 🔴 | ⬜ |
| 7.5 | **Blog Archiv** — grid postów, sidebar, pagination | `archive.php` | 🟡 | ⬜ |
| 7.6 | **Blog Single** — artykuł, related posts, CTA | `single.php` | 🟡 | ⬜ |
| 7.7 | **Impressum** — wymagane prawem austriackim | page content | 🔴 | ⬜ |
| 7.8 | **Datenschutzerklärung** — DSGVO polityka prywatności | page content | 🔴 | ⬜ |
| 7.9 | **AGB** — warunki ogólne | page content | 🟡 | ⬜ |
| 7.10 | Populacja treści demo (Referenzen, Testimonials, Blog posts) | WP-Admin | 🟠 | ⬜ |

#### Deliverables Fazy 7
- [ ] 5 page templates kompletnych
- [ ] `archive.php` + `single.php` dla bloga
- [ ] Treści prawne (Impressum, Datenschutz, AGB)
- [ ] 5-10 referencji demo, 5-8 testimonials, 3-5 blog posts

#### Milestone M7: All Pages Complete
- **Termin:** Tydzień 10, Dzień 5
- **Kryteria:** Wszystkie szablony stron gotowe, treści demo załadowane

---

### FAZA 8: Interaktywność i Formularze (Tydzień 10-11)

> **Cel:** Formularze kontaktowe, AJAX, walidacja, DSGVO consent  
> **Status:** ⬜ Not Started  

#### Zadania

| # | Zadanie | Priorytet | Status |
|---|---------|-----------|--------|
| 8.1 | Contact Form 7 — konfiguracja formularzy (Kontakt, Angebot, Rückruf) | 🔴 | ⬜ |
| 8.2 | Własny AJAX form handler (alternatywa/uzupełnienie CF7) | 🟠 | ⬜ |
| 8.3 | Client-side validation (HTML5 + JS) | 🟠 | ⬜ |
| 8.4 | Server-side sanitization (PHP) | 🔴 | ⬜ |
| 8.5 | DSGVO checkbox (zgoda na przetwarzanie danych) | 🔴 | ⬜ |
| 8.6 | Honeypot anti-spam field | 🟠 | ⬜ |
| 8.7 | Email notifications do himberg@alubram.at | 🔴 | ⬜ |
| 8.8 | Success/error messages inline (bez page reload) | 🟠 | ⬜ |
| 8.9 | Google Maps embed (lazy load po cookie consent) | 🟠 | ⬜ |
| 8.10 | Back-to-top button | 🟡 | ⬜ |
| 8.11 | Mobile hamburger menu (vanilla JS) | 🟠 | ⬜ |
| 8.12 | Smooth scroll anchor links | 🟡 | ⬜ |

#### Deliverables Fazy 8
- [ ] 3 formularze kontaktowe działające (Kontakt, Angebot, Rückruf)
- [ ] Walidacja client + server-side
- [ ] DSGVO consent + honeypot
- [ ] Email powiadomienia skonfigurowane
- [ ] Google Maps z lazy load

#### Milestone M8: Interactivity Complete
- **Termin:** Tydzień 11, Dzień 3
- **Kryteria:** Formularze działają, emailing OK, mapa działa po cookie consent

---

### FAZA 9: SEO, Performance & DSGVO (Tygodnie 11-12)

> **Cel:** Optymalizacja SEO, performance tuning, DSGVO compliance  
> **Status:** ⬜ Not Started  

#### Zadania

| # | Zadanie | Priorytet | Status |
|---|---------|-----------|--------|
| 9.1 | **Yoast SEO config** — meta titles, descriptions per page (DE keywords) | 🔴 | ⬜ |
| 9.2 | **XML Sitemap** — generacja + submission do Google Search Console | 🔴 | ⬜ |
| 9.3 | **Schema.org JSON-LD** — weryfikacja na każdej stronie (Google Rich Results Test) | 🔴 | ⬜ |
| 9.4 | **Open Graph** — og:title, og:description, og:image, og:locale (de_AT) | 🟠 | ⬜ |
| 9.5 | **Canonical URLs** — każda strona ma canonical | 🟠 | ⬜ |
| 9.6 | **robots.txt** — konfiguracja | 🟠 | ⬜ |
| 9.7 | **Image optimization** — kompresja, .avif/.webp konwersja (Imagify/ShortPixel) | 🔴 | ⬜ |
| 9.8 | **Lazy loading** — `loading="lazy"` + `decoding="async"` | 🔴 | ⬜ |
| 9.9 | **Critical CSS** — inline above-the-fold | 🟠 | ⬜ |
| 9.10 | **Font preloading** — `<link rel="preload">` dla kritycznych fontów | 🟠 | ⬜ |
| 9.11 | **Script defer/async** — wszystkie JS z defer | 🟠 | ⬜ |
| 9.12 | **WP Rocket config** — page cache, browser cache, minification, lazy load | 🔴 | ⬜ |
| 9.13 | **Borlabs Cookie** — DSGVO banner, kategoryzacja cookies, blokowanie skryptów | 🔴 | ⬜ |
| 9.14 | **Google Fonts local hosting** — DSGVO compliance (nie ładuj z Google CDN) | 🔴 | ⬜ |
| 9.15 | **ALT tags audit** — każdy img z opisowym alt (DE) | 🟠 | ⬜ |
| 9.16 | **Internal linking** — strategia linkowania wewnętrznego | 🟡 | ⬜ |
| 9.17 | **Heading hierarchy audit** — H1 > H2 > H3 na każdej stronie | 🟠 | ⬜ |

#### Deliverables Fazy 9
- [ ] Yoast SEO skonfigurowany na wszystkich stronach
- [ ] Schema.org zweryfikowany (Google Rich Results Test)
- [ ] Obrazy zoptymalizowane (.avif z fallback)
- [ ] PageSpeed Mobile ≥ 85 (pre-launch target)
- [ ] DSGVO compliance (Borlabs Cookie, lokalne fonty, Impressum, Datenschutz)

#### Milestone M9: SEO & Performance Optimized
- **Termin:** Tydzień 12, Dzień 3
- **Kryteria:** PageSpeed ≥ 85 mobile, Schema OK, DSGVO OK

---

### FAZA 10: Testing & QA (Tygodnie 12-13)

> **Cel:** Kompleksowe testy jakości, cross-browser, accessibility, security  
> **Status:** ⬜ Not Started  

#### Zadania

| # | Zadanie | Priorytet | Narzędzie | Status |
|---|---------|-----------|-----------|--------|
| 10.1 | **Functional testing** — wszystkie linki, formularze, CTA | 🔴 | Playwright, manual | ⬜ |
| 10.2 | **Cross-browser testing** — Chrome, Firefox, Safari, Edge | 🔴 | BrowserStack | ⬜ |
| 10.3 | **Mobile testing** — iOS Safari, Android Chrome, responsive breakpoints | 🔴 | BrowserStack, DevTools | ⬜ |
| 10.4 | **Performance audit** — PageSpeed Insights, Lighthouse CI | 🔴 | PageSpeed, Lighthouse | ⬜ |
| 10.5 | **Accessibility audit** — WCAG 2.1 AA, axe DevTools, WAVE | 🟠 | axe, WAVE | ⬜ |
| 10.6 | **SEO audit** — Screaming Frog crawl, meta tags, broken links | 🔴 | Screaming Frog, Ahrefs | ⬜ |
| 10.7 | **Security audit** — Wordfence scan, headers, HTTPS | 🔴 | Wordfence, SecurityHeaders.com | ⬜ |
| 10.8 | **Content review** — proofreading treści DE, sprawdzenie tłumaczeń | 🟠 | Native DE speaker | ⬜ |
| 10.9 | **Bug fixing** — naprawa znalezionych błędów | 🔴 | Developer | ⬜ |
| 10.10 | **Client UAT** — prezentacja klientowi, zbieranie feedbacku | 🔴 | Screen share | ⬜ |
| 10.11 | **Final PageSpeed optimization** — target ≥ 90 mobile | 🔴 | PageSpeed Insights | ⬜ |

#### Milestone M10: QA Complete
- **Termin:** Tydzień 13, Dzień 5
- **Kryteria:** Zero critical bugs, PageSpeed ≥ 90 mobile, accessibility ≥ 90, client UAT approved

---

### FAZA 11: Deployment & Go-Live (Tydzień 14)

> **Cel:** Migracja na produkcję, konfiguracja serwera, DNS, SSL, Go-Live  
> **Status:** ⬜ Not Started  

#### Zadania

| # | Zadanie | Priorytet | Status |
|---|---------|-----------|--------|
| 11.1 | Konfiguracja serwera produkcyjnego (hosting) | 🔴 | ⬜ |
| 11.2 | SSL certificate (Let's Encrypt lub hosting) | 🔴 | ⬜ |
| 11.3 | Migracja bazy danych (dev → prod) | 🔴 | ⬜ |
| 11.4 | Migracja plików (themes, plugins, uploads) | 🔴 | ⬜ |
| 11.5 | Search & Replace URLs (dev → https://alubram.at) | 🔴 | ⬜ |
| 11.6 | DNS konfiguracja (A record → serwer produkcyjny) | 🔴 | ⬜ |
| 11.7 | WP Rocket / cache konfiguracja produkcyjna | 🟠 | ⬜ |
| 11.8 | Wordfence konfiguracja produkcyjna | 🟠 | ⬜ |
| 11.9 | Google Analytics 4 — wdrożenie tracking code | 🟠 | ⬜ |
| 11.10 | Google Search Console — weryfikacja + sitemap submission | 🔴 | ⬜ |
| 11.11 | Google Business Profile — aktualizacja URL strony | 🟡 | ⬜ |
| 11.12 | UpdraftPlus — konfiguracja automatycznych backupów | 🔴 | ⬜ |
| 11.13 | Final smoke test na produkcji | 🔴 | ⬜ |
| 11.14 | **🚀 GO-LIVE** | 🔴 | ⬜ |

#### Milestone M11: Go-Live
- **Termin:** Tydzień 14, Dzień 5
- **Kryteria:** Strona żyje na https://alubram.at, SSL OK, GA4 OK, GSC OK

---

### FAZA 12: Post-Launch & Monitoring (Tygodnie 15-16+)

> **Cel:** Monitoring, szkolenie klienta, optymalizacja, wsparcie  
> **Status:** ⬜ Not Started  

#### Zadania

| # | Zadanie | Priorytet | Status |
|---|---------|-----------|--------|
| 12.1 | Monitoring uptime (Uptime Robot) | 🟠 | ⬜ |
| 12.2 | Monitoring performance (PageSpeed weekly) | 🟠 | ⬜ |
| 12.3 | Google Analytics — setup dashboards | 🟡 | ⬜ |
| 12.4 | Szkolenie klienta — WP-Admin, edycja treści, formularze | 🔴 | ⬜ |
| 12.5 | Dokumentacja użytkownika (Przewodnik Administratora DE) | 🟠 | ⬜ |
| 12.6 | Iteracyjne poprawki (feedback klienta) | 🟡 | ⬜ |
| 12.7 | SEO monitoring — pozycje keywords (Ahrefs/SEMrush) | 🟡 | ⬜ |
| 12.8 | Content plan — harmonogram wpisów blogowych | 🟡 | ⬜ |
| 12.9 | First month report — traffic, leads, performance | 🟡 | ⬜ |

#### Milestone M12: Post-Launch Complete
- **Termin:** Tydzień 16
- **Kryteria:** Klient przeszkolony, monitoring aktywny, raport miesięczny dostarczony

---

## 9. Rekomendacje Narzędzi AI/Dev

### 9.1 Optymalny Workflow z AI

```
┌─────────────────────────────────────────────────────────────────┐
│                    AI-ASSISTED DEVELOPMENT WORKFLOW              │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  1. PLANOWANIE                                                  │
│     Claude Opus 4.6 → architektura, analiza, dokumentacja       │
│     deepseek-r1:8b → reasoning, planowanie logiki               │
│     qwen3.5:397b → copywriting SEO DE                           │
│                                                                 │
│  2. GENEROWANIE KODU                                            │
│     Claude Code → agentic coding (terminal)                     │
│     qwen3-coder-next:cloud → szablony PHP, TypeScript           │
│     codestral:latest → offline coding (12GB, szybki)            │
│     deepseek-coder-v2:16b → debugging, refaktoryzacja           │
│                                                                 │
│  3. CODE REVIEW                                                 │
│     Claude Opus 4.6 → code review, security audit               │
│     devstral-small-2:24b → szybki review, linting               │
│                                                                 │
│  4. WIZUALNA ANALIZA                                            │
│     qwen3-vl:235b-cloud → analiza screenshotów konkurencji      │
│     llava-llama3 → lokalna analiza UI                           │
│                                                                 │
│  5. TESTING / QA                                                │
│     Playwright → E2E testing, screenshoty                       │
│     Lighthouse CI → performance audity                          │
│                                                                 │
│  6. DOKUMENTACJA                                                │
│     Claude Opus → markdown docs, ARCHITECTURE.md                │
│     Repomix → pakowanie repo do kontekstu LLM                  │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

### 9.2 Dodatkowe Narzędzia — Pełna Lista Rekomendacji

| Kategoria | Narzędzie | Zastosowanie |
|-----------|-----------|-------------|
| **AI IDE** | Cursor | AI-native editor, szybki refaktoring |
| **AI IDE** | Windsurf | Flow state coding |
| **AI Terminal** | Claude Code | Agentic coding z dostępem do plików |
| **AI Terminal** | OpenCode | CLI AI-assisted coding |
| **AI Terminal** | Aider | Pair-programming z wieloma modelami |
| **VS Code Extension** | Continue.dev | Autocomplete z Ollama lokalnie |
| **VS Code Extension** | Cline | Autonomous coding agent |
| **Context Manager** | Repomix | Pakowanie repo do jednego pliku dla LLM |
| **Workflow** | n8n | Automatyzacja (self-hosted, webhooks) |
| **Testing** | Playwright | E2E testy, screenshoty, visual regression |
| **Performance** | Lighthouse CI | Automatyczne audyty w CI/CD |
| **SEO** | Screaming Frog | SEO crawler, broken links, meta audit |
| **SEO** | Ahrefs/SEMrush | Keyword tracking, backlinks, competitor analysis |
| **Design** | Figma | Wireframy, mockupy, prototypy |
| **Diagramy** | Mermaid Chart MCP | Diagramy architektoniczne, flowcharty |
| **Zdjęcia** | Unsplash | Darmowe zdjęcia stockowe do prototypowania |
| **Image Optimization** | Squoosh | Kompresja, konwersja .avif/.webp |
| **Hosting preview** | Vercel / Netlify | Szybki deploy statycznych preview |

---

## 10. KPIs i Metryki Sukcesu

### 10.1 Techniczne KPIs

| KPI | Target | Narzędzie Pomiaru |
|-----|--------|-------------------|
| **PageSpeed Mobile** | ≥ 90/100 | PageSpeed Insights |
| **PageSpeed Desktop** | ≥ 95/100 | PageSpeed Insights |
| **LCP (Largest Contentful Paint)** | < 2.5s | Chrome UX Report |
| **FID/INP (Interaction to Next Paint)** | < 100ms | Chrome UX Report |
| **CLS (Cumulative Layout Shift)** | < 0.1 | Chrome UX Report |
| **TTFB (Time to First Byte)** | < 200ms | WebPageTest |
| **Lighthouse Accessibility** | ≥ 90/100 | Lighthouse |
| **Lighthouse Best Practices** | ≥ 95/100 | Lighthouse |
| **Lighthouse SEO** | 100/100 | Lighthouse |

### 10.2 Biznesowe KPIs (Target 12 miesięcy)

| KPI | Baseline | Target | Pomiar |
|-----|----------|--------|--------|
| **Organic Traffic** | 0 | 5,000 visits/miesiąc | Google Analytics 4 |
| **Keywords Top 3** | 0 | 20 keywords | Ahrefs / SEMrush |
| **Lead Forms / miesiąc** | 0 | 50 | Form submissions |
| **Bounce Rate** | N/A | < 40% | GA4 |
| **Avg. Session Duration** | N/A | > 2:30 | GA4 |
| **Domain Rating** | 0 | 25 | Ahrefs |
| **Mobile Traffic %** | N/A | > 50% | GA4 |

---

## 11. Zarządzanie Ryzykiem

| ID | Ryzyko | Prawdopodobieństwo | Wpływ | Mitygacja |
|----|--------|---------------------|-------|-----------|
| R1 | Opóźnienia w dostarczeniu treści DE od klienta | 🟠 Wysokie | 🟠 Wysoki | Przygotować treści demo/placeholder, ustalić deadlines na treści |
| R2 | Plugin conflicts (ACF + Yoast + WP Rocket) | 🟡 Średnie | 🟠 Wysoki | Testować na staging, aktualizować sekwencyjnie |
| R3 | Performance < 90 na mobile | 🟡 Średnie | 🔴 Krytyczny | Optymalizacja iteracyjna, critical CSS, image compression |
| R4 | Problemy z DSGVO compliance | 🟡 Średnie | 🔴 Krytyczny | Borlabs Cookie, lokalne fonty, prawnik DSGVO review |
| R5 | Zmiany wymagań w trakcie developmentu | 🟠 Wysokie | 🟡 Średni | Change request process, scope freeze po fazie 2 |
| R6 | Problemy z hostingiem produkcyjnym | 🟡 Średnie | 🟠 Wysoki | Testować na staging mirror, backup plan |
| R7 | SEO nie przynosi rezultatów w 6 mies. | 🟡 Średnie | 🟡 Średni | Content marketing plan, link building strategy |

---

## 12. Harmonogram Git Flow

### 12.1 Branching Strategy

```
main          ────●────────────────────────────●── (production releases only)
                  │                            │
develop       ────●──●──●──●──●──●──●──●──●──●── (integration branch)
                  │  │           │        │
feature/      ────●──●          │        │
  theme-foundation  │          │        │
                    │          │        │
feature/            ●──●──●    │        │
  homepage                │    │        │
                          │    │        │
feature/                  ●──●──●       │
  product-pages                │       │
                               │       │
feature/                       ●──●──●──●
  seo-optimization
```

### 12.2 Konwencja Commitów (Conventional Commits)

```
feat: add hero section with parallax video
fix: correct mobile menu z-index overlap
style: update button hover effects with gold shimmer
perf: optimize homepage images to avif format
docs: update ARCHITECTURE.md with CPT schema
refactor: extract breadcrumbs to template part
test: add Playwright E2E for contact form
chore: update npm dependencies
```

### 12.3 Feature Branches

| Branch | Faza | Opis |
|--------|------|------|
| `feature/infrastructure` | 2 | Docker, repo setup |
| `feature/theme-foundation` | 3 | style.css, functions.php, header, footer |
| `feature/core-templates` | 4 | CPT, taxonomies, shortcodes |
| `feature/homepage` | 5 | front-page.php + 11 sekcji |
| `feature/product-pages` | 6 | Archiwum, single product |
| `feature/info-pages` | 7 | Über uns, Leistungen, Kontakt, Blog |
| `feature/forms-interactivity` | 8 | Formularze, AJAX, maps |
| `feature/seo-performance` | 9 | SEO, optymalizacja, DSGVO |
| `feature/qa-fixes` | 10 | Bug fixes z testów |
| `release/v1.0.0` | 11 | Pre-production release branch |

---

## 13. Checklist Pre-Launch

### ✅ Techniczny

- [ ] Wszystkie strony renderują się poprawnie (desktop + mobile + tablet)
- [ ] PageSpeed Mobile ≥ 90
- [ ] PageSpeed Desktop ≥ 95
- [ ] Core Web Vitals: LCP < 2.5s, INP < 100ms, CLS < 0.1
- [ ] Lighthouse Accessibility ≥ 90
- [ ] Lighthouse SEO = 100
- [ ] Zero broken links (Screaming Frog)
- [ ] Formularze działają (wysyłka email OK)
- [ ] 404 page custom działa
- [ ] Search działa
- [ ] SSL certificate aktywny (HTTPS)
- [ ] robots.txt poprawny
- [ ] XML Sitemap wygenerowana i zgłoszona do GSC
- [ ] Favicon + app icons ustawione
- [ ] og:image ustawiony (1200x630)

### ✅ SEO

- [ ] Każda strona ma unikalny `<title>` z keyword DE
- [ ] Każda strona ma `<meta description>` (150-160 znaków DE)
- [ ] H1 na każdej stronie (1x)
- [ ] Hierarchia H2 > H3 poprawna
- [ ] Schema.org JSON-LD na każdej stronie (LocalBusiness + per page type)
- [ ] Open Graph tags na każdej stronie
- [ ] Canonical URLs ustawione
- [ ] ALT tagi na wszystkich obrazach (DE)
- [ ] Internal linking zaimplementowany

### ✅ DSGVO / Prawo

- [ ] Borlabs Cookie Banner działa
- [ ] Google Fonts hostowane lokalnie
- [ ] Google Maps ładuje się dopiero po cookie consent
- [ ] Impressum strona istnieje z poprawnymi danymi
- [ ] Datenschutzerklärung strona istnieje
- [ ] AGB strona istnieje
- [ ] DSGVO checkbox w formularzach
- [ ] Brak ładowania external resources bez consent

### ✅ Content

- [ ] Wszystkie treści w języku niemieckim (de_AT)
- [ ] Proofreading przez native DE speaker
- [ ] Dane kontaktowe poprawne (telefon, email, adres)
- [ ] Logo SVG w header i footer
- [ ] Social media links (jeśli istnieją)
- [ ] Copyright year dynamiczny

### ✅ Deployment

- [ ] Backup bazy danych i plików
- [ ] DNS propagacja zakończona
- [ ] SSL prawidłowo skonfigurowany
- [ ] Cache wyczyszczony i przebudowany
- [ ] Google Analytics 4 tracking code wdrożony
- [ ] Google Search Console zweryfikowane
- [ ] Uptime monitoring aktywny
- [ ] Automatyczne backupy skonfigurowane

---

## 📎 Załączniki i Dokumentacja Powiązana

| Dokument | Opis |
|----------|------|
| `ARCHITECTURE.md` | Architektura techniczna motywu WordPress |
| `BRAND-SETTINGS.md` | Brand identity, kolory, typografia, logo |
| `DESIGN-SYSTEM.md` | Design system, komponenty, spacing |
| `SEO-STRATEGY-ALUBRAM.md` | Strategia SEO, keyword map, content plan |
| `TRANSLATION-GUIDE.md` | Przewodnik tłumaczeń DE |
| `PAGES-WIREFRAMES.md` | Wireframy wszystkich stron |
| `ROADMAP.md` | Timeline, milestones, risk management |
| `ROADMAP.SCHEMA.md` | Schema struktury roadmapy (YAML/JSON) |
| `BRIEF.md` | Project brief dla klienta |
| `PROJECT-SPECIFICATION.md` | Pełna specyfikacja techniczna projektu |
| `README.skills.md` | Wymagane umiejętności i poziomy |

---

> **Ostatnia aktualizacja:** 2026-03-07  
> **Wersja dokumentu:** 2.0.0  
> **Następny przegląd:** Po zakończeniu Fazy 2  

---

*ALUBRAM-GMBH-PLAN-PROJEKTU.md — Master Project Plan | ALUBRAM GMBH WordPress | v2.0.0*
