# BRAND-SETTINGS.md — ALUBRAM GMBH

> **Dokument:** Ustawienia marki i identyfikacja wizualna  
> **Projekt:** alubram-gmbh-wordpress  
> **Zastosowanie:** Wszystkie materiały, strona internetowa, dokumenty  
> **Wersja:** 1.0.0 | 2026-02-26  

---

## 1. Identyfikacja Marki

| Parametr | Wartość |
|----------|---------|
| **Nazwa firmy** | ALUBRAM GMBH |
| **Forma prawna** | GmbH (Gesellschaft mit beschränkter Haftung) |
| **Branża** | Producent ogrodzeń, bram, wiat garażowych i zadaszenia aluminiowego |
| **Rynek** | DACH (Austria, Niemcy, Szwajcaria) |
| **Język komunikacji** | Deutsch (de_AT) — wyłącznie |
| **Ton komunikacji** | Profesjonalny · Zaufany · Ekspertowy · Sie-Form |
| **Pozycjonowanie** | Premium Manufacturer — Bezpośredni producent, bez pośredników |

---

## 2. Paleta Kolorów

### 2.1 Kolory Primary (Brand Core)

```css
:root {
  /* ══════════════════════════════════════════
     PRIMARY BRAND COLORS
     ══════════════════════════════════════════ */

  --color-primary:        #1A1A2E;   /* Dark Navy — główny kolor marki */
  --color-primary-light:  #16213E;   /* Dark Blue — gradient wariant */
  --color-primary-rgb:    26, 26, 46; /* Do rgba() użycia */

  /* ══════════════════════════════════════════
     GOLD / CHAMPAGNE ACCENT — Premium feel
     ══════════════════════════════════════════ */

  --color-accent:         #C8A96E;   /* Gold/Champagne */
  --color-accent-light:   #E8D5A3;   /* Light Gold — hover, backgrounds */
  --color-accent-dark:    #A07840;   /* Dark Gold — borders, shadows */
  --color-accent-rgb:     200, 169, 110;
}
```

**Zastosowanie kolorów primary:**

| Kolor | HEX | Zastosowanie |
|-------|-----|-------------|
| Dark Navy | `#1A1A2E` | Header, footer, CTA sekcje, tekst na jasnym tle |
| Dark Blue | `#16213E` | Gradient tła, hero overlay |
| Gold | `#C8A96E` | Akcenty, podkreślenia, ikony premium, przyciski outline |
| Light Gold | `#E8D5A3` | Tła sekcji accent, hover states, borders |
| Dark Gold | `#A07840` | Hover na gold elementach, separatory |

### 2.2 Kolory Secondary

```css
  /* ══════════════════════════════════════════
     SECONDARY COLORS
     ══════════════════════════════════════════ */

  --color-secondary:      #0F3460;   /* Deep Blue */
  --color-dark:           #0D0D0D;   /* Almost Black */
  --color-light:          #F8F6F1;   /* Warm White / Off-White */
  --color-white:          #FFFFFF;

  /* Grays */
  --color-gray-100:       #F5F5F5;
  --color-gray-200:       #E8E8E8;
  --color-gray-500:       #9E9E9E;
  --color-gray-800:       #2D2D2D;
```

### 2.3 Aluminium / Metal Tones (Branżowe)

```css
  /* ══════════════════════════════════════════
     ALUMINUM / METAL TONES
     ══════════════════════════════════════════ */

  --color-aluminum:       #8D9DB6;   /* Mid aluminum */
  --color-aluminum-light: #B8C5D6;   /* Light aluminum — surfaces */
  --color-aluminum-dark:  #5A6A7E;   /* Dark aluminum — shadows */
```

**Zastosowanie aluminum tones:**
- Tła sekcji o industrialnym charakterze
- Tekstury metaliczne (CSS gradients naśladujące metal szczotkowany)
- Ikony techniczne, specyfikacje
- Subtle borders na kartach produktowych

### 2.4 Semantic Colors

