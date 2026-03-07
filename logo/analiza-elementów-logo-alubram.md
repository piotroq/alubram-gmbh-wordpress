# Analiza Elementów Logo — ALUBRAM GMBH

> **Dokument:** Analiza brandingowa i wytyczne implementacji logo  
> **Projekt:** alubram-gmbh-wordpress  
> **Wersja:** 1.0.0  
> **Data:** 2026-02-26  
> **Autor:** Senior UI/UX Designer — alubramat-child team  

---

## 1. Kontekst Marki

**ALUBRAM GMBH** to austriacki producent aluminiowych ogrodzeń, bram, wiat garażowych (Carport) oraz zadaszenia z siedzibą w Himberg bei Wien. Marka pozycjonuje się jako **premium manufacturer** na rynku DACH — bezpośredni producent, bez pośredników, z gwarancją dostawy w 3–6 tygodni.

Logo musi komunikować:
- **Prestiż i jakość** — materiały premium, aluminium klasy przemysłowej
- **Solidność i trwałość** — „wartungsfrei, rostfrei, witterungsbeständig"
- **Nowoczesność** — industrialno-elegancki styl
- **Zaufanie** — producent z wieloletnim doświadczeniem

---

## 2. Rekomendowana Architektura Logo

### 2.1 Warianty logo (logo system)

| Wariant | Zastosowanie | Format |
|---------|-------------|--------|
| **Primary (Full)** | Desktop header, druki, prezentacje | SVG, PNG 2x |
| **Compact (Icon + Name)** | Mobile header, favicon area | SVG, PNG |
| **Icon Only (Monogram)** | Favicon 32px, app icon, watermark | SVG, ICO |
| **White / Negative** | Ciemne tła, nakładki hero | SVG, PNG |
| **Dark / Positive** | Jasne tła, dokumenty | SVG, PNG |
| **Gold Accent** | Certyfikaty, premium materiały | SVG |

---

## 3. Anatomia Logo — Elementy Składowe

### 3.1 Symbol / Icon Mark

**Rekomendacja:** Geometryczny symbol nawiązujący do struktury ogrodzenia aluminiowego.

```
Koncepcja symbolu:
  ┌─┬─┬─┐    ← lamelki aluminiowe (Zaunfelder)
  │ │ │ │
  └─┴─┴─┘
    ╪══╪      ← słupek / profil (Pfosten)
```

**Cechy symbolu:**
- Ostre, precyzyjne kąty — brak zaokrągleń (odzwierciedla obróbkę metalu)
- Rytmika pionowych elementów — nawiązanie do lamelki ogrodzeniowej
- Proporcja: `1:1` lub `1:1.2` (zbliżona do kwadratu)
- Grubość linii: `2px` przy 32px, `3px` przy 64px, skalowalna (stroke, nie fill dla elastyczności)

### 3.2 Wordmark — Nazwa Firmowa

```
ALUBRAM
GMBH
```

**Typografia wordmarku:**

| Element | Specyfikacja |
|---------|-------------|
| Font | `Montserrat` — weight **700 (Bold)** lub **800 (ExtraBold)** |
| Tracking (letter-spacing) | `+80 do +120` (szerokie — premium feel) |
| Case | `ALL CAPS` — buduje autorytety i siłę marki |
| Linia 1 (`ALUBRAM`) | Większa — główna nazwa |
| Linia 2 (`GMBH`) | 60–65% rozmiaru linii 1, `font-weight: 400/500` |
| Kolor primary | `#1A1A2E` (Dark Navy) na jasnym tle |
| Kolor negative | `#FFFFFF` na ciemnym tle |
| Kolor gold | `#C8A96E` — wariant premium/akcentowy |

**Alternatywna typografia** (jeżeli Montserrat za geometryczna):
- `Raleway` 700 — elegantszy, bardziej „branded"
- `Bebas Neue` — mocny, industrialny (tylko header, bez `GMBH` subtext)

### 3.3 Tagline (opcjonalny element pod logo)

```
Ihr Aluminium-Spezialist aus Österreich
```

lub krócej:

```
Premium Aluminium · Direkt vom Hersteller
```

