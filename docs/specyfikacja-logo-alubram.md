# specyfikacja-logo-alubram.md — ALUBRAM GMBH Logo Specification

> **Dokument:** Kompletna specyfikacja i wytyczne logo ALUBRAM GMBH
> **Projekt:** `piotroq/alubram-gmbh-wordpress`
> **Wersja:** 1.0.0 | 2026-02-26

---

## 📋 Spis Treści

1. [Wprowadzenie](#1-wprowadzenie)
2. [Architektura Systemu Logo](#2-architektura-systemu-logo)
3. [Anatomia Logo](#3-anatomia-logo)
4. [Paleta Kolorystyczna](#4-paleta-kolorystyczna)
5. [Typografia](#5-typografia)
6. [Proporcje i Clear Space](#6-proporcje-i-clear-space)
7. [Warianty Logo](#7-warianty-logo)
8. [Implementacja w WordPress](#8-implementacja-w-wordpress)
9. [Favicon i App Icons](#9-favicon-i-app-icons)
10. [Social Media & OG Images](#10-social-media--og-images)
11. [Zasady Użycia — Dos & Don'ts](#11-zasady-użycia--dos--donts)
12. [Checklist Wdrożeniowa](#12-checklist-wdrożeniowa)

---

## 1. Wprowadzenie

### 1.1 Kontekst Marki

**ALUBRAM GMBH** to austriacki producent premium aluminiowych ogrodzeń, bram, wiat garażowych (Carport) oraz zadaszeń z siedzibą w Himberg bei Wien, Austria.

**Marka komunikuje:**
- ✅ **Prestiż i jakość** — materiały premium, aluminium klasy przemysłowej
- ✅ **Solidność i trwałość** — "wartungsfrei, rostfrei, witterungsbeständig"
- ✅ **Nowoczesność** — industrialno-elegancki styl
- ✅ **Zaufanie** — producent z wieloletnim doświadczeniem

### 1.2 Cel Dokumentu

Ten dokument definiuje kompletny system identyfikacji wizualnej ALUBRAM GMBH, w tym:
- Architektura logo (wszystkie warianty)
- Specyfikacje kolorów i typografii
- Wytyczne implementacji (web, print, social)
- Zasady prawidłowego i nieprawidłowego użycia

---

## 2. Architektura Systemu Logo

### 2.1 Warianty Logo (Logo System)

| Wariant | Zastosowanie | Format | Lokalizacja |
|---------|-------------|--------|-------------|
| **Primary (Full)** | Desktop header, druki, prezentacje | SVG, PNG 2x | `assets/images/logo.svg` |
| **Compact (Icon + Name)** | Mobile header, stopka | SVG, PNG | `assets/images/logo-compact.svg` |
| **Icon Only (Monogram)** | Favicon, watermark, app icon | SVG, ICO | `assets/images/logo-icon.svg` |
| **White / Negative** | Ciemne tła, nakładki hero | SVG, PNG | `assets/images/logo-white.svg` |
| **Dark / Positive** | Jasne tła, dokumenty | SVG, PNG | `assets/images/logo-dark.svg` |
| **Gold Accent** | Certyfikaty, premium materiały | SVG | `assets/images/logo-gold.svg` |

### 2.2 Struktura Plików

```
alubramat-child/
└── assets/
    └── images/
        ├── logo.svg                    ← Primary (full color, Navy)
        ├── logo-compact.svg            ← Compact version
        ├── logo-icon.svg               ← Icon only (symbol mark)
        ├── logo-white.svg              ← Negative (white wordmark)
        ├── logo-dark.svg               ← Dark version (Deep Blue)
        ├── logo-gold.svg               ← Gold accent version
        │
        ├── favicon.ico                 ← Multi-size ICO (16, 32, 48)
        ├── favicon-16x16.png
        ├── favicon-32x32.png
        ├── apple-touch-icon.png        ← 180×180
        ├── safari-pinned-tab.svg       ← Monochrome SVG
        │
        ├── og-image.jpg                ← Open Graph 1200×630
        ├── og-image-produkt.jpg        ← Product OG 1200×630
        └── social-share.png            ← Social media 1080×1080
```

---

## 3. Anatomia Logo

### 3.1 Symbol / Icon Mark

**Koncepcja symbolu:** Geometryczny symbol nawiązujący do struktury ogrodzenia aluminiowego.

```
┌─────────────────────────────────────────┐
│                                         │
│   ┌─┬─┬─┐    ← lamelki aluminiowe      │
│   │ │ │ │      (Zaunfelder)             │
│   └─┴─┴─┘                               │
│     ╪══╪      ← słupek / profil         │
│               (Pfosten)                  │
│                                         │
└─────────────────────────────────────────┘
```

**Cechy symbolu:**
- ✅ Ostre, precyzyjne kąty — brak zaokrągleń (odzwierciedla obróbkę metalu)
- ✅ Rytmika pionowych elementów — nawiązanie do lamelki ogrodzeniowej
- ✅ Proporcja: `1:1` lub `1:1.2` (zbliżona do kwadratu)
- ✅ Grubość linii: `2px` przy 32px, `3px` przy 64px, skalowalna (stroke, nie fill)

### 3.2 Wordmark — Nazwa Firmowa

```
ALUBRAM
GMBH
```

**Specyfikacja wordmarku:**

| Element | Specyfikacja |
|---------|-------------|
| **Font** | `Montserrat` — weight **800 (ExtraBold)** |
| **Tracking** | `+100` (szerokie — premium feel) |
| **Case** | `ALL CAPS` — buduje autorytet i siłę marki |
| **Linia 1 (`ALUBRAM`)** | Większa — główna nazwa |
| **Linia 2 (`GMBH`)** | 60-65% rozmiaru linii 1, `font-weight: 500` |
| **Kolor primary** | `#1A1A2E` (Dark Navy) na jasnym tle |
| **Kolor negative** | `#FFFFFF` na ciemnym tle |
| **Kolor gold** | `#C8A96E` — wariant premium/akcentowy |

### 3.3 Tagline (Opcjonalny)

```
Ihr Aluminium-Spezialist aus Österreich
```

lub krócej:

```
Premium Aluminium · Direkt vom Hersteller
```

**Specyfikacja tagline:**
- Font: `Inter` lub `Montserrat` — `font-weight: 400`
- Rozmiar: 35-40% rozmiaru wordmarku
- Kolor: `#9E9E9E` (gray-500) lub `#C8A96E` (gold)
- Odstęp od wordmarku: `8-12px`

---

## 4. Paleta Kolorystyczna

### 4.1 Kolory Logo

| Nazwa | HEX | RGB | CMYK | Zastosowanie |
|-------|-----|-----|------|-------------|
| **Primary Navy** | `#1A1A2E` | 26, 26, 46 | 95, 90, 60, 55 | Wordmark, symbol — jasne tła |
| **Gold / Champagne** | `#C8A96E` | 200, 169, 110 | 25, 30, 65, 5 | Akcent, separator, premium |
| **Dark Gold** | `#A07840` | 160, 120, 64 | 35, 45, 75, 20 | Hover state, shadow logo |
| **White** | `#FFFFFF` | 255, 255, 255 | 0, 0, 0, 0 | Negative logo — ciemne tła |
| **Deep Blue** | `#0F3460` | 15, 52, 96 | 95, 75, 20, 45 | Alternatywna wersja |

### 4.2 Kombinacje Logo vs Tło

```
✅ DOZWOLONE:
┌─────────────────────────────────────────────────────────────┐
│ Tło                          │ Logo         │ Contrast     │
├──────────────────────────────┼──────────────┼──────────────┤
│ White (#FFFFFF)              │ Navy         │ 16.1:1 ✓ AAA │
│ Off-White (#F8F6F1)          │ Navy         │ 15.2:1 ✓ AAA │
│ Dark Navy (#1A1A2E)          │ White        │ 16.1:1 ✓ AAA │
│ Deep Blue (#0F3460)          │ White        │  9.4:1 ✓ AAA │
│ Dark Navy (#1A1A2E)          │ Gold         │  5.8:1 ✓ AA  │
│ Zdjęcie z overlay (opacity ≥ 0.65) │ White │ - ✓         │
└─────────────────────────────────────────────────────────────┘

❌ ZABRONIONE:
┌─────────────────────────────────────────────────────────────┐
│ Tło                          │ Logo         │ Contrast     │
├──────────────────────────────┼──────────────┼──────────────┤
│ Dark (#0D0D0D)               │ Navy         │ Nieczytelne  │
│ White (#FFFFFF)              │ Gold         │  2.4:1 ✗ FAIL│
│ Light Gray (#F5F5F5)         │ Gold         │  2.3:1 ✗ FAIL│
│ Kolorowe tła (bez overlay)   │ Dowolne      │ - ✗         │
└─────────────────────────────────────────────────────────────┘
```

### 4.3 Gradienty Brandowe

```css
/* Gradient Primary (Navy → Blue) */
--gradient-primary: linear-gradient(135deg, #1A1A2E 0%, #0F3460 100%);

/* Gradient Gold (Champagne) */
--gradient-gold: linear-gradient(135deg, #C8A96E 0%, #E8D5A3 50%, #A07840 100%);

/* Gradient Overlay (Hero) */
--gradient-overlay: linear-gradient(180deg, rgba(26,26,46,0.4) 0%, rgba(26,26,46,0.85) 100%);

/* Gradient Hero */
--gradient-hero: linear-gradient(135deg, rgba(15,52,96,0.9) 0%, rgba(26,26,46,0.95) 100%);
```

---

## 5. Typografia

### 5.1 Font Stack

```css
/* Heading / Wordmark */
--font-heading: 'Montserrat', 'Raleway', 'Arial', sans-serif;

/* Body Text */
--font-body: 'Inter', 'Open Sans', 'Helvetica Neue', sans-serif;

/* Accent / Tagline */
--font-accent: 'Playfair Display', 'Georgia', serif;
```

### 5.2 Google Fonts Import

```html
<!-- Preconnect -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>

<!-- Font Import -->
<link href="https://fonts.googleapis.com/css2?
  family=Montserrat:ital,wght@0,400;0,500;0,600;0,700;0,800;0,900;1,400&
  family=Inter:wght@300;400;500;600;700&
  family=Playfair+Display:ital,wght@0,400;0,700;1,400&
  display=swap" rel="stylesheet">
```

> ⚠️ **DSGVO Compliance:** W produkcji Google Fonts MUSI być hostowany lokalnie.
> Narzędzie: [google-webfonts-helper.herokuapp.com](https://google-webfonts-helper.herokuapp.com/fonts)

### 5.3 Wordmark Typography

```css
/* ALUBRAM (Line 1) */
.alubram-wordmark-primary {
    font-family: 'Montserrat', sans-serif;
    font-weight: 800;
    font-size: 48px;        /* Desktop header */
    letter-spacing: 0.1em;  /* +100 tracking */
    text-transform: uppercase;
    color: #1A1A2E;         /* Dark Navy */
}

/* GMBH (Line 2) */
.alubram-wordmark-secondary {
    font-family: 'Montserrat', sans-serif;
    font-weight: 500;
    font-size: 28px;        /* 60% of primary */
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: #1A1A2E;
}

/* Mobile scaling */
@media (max-width: 768px) {
    .alubram-wordmark-primary { font-size: 32px; }
    .alubram-wordmark-secondary { font-size: 18px; }
}
```

---

## 6. Proporcje i Clear Space

### 6.1 Strefa Ochronna (Clear Space)

```
Minimalna strefa ochronna = 1× wysokość litery "A" z wordmarku

┌────────────────────────────────────────────────────────┐
│  ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░  │  ← min. 1x
│  ░░░                                                ░░░  │
│  ░░░   [SYMBOL]    A L U B R A M                    ░░░  │
│  ░░░                  G M B H                        ░░░  │
│  ░░░                                                ░░░  │
│  ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░  │  ← min. 1x
└────────────────────────────────────────────────────────┘
       ↑                                          ↑
    min. 1x                                    min. 1x
```

### 6.2 Minimalne Rozmiary Logo

| Kontekst | Min. Szerokość | Format | Plik |
|---------|---------------|--------|------|
| Favicon (browser tab) | 16×16 px | `.ico` lub `.png` | `favicon.ico` |
| Favicon (HD) | 32×32 px | `.png` | `favicon-32x32.png` |
| Apple Touch Icon | 180×180 px | `.png` | `apple-touch-icon.png` |
| Mobile header | 120 px szer. | SVG | `logo-compact.svg` |
| Desktop header | 180-220 px szer. | SVG | `logo.svg` |
| Druk (wizytówka) | 40 mm szer. | SVG / PDF | `logo-print.svg` |
| Billbord/banner | bez ograniczeń | SVG | `logo.svg` |

### 6.3 Proporcje Logo

```
Primary Logo (Full):
┌────────────────────────────────────────────┐
│                                            │
│  [SYMBOL]    A L U B R A M                 │
│              G M B H                       │
│                                            │
└────────────────────────────────────────────┘
     ↑                    ↑
  25% width          75% width

Aspect Ratio: 1 : 0.4 (height : width)
```

---

## 7. Warianty Logo

### 7.1 Primary Logo (Full Color)

**Zastosowanie:** Desktop header, strona główna, materiały drukowane

```svg
<!-- logo.svg -->
<svg viewBox="0 0 400 160" xmlns="http://www.w3.org/2000/svg">
  <!-- Symbol -->
  <g id="symbol" fill="none" stroke="#1A1A2E" stroke-width="3">
    <rect x="20" y="40" width="80" height="80" rx="2"/>
    <!-- Lamelki -->
    <line x1="40" y1="50" x2="40" y2="110"/>
    <line x1="60" y1="50" x2="60" y2="110"/>
    <line x1="80" y1="50" x2="80" y2="110"/>
  </g>
  
  <!-- Wordmark -->
  <text x="120" y="80" font-family="Montserrat" font-weight="800" 
        font-size="48" fill="#1A1A2E" letter-spacing="4">ALUBRAM</text>
  <text x="120" y="110" font-family="Montserrat" font-weight="500" 
        font-size="28" fill="#1A1A2E" letter-spacing="6">GMBH</text>
</svg>
```

### 7.2 White Logo (Negative)

**Zastosowanie:** Ciemne tła, hero section z overlay, stopka

```svg
<!-- logo-white.svg -->
<svg viewBox="0 0 400 160" xmlns="http://www.w3.org/2000/svg">
  <!-- Symbol -->
  <g id="symbol" fill="none" stroke="#FFFFFF" stroke-width="3">
    <rect x="20" y="40" width="80" height="80" rx="2"/>
    <!-- Lamelki -->
    <line x1="40" y1="50" x2="40" y2="110"/>
    <line x1="60" y1="50" x2="60" y2="110"/>
    <line x1="80" y1="50" x2="80" y2="110"/>
  </g>
  
  <!-- Wordmark -->
  <text x="120" y="80" font-family="Montserrat" font-weight="800" 
        font-size="48" fill="#FFFFFF" letter-spacing="4">ALUBRAM</text>
  <text x="120" y="110" font-family="Montserrat" font-weight="500" 
        font-size="28" fill="#FFFFFF" letter-spacing="6">GMBH</text>
</svg>
```

### 7.3 Gold Logo (Accent)

**Zastosowanie:** Premium materials, certyfikaty, special editions

```svg
<!-- logo-gold.svg -->
<svg viewBox="0 0 400 160" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <linearGradient id="goldGradient" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" style="stop-color:#C8A96E"/>
      <stop offset="50%" style="stop-color:#E8D5A3"/>
      <stop offset="100%" style="stop-color:#A07840"/>
    </linearGradient>
  </defs>
  
  <!-- Symbol -->
  <g id="symbol" fill="none" stroke="url(#goldGradient)" stroke-width="3">
    <rect x="20" y="40" width="80" height="80" rx="2"/>
    <!-- Lamelki -->
    <line x1="40" y1="50" x2="40" y2="110"/>
    <line x1="60" y1="50" x2="60" y2="110"/>
    <line x1="80" y1="50" x2="80" y2="110"/>
  </g>
  
  <!-- Wordmark -->
  <text x="120" y="80" font-family="Montserrat" font-weight="800" 
        font-size="48" fill="url(#goldGradient)" letter-spacing="4">ALUBRAM</text>
  <text x="120" y="110" font-family="Montserrat" font-weight="500" 
        font-size="28" fill="url(#goldGradient)" letter-spacing="6">GMBH</text>
</svg>
```

### 7.4 Icon Only (Monogram)

**Zastosowanie:** Favicon, watermark, social media profile pictures

```svg
<!-- logo-icon.svg -->
<svg viewBox="0 0 120 120" xmlns="http://www.w3.org/2000/svg">
  <rect x="10" y="10" width="100" height="100" rx="4" fill="#1A1A2E"/>
  <g fill="none" stroke="#C8A96E" stroke-width="3">
    <!-- Lamelki -->
    <line x1="35" y1="30" x2="35" y2="90"/>
    <line x1="55" y1="30" x2="55" y2="90"/>
    <line x1="75" y1="30" x2="75" y2="90"/>
    <!-- Pfosten -->
    <line x1="30" y1="95" x2="80" y2="95" stroke-width="4"/>
  </g>
</svg>
```

---

## 8. Implementacja w WordPress

### 8.1 Rejestracja Logo w functions.php

```php
<?php
/**
 * Register custom logo support
 * @package alubramat-child
 */

add_theme_support('custom-logo', [
    'height'               => 80,
    'width'                => 220,
    'flex-height'          => true,
    'flex-width'           => true,
    'header-text'          => ['site-title', 'site-description'],
    'unlink-homepage-logo' => false,
]);
```

### 8.2 Header.php — Logo Output

```php
<?php
/**
 * Logo output in header with scroll-based variant switching
 * @package alubramat-child
 */

$logo_primary = get_stylesheet_directory_uri() . '/assets/images/logo.svg';
$logo_white   = get_stylesheet_directory_uri() . '/assets/images/logo-white.svg';
$logo_icon    = get_stylesheet_directory_uri() . '/assets/images/logo-icon.svg';
?>

<header id="site-header" class="site-header" role="banner">
    <div class="alubram-container">
        <a href="<?php echo esc_url(home_url('/')); ?>"
           class="alubram-logo"
           aria-label="<?php esc_attr_e('ALUBRAM GMBH – Zur Startseite', 'alubramat-child'); ?>">
            
            <!-- White logo (visible on transparent/hero) -->
            <img src="<?php echo esc_url($logo_white); ?>"
                 class="logo-white"
                 alt="ALUBRAM GMBH Logo – Hersteller für Aluminiumzäune und Tore in Österreich"
                 width="200"
                 height="60"
                 fetchpriority="high"
                 decoding="async">
            
            <!-- Color logo (visible on solid header after scroll) -->
            <img src="<?php echo esc_url($logo_primary); ?>"
                 class="logo-color"
                 alt="ALUBRAM GMBH Logo – Aluminiumzaun Hersteller Österreich"
                 width="200"
                 height="60"
                 fetchpriority="high"
                 decoding="async">
        </a>
        
        <!-- Mobile icon logo -->
        <a href="<?php echo esc_url(home_url('/')); ?>"
           class="alubram-logo-mobile"
           aria-label="<?php esc_attr_e('ALUBRAM GMBH – Zur Startseite', 'alubramat-child'); ?>">
            <img src="<?php echo esc_url($logo_icon); ?>"
                 alt="ALUBRAM GMBH"
                 width="48"
                 height="48">
        </a>
    </div>
</header>
```

### 8.3 CSS — Scroll-based Logo Switching

```css
/* alubramat-child/assets/css/custom/components.css */

.alubram-logo {
    display: inline-flex;
    align-items: center;
    text-decoration: none;
    flex-shrink: 0;
}

.alubram-logo img {
    height: 48px;
    width: auto;
    max-width: 200px;
    transition: opacity 0.3s ease, transform 0.3s ease;
}

/* ── Default state (transparent header — over hero) ── */
.site-header .logo-white  { opacity: 1; position: static; }
.site-header .logo-color  { opacity: 0; position: absolute; }

/* ── After scroll (solid header) ── */
.site-header.is-scrolled .logo-white { opacity: 0; position: absolute; }
.site-header.is-scrolled .logo-color  { opacity: 1; position: static; }

/* ── Mobile: always color logo ── */
@media (max-width: 767px) {
    .site-header .logo-white { opacity: 0; position: absolute; }
    .site-header .logo-color  { opacity: 1; position: static; }
    
    .alubram-logo { display: none; }
    .alubram-logo-mobile { display: inline-flex; }
}

/* ── Hover effect ── */
.alubram-logo:hover img {
    transform: scale(1.02);
}
```

### 8.4 JavaScript — Sticky Header Toggle

```typescript
// assets/ts/main.ts
/**
 * Sticky header with logo switching
 */

export function initStickyHeader(): void {
    const header = document.getElementById('site-header');
    if (!header) return;

    let lastScrollY = window.scrollY;
    const scrollThreshold = 80;

    window.addEventListener('scroll', () => {
        const currentScrollY = window.scrollY;

        if (currentScrollY > scrollThreshold) {
            header.classList.add('is-scrolled');
        } else {
            header.classList.remove('is-scrolled');
        }

        lastScrollY = currentScrollY;
    }, { passive: true });
}

// Initialize
document.addEventListener('DOMContentLoaded', initStickyHeader);
```

### 8.5 Favicon Hook — wp_head

```php
<?php
/**
 * Add favicon and app icons to wp_head
 * @package alubramat-child
 */

add_action('wp_head', function(): void {
    $assets = get_stylesheet_directory_uri() . '/assets/images';
    ?>
    <!-- Favicon -->
    <link rel="icon" type="image/x-icon" href="<?php echo esc_url($assets . '/favicon.ico'); ?>">
    <link rel="icon" type="image/png" sizes="32x32" href="<?php echo esc_url($assets . '/favicon-32x32.png'); ?>">
    <link rel="icon" type="image/png" sizes="16x16" href="<?php echo esc_url($assets . '/favicon-16x16.png'); ?>">
    
    <!-- Apple Touch Icon -->
    <link rel="apple-touch-icon" sizes="180x180" href="<?php echo esc_url($assets . '/apple-touch-icon.png'); ?>">
    
    <!-- Safari Pinned Tab -->
    <link rel="mask-icon" href="<?php echo esc_url($assets . '/safari-pinned-tab.svg'); ?>" color="#C8A96E">
    
    <!-- Theme Color -->
    <meta name="theme-color" content="#1A1A2E">
    <meta name="msapplication-TileColor" content="#1A1A2E">
    <?php
}, 1);
```

---

## 9. Favicon i App Icons

### 9.1 Required Files

| Plik | Rozmiar | Format | Zastosowanie |
|------|---------|--------|-------------|
| `favicon.ico` | 16×16, 32×32, 48×48 | ICO | Multi-size favicon |
| `favicon-16x16.png` | 16×16 | PNG | Browser tab (small) |
| `favicon-32x32.png` | 32×32 | PNG | Browser tab (standard) |
| `apple-touch-icon.png` | 180×180 | PNG | iOS home screen |
| `safari-pinned-tab.svg` | Any (vector) | SVG | Safari pinned tab |
| `android-chrome-192.png` | 192×192 | PNG | Android home screen |
| `android-chrome-512.png` | 512×512 | PNG | Android splash |

### 9.2 Favicon Design Specification

```
┌─────────────────────────────────────────┐
│                                         │
│         ┌─────────────────┐             │
│         │                 │             │
│         │   [SYMBOL]      │             │
│         │   (centered)    │             │
│         │                 │             │
│         └─────────────────┘             │
│                                         │
│  Background: #1A1A2E (Dark Navy)        │
│  Symbol: #C8A96E (Gold)                 │
│                                         │
└─────────────────────────────────────────┘
```

### 9.3 HTML Head Implementation

```html
<head>
    <!-- Standard favicon -->
    <link rel="icon" href="/favicon.ico" sizes="any">
    <link rel="icon" href="/favicon.svg" type="image/svg+xml">
    
    <!-- Apple touch icon -->
    <link rel="apple-touch-icon" href="/apple-touch-icon.png">
    
    <!-- Safari pinned tab -->
    <link rel="mask-icon" href="/safari-pinned-tab.svg" color="#C8A96E">
    
    <!-- Android / Chrome -->
    <link rel="icon" type="image/png" sizes="32x32" href="/favicon-32x32.png">
    <link rel="icon" type="image/png" sizes="16x16" href="/favicon-16x16.png">
    <link rel="icon" type="image/png" sizes="192x192" href="/android-chrome-192.png">
    <link rel="icon" type="image/png" sizes="512x512" href="/android-chrome-512.png">
    
    <!-- Manifest for PWA -->
    <link rel="manifest" href="/site.webmanifest">
    
    <!-- Theme color -->
    <meta name="theme-color" content="#1A1A2E">
</head>
```

---

## 10. Social Media & OG Images

### 10.1 Open Graph Image Specification

**Rozmiar:** 1200 × 630 px (1.91:1 aspect ratio)

```
┌──────────────────────────────────────────────────────────────┐
│                                                              │
│  Tło: gradient #1A1A2E → #0F3460                            │
│                                                              │
│            [LOGO WHITE — szerokość 320px]                    │
│                                                              │
│   „Premium Aluminiumzäune · Tore · Carports"                 │
│   (Inter 700, 48px, White)                                   │
│                                                              │
│        alubram.at          +43 223 584 793                   │
│        (Inter 400, 24px, Gold #C8A96E)                       │
│                                                              │
└──────────────────────────────────────────────────────────────┘
```

### 10.2 Platform-Specific Images

| Platforma | Rozmiar | Format | Plik |
|-----------|---------|--------|------|
| **Facebook / Meta OG** | 1200×630 | JPG/WEBP | `og-image.jpg` |
| **LinkedIn** | 1200×627 | JPG | `og-image.jpg` |
| **Twitter/X Card** | 1200×600 | JPG | `twitter-card.jpg` |
| **WhatsApp** | 400×400 | JPG | `social-share.png` |
| **Google Business** | 720×720 min | JPG | `gbp-cover.jpg` |
| **Email Signature** | 240×72 | PNG | `email-logo.png` |

### 10.3 OG Tags Implementation

```php
<?php
/**
 * Add Open Graph meta tags to wp_head
 * @package alubramat-child
 */

add_action('wp_head', function(): void {
    global $post;
    
    $site_name = get_bloginfo('name');
    $site_desc = get_bloginfo('description');
    $og_image = get_stylesheet_directory_uri() . '/assets/images/og-image.jpg';
    
    // Default values
    $og_title = $site_name;
    $og_description = $site_desc;
    $og_url = home_url();
    $og_type = 'website';
    
    // Single post/page
    if (is_singular()) {
        $og_title = get_the_title();
        $og_description = get_the_excerpt();
        $og_url = get_permalink();
        $og_type = 'article';
        
        // Post thumbnail
        if (has_post_thumbnail()) {
            $og_image = get_the_post_thumbnail_url(get_the_ID(), 'full');
        }
    }
    ?>
    
    <!-- Open Graph -->
    <meta property="og:locale" content="de_AT">
    <meta property="og:type" content="<?php echo esc_attr($og_type); ?>">
    <meta property="og:title" content="<?php echo esc_attr($og_title); ?>">
    <meta property="og:description" content="<?php echo esc_attr($og_description); ?>">
    <meta property="og:url" content="<?php echo esc_url($og_url); ?>">
    <meta property="og:site_name" content="<?php echo esc_attr($site_name); ?>">
    <meta property="og:image" content="<?php echo esc_url($og_image); ?>">
    <meta property="og:image:width" content="1200">
    <meta property="og:image:height" content="630">
    
    <!-- Twitter Card -->
    <meta name="twitter:card" content="summary_large_image">
    <meta name="twitter:title" content="<?php echo esc_attr($og_title); ?>">
    <meta name="twitter:description" content="<?php echo esc_attr($og_description); ?>">
    <meta name="twitter:image" content="<?php echo esc_url($og_image); ?>">
    
    <?php
}, 5);
```

---

## 11. Zasady Użycia — Dos & Don'ts

### 11.1 ✅ Prawidłowe Użycie

```
✅ Używaj wyłącznie plików SVG z repozytorium (assets/images/)
✅ Zachowuj proporcje logo — object-fit: contain
✅ Stosuj właściwą wersję logo do tła (Navy/White/Gold)
✅ Na tle zdjęciowym używaj logo-white.svg z overlay min. rgba(0,0,0,0.5)
✅ Skaluj logo proporcjonalnie (width: auto przy ustalonej height)
✅ Minimalna szerokość: 120px (czytelność wordmarku)
✅ Kontrast logo vs tło: ≥ 4.5:1 (WCAG AA)
✅ fetchpriority="high" na logo w headerze
✅ Alt text po niemiecku: "ALUBRAM GMBH Logo – Hersteller für Aluminiumzäune"
```

### 11.2 ❌ Błędy do Unikania

```
❌ Rozciąganie / deformowanie proporcji logo
❌ Zmiana kolorów logo poza zdefiniowanym systemem
❌ Dodawanie cienia, glow, emboss (wyjątek: lekki drop-shadow na hero)
❌ Umieszczanie logo na pstrokatych, tęczowych tłach
❌ Używanie pliku .png na dużych rozmiarach zamiast SVG
❌ Logo poniżej 120px szerokości (nieczytelny wordmark)
❌ Rotowanie lub pochylanie (skewing) logo
❌ Logo ze starym brandingiem / poprzednie wersje
❌ Logo jako wypełnienie animacji (nieustanne animowanie pulsem)
❌ Zmiana fontu wordmarku (zawsze Montserrat 800)
❌ Zmiana letter-spacing (zawsze +100)
❌ Użycie gold logo na białym tle (contrast fail)
```

### 11.3 Przykłady Wizualne

```
┌─────────────────────────────────────────────────────────────┐
│                    ✅ CORRECT EXAMPLES                      │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  [Logo Navy on White]    [Logo White on Navy]              │
│  Contrast: 16.1:1 ✓      Contrast: 16.1:1 ✓                │
│                                                             │
│  [Logo White on Photo + Overlay]                           │
│  Overlay opacity: 0.65 ✓                                   │
│                                                             │
└─────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────┐
│                    ❌ WRONG EXAMPLES                        │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  [Logo Gold on White]    [Logo Navy on Black]              │
│  Contrast: 2.4:1 ✗       Unreadable ✗                      │
│                                                             │
│  [Stretched Logo]        [Rotated Logo]                    │
│  Deformed ✗            Wrong orientation ✗                 │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## 12. Checklist Wdrożeniowa

### 12.1 Pre-Launch Checklist

```
LOGO FILES
□ logo.svg — Primary (full color, Navy)
□ logo-white.svg — Negative (white wordmark + symbol)
□ logo-compact.svg — Compact version for mobile
□ logo-icon.svg — Icon only (symbol mark)
□ logo-dark.svg — Dark version (Deep Blue)
□ logo-gold.svg — Gold accent version

FAVICON & APP ICONS
□ favicon.ico — Multi-size (16, 32, 48px)
□ favicon-16x16.png
□ favicon-32x32.png
□ apple-touch-icon.png — 180×180px
□ safari-pinned-tab.svg — Monochrome
□ android-chrome-192.png
□ android-chrome-512.png

SOCIAL MEDIA
□ og-image.jpg — 1200×630px (Facebook, LinkedIn)
□ twitter-card.jpg — 1200×600px
□ social-share.png — 1080×1080px
□ gbp-cover.jpg — 720×720px (Google Business Profile)

WORDPRESS IMPLEMENTATION
□ add_theme_support('custom-logo') — functions.php
□ Logo output in header.php — with scroll switching
□ CSS for logo variants — components.css
□ JavaScript for sticky header — main.ts
□ Favicon hook — wp_head
□ Alt text in German — all logo img tags
□ fetchpriority="high" — header logo

QUALITY CHECK
□ Logo displays correctly on all devices
□ Logo switches on scroll (white ↔ color)
□ Mobile shows compact/icon logo
□ All logo variants have proper alt text
□ Contrast ratio ≥ 4.5:1 (WCAG AA)
□ SVG files are optimized (< 50KB each)
□ Favicon displays in all browsers
□ OG image displays correctly on social media
```

### 12.2 Print Materials Checklist

```
BUSINESS CARD
□ Logo in correct colors (Navy or Gold)
□ Clear space maintained
□ Minimum size: 40mm width
□ File format: SVG or PDF (vector)

LETTERHEAD
□ Logo positioned top-left or center
□ Clear space: 20mm from edges
□ Company info aligned with logo

EMAIL SIGNATURE
□ Logo: 240×72px (PNG @ 2x)
□ Alt text included
□ Links to website

VEHICLE BRANDING
□ Logo in vector format (SVG/EPS)
□ Colors: Navy or White (depending on vehicle color)
□ Minimum size: 500mm width

BILLBOARD / BANNER
□ Logo in vector format
□ High contrast with background
□ Minimum size: 2000mm width
□ Clear space: 500mm from edges
```

---

*specyfikacja-logo-alubram.md — ALUBRAM GMBH WordPress Project | v1.0.0 | 2026-02-26*