```css
  /* ══════════════════════════════════════════
     SEMANTIC / FUNCTIONAL COLORS
     ══════════════════════════════════════════ */

  --color-success:        #2D7D46;   /* Zielony — sukces formularza */
  --color-warning:        #F5A623;   /* Pomarańczowy — ostrzeżenia */
  --color-error:          #D32F2F;   /* Czerwony — błędy walidacji */
  --color-info:           #1565C0;   /* Niebieski — informacje */
```

### 2.5 Dostępność — Contrast Ratios WCAG 2.1

| Kombinacja | Ratio | Standard |
|-----------|-------|---------|
| `#1A1A2E` na `#FFFFFF` | 16.1:1 | ✅ AAA |
| `#1A1A2E` na `#F8F6F1` | 15.2:1 | ✅ AAA |
| `#FFFFFF` na `#1A1A2E` | 16.1:1 | ✅ AAA |
| `#FFFFFF` na `#0F3460` | 9.4:1 | ✅ AAA |
| `#C8A96E` na `#1A1A2E` | 5.8:1 | ✅ AA |
| `#0D0D0D` na `#F8F6F1` | 17.2:1 | ✅ AAA |
| `#C8A96E` na `#FFFFFF` | 2.4:1 | ❌ FAIL — nie używaj |

---

## 3. Typografia

### 3.1 Font Stack

```css
  /* ══════════════════════════════════════════
     TYPOGRAPHY
     ══════════════════════════════════════════ */

  --font-heading:  'Montserrat', 'Raleway', 'Arial', sans-serif;
  --font-body:     'Inter', 'Open Sans', 'Helvetica Neue', sans-serif;
  --font-accent:   'Playfair Display', 'Georgia', serif;
  --font-mono:     'JetBrains Mono', 'Fira Code', 'Courier New', monospace;
```

### 3.2 Google Fonts — Import (lokalny hosting dla DSGVO)

```html
<!-- Preconnect (performance) -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>

<!-- Font imports -->
<link href="https://fonts.googleapis.com/css2?
  family=Montserrat:ital,wght@0,400;0,500;0,600;0,700;0,800;0,900;1,400&
  family=Inter:wght@300;400;500;600;700&
  family=Playfair+Display:ital,wght@0,400;0,700;1,400&
  display=swap" rel="stylesheet">
```