**Specyfikacja tagline:**
- Font: `Inter` lub `Montserrat` — `font-weight: 400`
- Rozmiar: 35–40% rozmiaru wordmarku
- Kolor: `#9E9E9E` (gray-500) lub `#C8A96E` (gold)
- Odstęp od wordmarku: `8–12px`

---

## 4. Paleta Kolorystyczna Logo

### 4.1 Kolory Logo

| Nazwa | HEX | RGB | Zastosowanie |
|-------|-----|-----|-------------|
| **Primary Navy** | `#1A1A2E` | rgb(26, 26, 46) | Wordmark, symbol — jasne tła |
| **Gold / Champagne** | `#C8A96E` | rgb(200, 169, 110) | Akcent, separator, premium wariant |
| **Dark Gold** | `#A07840` | rgb(160, 120, 64) | Hover state, shadow logo |
| **White** | `#FFFFFF` | rgb(255, 255, 255) | Negative logo — ciemne tła |
| **Deep Blue** | `#0F3460` | rgb(15, 52, 96) | Alternatywna wersja na jasnych tłach |

### 4.2 Kombinacje Logo vs Tło

```
✅ DOZWOLONE:
  Logo Navy (#1A1A2E) na tle White (#FFFFFF)       → contrast ratio: 16.1:1 ✓ AAA
  Logo Navy (#1A1A2E) na tle Off-White (#F8F6F1)   → contrast ratio: 15.2:1 ✓ AAA
  Logo White (#FFFFFF) na tle Navy (#1A1A2E)        → contrast ratio: 16.1:1 ✓ AAA
  Logo White (#FFFFFF) na tle Deep Blue (#0F3460)   → contrast ratio:  9.4:1 ✓ AAA
  Logo Gold (#C8A96E) na tle Navy (#1A1A2E)         → contrast ratio:  5.8:1 ✓ AA
  Logo White (#FFFFFF) na zdjęciu z overlay         → overlay opacity min. 0.65

❌ ZABRONIONE:
  Logo Navy na tle Dark (#0D0D0D)                   → nieczytelne
  Logo Gold na tle White                            → contrast ratio: 2.4:1 ✗ FAIL
  Logo Gold na tle Light Gray (#F5F5F5)             → contrast ratio: 2.3:1 ✗ FAIL
  Logo z efektem cienia drop-shadow (wyjątek: hero overlay)
  Logo w kolorach innych niż zdefiniowane powyżej
```

---

## 5. Proporcje i Clear Space

### 5.1 Strefa ochronna (clear space)

```
Minimalna strefa ochronna = 1× wysokość litery „A" z wordmarku

┌────────────────────────────────────────┐
│  ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░  │  ← min. 1x
│  ░░░  [SYMBOL]  ALUBRAM  ░░░░░░░░░░  │
│  ░░░             GMBH    ░░░░░░░░░░  │
│  ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░  │  ← min. 1x
└────────────────────────────────────────┘
```

### 5.2 Minimalne rozmiary logo

| Kontekst | Min. szerokość | Format |
|---------|---------------|--------|
| Favicon (browser tab) | 16×16 px | `.ico` lub `.png` |
| Favicon (HD) | 32×32 px | `.png` |
| Apple Touch Icon | 180×180 px | `.png` |
| Mobile header | 120 px szer. | SVG |
| Desktop header | 180–220 px szer. | SVG |
| Druk (wizytówka) | 40 mm szer. | SVG / PDF wektorowy |
| Billbord/banner | bez ograniczeń | SVG |

---

## 6. Implementacja w WordPress — alubramat-child

### 6.1 Plik logo SVG — lokalizacja

```
alubramat-child/
└── assets/
    └── images/
        ├── logo.svg                ← Primary (full color, Navy)
        ├── logo-white.svg          ← Negative (white wordmark + symbol)
        ├── logo-gold.svg           ← Gold accent variant
        ├── logo-icon.svg           ← Icon only (symbol mark)
        ├── logo-dark.svg           ← Dark tła (Deep Blue)
        ├── favicon.ico             ← Multi-size ICO (16, 32, 48)
        ├── favicon-32x32.png
        ├── favicon-16x16.png
        ├── apple-touch-icon.png    ← 180×180
        ├── og-image.jpg            ← Open Graph 1200×630 (z logo)
        └── safari-pinned-tab.svg   ← Monochrome SVG
```

### 6.2 Rejestracja logo w WordPress — functions.php

```php
<?php
// alubramat-child/inc/nav-menus.php

add_theme_support('custom-logo', [
    'height'               => 80,
    'width'                => 220,
    'flex-height'          => true,
    'flex-width'           => true,
    'header-text'          => ['site-title', 'site-description'],
    'unlink-homepage-logo' => false,
]);
```

### 6.3 Implementacja w header.php

```php
<?php
/**
 * Logo output w headerze z obsługą wariantu white/color
 * @package alubramat-child
 */

// Detect sticky scroll state via CSS class (JS toggles .scrolled na <header>)
$logo_primary = get_template_directory_uri() . '/assets/images/logo.svg';
$logo_white   = get_template_directory_uri() . '/assets/images/logo-white.svg';
?>

<a href="<?php echo esc_url(home_url('/')); ?>"
   class="alubram-logo"
   aria-label="<?php esc_attr_e('ALUBRAM GMBH – Zur Startseite', 'alubramat-child'); ?>">

  <!-- Logo color (default — wczytywane zawsze, widoczność przez CSS) -->
  <img src="<?php echo esc_url($logo_white); ?>"
       class="logo-white"
       alt="ALUBRAM GMBH Logo – Hersteller für Aluminiumzäune und Tore in Österreich"
       width="200"
       height="60"
       fetchpriority="high"
       decoding="async">

  <img src="<?php echo esc_url($logo_primary); ?>"
       class="logo-color"
       alt="ALUBRAM GMBH Logo – Aluminiumzaun Hersteller Österreich"
       width="200"
       height="60"
       fetchpriority="high"
       decoding="async">
</a>
```

### 6.4 CSS — Przełączanie logo przy scrollowaniu

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
  transition: opacity var(--transition-fast), transform var(--transition-fast);
}

/* ── Domyślny stan (transparent header — nad hero) ── */
.site-header .logo-white  { opacity: 1;  }
.site-header .logo-color  { opacity: 0; position: absolute; }

/* ── Po scrollowaniu (solid header) ── */
.site-header.is-scrolled .logo-white { opacity: 0; position: absolute; }
.site-header.is-scrolled .logo-color  { opacity: 1; position: static; }

/* ── Mobile: zawsze color logo ── */
@media (max-width: 767px) {
  .site-header .logo-white { opacity: 0; position: absolute; }
  .site-header .logo-color  { opacity: 1; position: static; }
}

/* ── Hover efekt ── */
.alubram-logo:hover img {
  transform: scale(1.02);
}

/* ── Favicon SVG dla pinned Safari tab ── */
/* (implementowane przez wp_head hook — link rel="mask-icon") */
```

### 6.5 Favicon — wp_head hook

```php
<?php
// alubramat-child/inc/enqueue.php — dodaj do wp_head