> ⚠️ **DSGVO Compliance:** W produkcji Google Fonts MUSI być hostowany lokalnie.  
> Narzędzie: [google-webfonts-helper.herokuapp.com](https://google-webfonts-helper.herokuapp.com)

### 3.3 Type Scale

```css
/* Fluid Typography (clamp) — Mobile First */
--text-xs:    clamp(0.75rem,  0.7rem  + 0.25vw, 0.875rem);  /* 12–14px */
--text-sm:    clamp(0.875rem, 0.85rem + 0.25vw, 1rem);       /* 14–16px */
--text-base:  clamp(1rem,     0.95rem + 0.5vw,  1.125rem);   /* 16–18px */
--text-lg:    clamp(1.125rem, 1rem    + 0.5vw,  1.25rem);    /* 18–20px */
--text-xl:    clamp(1.25rem,  1.1rem  + 0.75vw, 1.5rem);     /* 20–24px */
--text-2xl:   clamp(1.5rem,   1.3rem  + 1vw,    1.875rem);   /* 24–30px */
--text-3xl:   clamp(1.875rem, 1.5rem  + 1.5vw,  2.25rem);    /* 30–36px */
--text-4xl:   clamp(2.25rem,  1.8rem  + 2vw,    3rem);       /* 36–48px */
--text-5xl:   clamp(2.75rem,  2rem    + 3vw,    4rem);       /* 44–64px */
--text-hero:  clamp(2.5rem,   2rem    + 3.5vw,  5rem);       /* 40–80px */
```

### 3.4 Heading Styles

```css
/* H1 — Page Title / Hero */
h1, .h1 {
  font-family: var(--font-heading);
  font-size: var(--text-hero);
  font-weight: 800;
  line-height: 1.1;
  letter-spacing: -0.02em;
  color: var(--color-primary);
}

/* H2 — Section Titles */
h2, .h2 {
  font-family: var(--font-heading);
  font-size: var(--text-4xl);
  font-weight: 700;
  line-height: 1.2;
  letter-spacing: -0.01em;
  color: var(--color-primary);
}

/* H3 — Subsection Titles */
h3, .h3 {
  font-family: var(--font-heading);
  font-size: var(--text-2xl);
  font-weight: 600;
  line-height: 1.3;
  color: var(--color-gray-800);
}

/* H4 — Card Titles */
h4, .h4 {
  font-family: var(--font-heading);
  font-size: var(--text-xl);
  font-weight: 600;
  line-height: 1.4;
  color: var(--color-gray-800);
}

/* Body Text */
body, p {
  font-family: var(--font-body);
  font-size: var(--text-base);
  font-weight: 400;
  line-height: 1.7;
  color: var(--color-gray-800);
}

/* Accent / Quote */
.text-accent {
  font-family: var(--font-accent);
  font-style: italic;
  color: var(--color-accent-dark);
}
```

---

## 4. Spacing System

```css
  /* ══════════════════════════════════════════
     SPACING
     ══════════════════════════════════════════ */

  --spacing-1:  0.25rem;   /*  4px */
  --spacing-2:  0.5rem;    /*  8px */
  --spacing-3:  0.75rem;   /* 12px */
  --spacing-4:  1rem;      /* 16px */
  --spacing-5:  1.25rem;   /* 20px */
  --spacing-6:  1.5rem;    /* 24px */
  --spacing-8:  2rem;      /* 32px */
  --spacing-10: 2.5rem;    /* 40px */
  --spacing-12: 3rem;      /* 48px */
  --spacing-16: 4rem;      /* 64px */
  --spacing-20: 5rem;      /* 80px */
  --spacing-24: 6rem;      /* 96px */
  --spacing-32: 8rem;      /* 128px */

  /* Section Padding */
  --section-padding:          80px 0;   /* Desktop */
  --section-padding-tablet:   60px 0;   /* Tablet */
  --section-padding-mobile:   40px 0;   /* Mobile */

  /* Container */
  --container-max:     1280px;
  --container-padding: 0 1.5rem;        /* Mobile: 24px sides */
  --container-padding-lg: 0 2rem;       /* Desktop: 32px sides */
```

---

## 5. Border Radius

```css
  --border-radius-sm:   2px;    /* Bardzo subtelne, przemysłowe */
  --border-radius:      4px;    /* Default — karty, inputy */
  --border-radius-md:   8px;    /* Buttons, tags */
  --border-radius-lg:   12px;   /* Karty produktów, galeria */
  --border-radius-xl:   20px;   /* Modal, hero cards */
  --border-radius-full: 9999px; /* Pill buttons, badges */
```

---

## 6. Shadow System

```css
  /* ══════════════════════════════════════════
     BOX SHADOWS
     ══════════════════════════════════════════ */

  --shadow-sm:   0 2px 8px rgba(0, 0, 0, 0.08);
  --shadow-md:   0 8px 30px rgba(0, 0, 0, 0.12);
  --shadow-lg:   0 20px 60px rgba(0, 0, 0, 0.18);
  --shadow-xl:   0 25px 80px rgba(0, 0, 0, 0.22);

  /* Brand shadows */
  --shadow-gold:  0 4px 20px rgba(200, 169, 110, 0.30);
  --shadow-navy:  0 8px 30px rgba(26, 26, 46, 0.25);
  --shadow-blue:  0 8px 30px rgba(15, 52, 96, 0.20);

  /* Inset shadows (inner) */
  --shadow-inner: inset 0 2px 8px rgba(0, 0, 0, 0.10);
```

---

## 7. Gradient Definitions

```css
  /* ══════════════════════════════════════════
     GRADIENTS
     ══════════════════════════════════════════ */

  --gradient-primary:  linear-gradient(135deg, #1A1A2E 0%, #0F3460 100%);
  --gradient-navy:     linear-gradient(180deg, #1A1A2E 0%, #16213E 100%);
  --gradient-gold:     linear-gradient(135deg, #C8A96E 0%, #E8D5A3 50%, #A07840 100%);
  --gradient-gold-h:   linear-gradient(90deg,  #A07840 0%, #C8A96E 50%, #E8D5A3 100%);
  --gradient-overlay:  linear-gradient(180deg, rgba(26,26,46,0.4) 0%, rgba(26,26,46,0.85) 100%);
  --gradient-hero:     linear-gradient(135deg, rgba(15,52,96,0.9) 0%, rgba(26,26,46,0.95) 100%);
  --gradient-card:     linear-gradient(180deg, rgba(26,26,46,0) 50%, rgba(26,26,46,0.85) 100%);
  --gradient-aluminum: linear-gradient(135deg, #B8C5D6 0%, #8D9DB6 50%, #5A6A7E 100%);
  --gradient-light:    linear-gradient(180deg, #FFFFFF 0%, #F8F6F1 100%);
```

---

## 8. Transitions & Animations

```css
  /* ══════════════════════════════════════════
     TRANSITIONS
     ══════════════════════════════════════════ */

  --transition-fast:   0.15s ease;
  --transition-base:   0.35s ease;
  --transition-slow:   0.6s cubic-bezier(0.4, 0, 0.2, 1);
  --transition-bounce: 0.5s cubic-bezier(0.34, 1.56, 0.64, 1);
  --transition-spring: 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
```

---

## 9. Z-Index Scale

```css
  /* ══════════════════════════════════════════
     Z-INDEX SCALE
     ══════════════════════════════════════════ */

  --z-behind:   -1;      /* Tło za contentem */
  --z-base:      0;      /* Default */
  --z-raised:    10;     /* Karty, elementy uniesione */
  --z-dropdown:  100;    /* Dropdowny nav */
  --z-sticky:    200;    /* Sticky header */
  --z-overlay:   300;    /* Overlaye, backsdrops */
  --z-modal:     400;    /* Modalne okna */
  --z-toast:     500;    /* Toasty, notifikacje */
  --z-tooltip:   600;    /* Tooltips */
  --z-maximum:   9999;   /* Cookie banner, critical UI */
```

---

## 10. Brand Voice & Copywriting Rules

### 10.1 Ton komunikacji

| Zasada | Opis |
|--------|------|
| **Sie-Form** | Zawsze formalna forma „Sie" — nie „du" |
| **Konkretność** | Liczby, fakty: „3–6 Wochen", „15 Jahre Erfahrung", „24/7" |
| **Aktywne zdania** | „Wir liefern direkt" zamiast „Es wird geliefert" |
| **Max. długość zdania** | 25 słów — jasność i czytelność |
| **Nagłówki** | Benefit-driven: „Ihr wartungsfreier Zaun — direkt vom Hersteller" |
| **CTA** | Actionable: „Jetzt kostenlos beraten lassen", „Angebot anfordern" |

### 10.2 Kluczowe USPs w komunikacji

```
1. Direkt vom Hersteller — kein Zwischenhändler
2. Lieferung in 3–6 Wochen garantiert
3. 24 Stunden · 7 Tage erreichbar
4. Alles aus einer Hand: Beratung → Planung → Lieferung → Montage
5. Aluminium: rostfrei · wartungsfrei · witterungsbeständig
6. Pulverbeschichtet — jahrzehntelange Haltbarkeit
```

### 10.3 Słowa kluczowe SEO (DE)

**Primary keywords:**
- `Aluminiumzaun Österreich`
- `Zaunanlage Wien`
- `Einfahrtstor Aluminium`
- `Carport Aluminium kaufen`
- `Überdachung Aluminium`
- `Zaunhersteller Österreich`

**Long-tail keywords:**
- `Aluminiumzaun direkt vom Hersteller`
- `Carport aus Aluminium kaufen Wien`
- `wartungsfreier Aluzaun Austria`
- `Aluminiumtor Schiebetor kaufen`
- `Terrassenüberdachung Aluminium Österreich`

---

## 11. Photography Style

### 11.1 Styl zdjęć

- **Nastrój:** Nowoczesny, czysty, premium — architektural photography style
- **Oświetlenie:** Naturalne, złota godzina (golden hour) — ciepłe tony
- **Kompozycja:** Symetryczna, geometryczna — podkreśla precyzję wykonania
- **Tło:** Nowoczesne domy, minimalistyczne ogrody, urban/suburban
- **Bohater:** Produkt ZAWSZE w centrum kadru — nie przysłonięty

### 11.2 Overlay na zdjęciach

```css
/* Hero section overlay */
.hero-overlay {
  background: var(--gradient-hero);
  /* = linear-gradient(135deg, rgba(15,52,96,0.9) 0%, rgba(26,26,46,0.95) 100%) */
}

/* Card image overlay (hover) */
.card-image-overlay {
  background: var(--gradient-card);
  /* = linear-gradient(180deg, rgba(26,26,46,0) 50%, rgba(26,26,46,0.85) 100%) */
}
```

### 11.3 Unsplash Photo Categories

```
Hero background:   ?q=aluminium+fence+modern+house&orientation=landscape
Products — Zäune:  ?q=metal+fence+garden+modern
Products — Tore:   ?q=entrance+gate+metal+modern
Products — Carport:?q=carport+modern+house+garage
Überdachungen:     ?q=patio+pergola+modern+aluminium
Über uns:          ?q=metal+manufacturing+workshop+professional
Galerie:           ?q=modern+house+outdoor+gate+fence
```

---

## 12. Icon System

### 12.1 Material Design Icons (Google)

```html
<!-- Import w <head> -->
<link rel="stylesheet"
      href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:opsz,wght,FILL,GRAD@20..48,100..700,0..1,-50..200"
      media="print" onload="this.media='all'">

<!-- Użycie -->
<span class="material-symbols-outlined" aria-hidden="true">fence</span>
<span class="material-symbols-outlined" aria-hidden="true">garage</span>
<span class="material-symbols-outlined" aria-hidden="true">roofing</span>
```

### 12.2 Ikony brandowe (do konsekwentnego użycia)

| Ikona | Material Symbol | Zastosowanie |
|-------|----------------|-------------|
| Ogrodzenie | `fence` | Produkt Zäune |
| Brama | `garage` / `door_sliding` | Produkt Tore |
| Wiata | `garage_home` | Produkt Carports |
| Zadaszenie | `roofing` | Produkt Überdachungen |
| Dostawa | `local_shipping` | USP Lieferung 3-6 tyg. |
| Czas | `schedule` | USP 24/7 |
| Serwis pełny | `handyman` | USP Komplettservice |
| Jakość | `verified` | USP Premium |
| Bez rdzy | `shield` | Aluminium — rostfrei |
| Bezobsługowy | `settings_suggest` | wartungsfrei |
| Telefon | `phone` | Kontakt |
| Email | `email` | Kontakt |
| Lokalizacja | `location_on` | Adres |
| Gwiazdka | `star` | Testimonials |
| Strzałka | `arrow_forward` | CTA |
| Checkmark | `check_circle` | Lista zalet |

---

## 13. Brand Compliance Checklist

Przed każdą publiczną implementacją zweryfikuj:

```
KOLORY
□ Używane tylko kolory z palety brand (:root variables)
□ Kontrast tło/tekst ≥ 4.5:1 dla normalnego tekstu (WCAG AA)
□ Kontrast tło/tekst ≥ 3:1 dla dużego tekstu (WCAG AA)
□ Gold (#C8A96E) NIGDY na białym tle jako tekst

TYPOGRAFIA
□ Tylko zdefiniowane fonty: Montserrat, Inter, Playfair Display
□ font-display: swap — zaimplementowany
□ H1 — tylko jeden na stronie
□ Hierarchia H1 > H2 > H3 — zachowana

LOGO
□ Prawidłowy wariant logo do tła (Navy/White/Gold)
□ Proporcje logo — niezdeformowane
□ Clear space wokół logo — zachowany
□ Logo nie mniejsze niż 120px szerokości na ekranie

ZDJĘCIA
□ alt="" — po niemiecku, opisowy, z keyword
□ loading="lazy" — dla wszystkich img poniżej fold
□ fetchpriority="high" — dla hero/LCP image
□ Overlay na hero: opacity ≥ 0.65

KOMUNIKACJA
□ Sie-Form — nie „du"
□ USPs uwzględnione w treści strony
□ SEO keywords — naturalnie wplecione
□ Jeden H1 z keyword per strona
□ CTA button — na każdej sekcji/stronie
```

---

*BRAND-SETTINGS.md — ALUBRAM GMBH | v1.0.0 | 2026-02-26*