add_action('wp_head', function(): void {
    $assets = get_stylesheet_directory_uri() . '/assets/images';
    ?>
    <link rel="icon" type="image/x-icon"
          href="<?php echo esc_url($assets . '/favicon.ico'); ?>">
    <link rel="icon" type="image/png" sizes="32x32"
          href="<?php echo esc_url($assets . '/favicon-32x32.png'); ?>">
    <link rel="icon" type="image/png" sizes="16x16"
          href="<?php echo esc_url($assets . '/favicon-16x16.png'); ?>">
    <link rel="apple-touch-icon" sizes="180x180"
          href="<?php echo esc_url($assets . '/apple-touch-icon.png'); ?>">
    <link rel="mask-icon"
          href="<?php echo esc_url($assets . '/safari-pinned-tab.svg'); ?>"
          color="#C8A96E">
    <meta name="theme-color" content="#1A1A2E">
    <meta name="msapplication-TileColor" content="#1A1A2E">
    <?php
}, 1);
```

---

## 7. Open Graph i Social Media Logo

### 7.1 Specyfikacje OG Image

```
og-image.jpg (1200 × 630 px):
┌──────────────────────────────────────────────────────┐
│  Tło: gradient #1A1A2E → #0F3460                    │
│                                                      │
│        [LOGO WHITE — szerokość 320px]                │
│                                                      │
│   „Premium Aluminiumzäune · Tore · Carports"         │
│                                                      │
│        alubram.at          +43 223 584 793           │
└──────────────────────────────────────────────────────┘
```

### 7.2 Platformy i rozmiary

| Platforma | Rozmiar | Format |
|-----------|---------|--------|
| Facebook / Meta OG | 1200×630 | JPG/WEBP |
| LinkedIn | 1200×627 | JPG |
| Twitter/X Card | 1200×600 | JPG |
| WhatsApp | 400×400 | JPG |
| Google Business | 720×720 min | JPG |
| Email Signature | 240×72 | PNG 2x |

---

## 8. Zasady Użycia — Dos & Don'ts

### ✅ Prawidłowe użycie

- Używaj wyłącznie plików SVG z repozytorium (`assets/images/`)
- Zachowuj proporcje logo — `object-fit: contain`
- Stosuj właściwą wersję logo do tła (Navy/White/Gold)
- Na tle zdjęciowym używaj zawsze `logo-white.svg` z semi-transparent overlay min. `rgba(0,0,0,0.5)`
- Skaluj logo proporcjonalnie (`width: auto` przy ustalonej `height`)

### ❌ Błędy do unikania

```
✗ Rozciąganie / deformowanie proporcji logo
✗ Zmiana kolorów logo poza zdefiniowanym systemem
✗ Dodawanie cienia, glow, emboss (wyjątek: lekki drop-shadow na hero)
✗ Umieszczanie logo na pstrokatych, tęczowych tłach
✗ Używanie pliku .png na dużych rozmiarach zamiast SVG
✗ Logo poniżej 120px szerokości (czytelność wordmarku)
✗ Rotowanie lub pochylanie (skewing) logo
✗ Logo ze starym brandingiem / poprzednie wersje
✗ Logo jako wypełnienie animacji (nieustanne animowanie pulsem)
```

---

## 9. Checklist Wdrożeniowa Logo

```
□ Plik logo.svg przesłany do assets/images/
□ Plik logo-white.svg (wersja negatywna)
□ Plik logo-icon.svg (symbol only — favicon)
□ Favicon.ico wygenerowany (multi-size: 16, 32, 48px)
□ favicon-32x32.png i favicon-16x16.png
□ apple-touch-icon.png (180×180px)
□ og-image.jpg (1200×630px) — z logo i adresem strony
□ safari-pinned-tab.svg (monochrome)
□ add_theme_support('custom-logo') dodany w functions.php
□ wp_head favicon hook — zaimplementowany
□ Przełączanie logo color/white przy scrollowaniu — CSS + JS
□ alt="" opisowe po niemiecku — każdy <img> logo
□ fetchpriority="high" na logo — poprawa LCP
□ Kontrast logo vs tło: ≥ 4.5:1 (WCAG AA) — zweryfikowany
```

---

## 10. Pliki do Wygenerowania / Zamówienia

Jeżeli logo nie istnieje jeszcze jako plik SVG, projekt potrzebuje:

1. **Briefing dla grafika:**
   - Symbol: geometryczny, lamelki aluminiowe + profil słupka
   - Wordmark: `ALUBRAM` (Montserrat 800) + `GMBH` (Montserrat 400)
   - Paleta: `#1A1A2E` primary + `#C8A96E` gold accent
   - Dostarczyć: `.ai` / `.eps` + SVG + PNG 2x (wszystkie warianty)

2. **Narzędzia do samodzielnego prototypowania:**
   - [Figma](https://figma.com) — prototyp SVG
   - [Logo.ai](https://logo.ai) — AI-assisted brand identity
   - [Vectr](https://vectr.com) — darmowy edytor SVG online

---

*Wersja dokumentu: 1.0.0 | Projekt: ALUBRAM GMBH WordPress | © 2026 alubramat-child team*
