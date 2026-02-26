# BRAND-CONTEXT.md — Brand Context & Guidelines

> **Dokument:** Kontekst marki i wytyczne dla ALUBRAM GMBH
> **Projekt:** `piotroq/alubram-gmbh-wordpress`
> **Wersja:** 1.0.0 | 2026-02-26

---

## 📋 Spis Treści

1. [Company Overview](#1-company-overview)
2. [Brand Identity](#2-brand-identity)
3. [Visual Identity](#3-visual-identity)
4. [Brand Voice](#4-brand-voice)
5. [Target Audience](#5-target-audience)
6. [Competitive Landscape](#6-competitive-landscape)
7. [Brand Applications](#7-brand-applications)

---

## 1. Company Overview

### 1.1 Basic Information

| Field | Value |
|-------|-------|
| **Company Name** | ALUBRAM GMBH |
| **Legal Form** | GmbH (Gesellschaft mit beschränkter Haftung) |
| **Industry** | Aluminum fences, gates, carports, canopies manufacturer |
| **Market** | DACH (Austria, Germany, Switzerland) |
| **Language** | German (de_AT) |
| **Founded** | [Year] |
| **Headquarters** | Hintere Ortsstraße 31, 2325 Himberg bei Wien, Austria |

### 1.2 Contact Information

| Type | Details |
|------|---------|
| **Phone 1** | +43 (0) 223 584 793 |
| **Phone 2** | +43 664 437 3954 |
| **Email 1** | himberg@alubram.at |
| **Email 2** | wien@alubram.at |
| **Website** | https://alubram.at |
| **Contact Person** | Herr Szpak Irek |

### 1.3 Business Model

**ALUBRAM GMBH** is a **premium manufacturer** of aluminum products:

```
┌─────────────────────────────────────────────────────────────────┐
│                    BUSINESS MODEL                               │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  Manufacturer → Direct to Customer                              │
│  (kein Zwischenhändler - no middleman)                          │
│                                                                 │
│  Products:                                                      │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐             │
│  │  Zäune      │  │  Tore       │  │  Carports   │             │
│  │  Fences     │  │  Gates      │  │  Carports   │             │
│  └─────────────┘  └─────────────┘  └─────────────┘             │
│  ┌─────────────┐                                              │
│  │Überdachungen│                                              │
│  │  Canopies   │                                              │
│  └─────────────┘                                              │
│                                                                 │
│  Service: Beratung → Planung → Lieferung → Montage             │
│  (All from one source)                                         │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

---

## 2. Brand Identity

### 2.1 Mission Statement

**"Premium aluminum products delivered directly from the manufacturer, combining Austrian quality with modern design and unmatched service."**

### 2.2 Vision

**"To be the leading premium aluminum products manufacturer in the DACH region, recognized for quality, reliability, and innovation."**

### 2.3 Core Values

| Value | Description |
|-------|-------------|
| **Qualität** | Austrian quality, premium materials, precision manufacturing |
| **Zuverlässigkeit** | Reliable delivery, on-time completion, trustworthy |
| **Innovation** | Modern designs, latest technology, continuous improvement |
| **Service** | Complete service, customer-focused, 24/7 availability |
| **Nachhaltigkeit** | Durable products, maintenance-free, long-lasting |

### 2.4 Unique Selling Propositions (USPs)

```
┌─────────────────────────────────────────────────────────────────┐
│                    UNIQUE SELLING PROPOSITIONS                  │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  ✓ Direkt vom Hersteller                                        │
│    (Direct from manufacturer - no middleman)                    │
│                                                                 │
│  ✓ Lieferung in 3–6 Wochen garantiert                           │
│    (Delivery in 3-6 weeks guaranteed)                           │
│                                                                 │
│  ✓ 24 Stunden · 7 Tage erreichbar                               │
│    (Available 24/7)                                             │
│                                                                 │
│  ✓ Alles aus einer Hand                                         │
│    (Everything from one source)                                 │
│    Beratung → Planung → Lieferung → Montage                     │
│                                                                 │
│  ✓ Aluminium: rostfrei · wartungsfrei                           │
│    (Aluminum: rust-free · maintenance-free)                     │
│                                                                 │
│  ✓ Pulverbeschichtet — jahrzehntelange Haltbarkeit              │
│    (Powder-coated — decades of durability)                      │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

---

## 3. Visual Identity

### 3.1 Brand Colors

#### Primary Colors

```css
/* Dark Navy - Main brand color */
--color-primary: #1A1A2E;
--color-primary-light: #16213E;
--color-primary-rgb: 26, 26, 46;

/* Gold/Champagne - Premium accent */
--color-accent: #C8A96E;
--color-accent-light: #E8D5A3;
--color-accent-dark: #A07840;
--color-accent-rgb: 200, 169, 110;
```

#### Secondary Colors

```css
/* Deep Blue */
--color-secondary: #0F3460;

/* Almost Black */
--color-dark: #0D0D0D;

/* Warm White */
--color-light: #F8F6F1;

/* Pure White */
--color-white: #FFFFFF;
```

#### Aluminum Tones

```css
/* Mid Aluminum */
--color-aluminum: #8D9DB6;

/* Light Aluminum */
--color-aluminum-light: #B8C5D6;

/* Dark Aluminum */
--color-aluminum-dark: #5A6A7E;
```

### 3.2 Color Usage

| Color | Usage | Context |
|-------|-------|---------|
| **Dark Navy (#1A1A2E)** | Header, footer, CTA sections, text on light | Primary brand color |
| **Gold (#C8A96E)** | Accents, underlines, premium icons, outline buttons | Premium accent |
| **Deep Blue (#0F3460)** | Background gradients, hero overlay | Secondary |
| **Warm White (#F8F6F1)** | Section backgrounds, light backgrounds | Light neutral |
| **Aluminum tones** | Industrial sections, technical specs | Product-related |

### 3.3 Typography

#### Font Stack

```css
/* Headings */
--font-heading: 'Montserrat', 'Raleway', sans-serif;

/* Body Text */
--font-body: 'Inter', 'Open Sans', sans-serif;

/* Accent/Quotes */
--font-accent: 'Playfair Display', serif;
```

#### Font Weights

| Font | Weights | Usage |
|------|---------|-------|
| **Montserrat** | 400, 500, 600, 700, 800, 900 | H1-H6, wordmark |
| **Inter** | 300, 400, 500, 600, 700 | Body text, UI |
| **Playfair Display** | 400, 700 | Quotes, special text |

#### Type Scale

```css
/* Fluid Typography (clamp) */
--text-xs:    clamp(0.75rem,  0.7rem  + 0.25vw, 0.875rem);
--text-sm:    clamp(0.875rem, 0.85rem + 0.25vw, 1rem);
--text-base:  clamp(1rem,     0.95rem + 0.5vw,  1.125rem);
--text-lg:    clamp(1.125rem, 1rem    + 0.5vw,  1.25rem);
--text-xl:    clamp(1.25rem,  1.1rem  + 0.75vw, 1.5rem);
--text-2xl:   clamp(1.5rem,   1.3rem  + 1vw,    1.875rem);
--text-3xl:   clamp(1.875rem, 1.5rem  + 1.5vw,  2.25rem);
--text-4xl:   clamp(2.25rem,  1.8rem  + 2vw,    3rem);
--text-5xl:   clamp(2.75rem,  2rem    + 3vw,    4rem);
--text-hero:  clamp(2.5rem,   2rem    + 3.5vw,  5rem);
```

### 3.4 Logo Usage

**Logo Variants:**
- Primary (full color, Navy)
- White/Negative (for dark backgrounds)
- Gold accent (premium materials)
- Icon only (favicon, social)

**Clear Space:**
```
Minimum clear space = 1× height of letter "A" in wordmark

┌────────────────────────────────────────┐
│  ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░  │
│  ░░░  [LOGO]  ALUBRAM GMBH  ░░░░░░░░  │
│  ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░  │
└────────────────────────────────────────┘
```

**Minimum Sizes:**
- Desktop header: 180-220px width
- Mobile header: 120px width
- Print business card: 40mm width
- Favicon: 32×32px

---

## 4. Brand Voice

### 4.1 Tone of Voice

**Keywords:**
- Professional (professionell)
- Trustworthy (zuverlässig)
- Expert (kompetent)
- Friendly (freundlich)
- Direct (direkt)

### 4.2 Communication Style

| Aspect | Guideline |
|--------|-----------|
| **Form** | Sie-Form (formal address) |
| **Voice** | Active voice |
| **Sentence Length** | Max 25 words |
| **Focus** | Benefits, numbers, facts |
| **Avoid** | Passive constructions, jargon |

### 4.3 Writing Guidelines

**DO:**
```
✅ "Wir liefern direkt vom Hersteller."
✅ "Lieferung in 3–6 Wochen garantiert."
✅ "15 Jahre Erfahrung."
✅ "Kostenlose Beratung."
```

**DON'T:**
```
❌ "Es wird geliefert." (passive)
❌ "Schnelle Lieferung." (vague)
❌ "Viele Jahre Erfahrung." (imprecise)
❌ "Günstige Preise." (cheap connotation)
```

### 4.4 Key Messages

**Primary Messages:**
1. "Direkt vom Hersteller — kein Zwischenhändler"
2. "Lieferung in 3–6 Wochen garantiert"
3. "24 Stunden · 7 Tage erreichbar"
4. "Alles aus einer Hand: Beratung → Planung → Lieferung → Montage"
5. "Aluminium: rostfrei · wartungsfrei · witterungsbeständig"

---

## 5. Target Audience

### 5.1 Primary Audience

**Demographics:**
- **Age:** 35-65 years
- **Gender:** Predominantly male (70%)
- **Location:** Austria (primary), Germany, Switzerland
- **Income:** Middle to high income
- **Property:** Homeowners, property owners

**Psychographics:**
- Value quality over price
- Prefer durable, maintenance-free solutions
- Appreciate premium design
- Research online before purchasing
- Value local manufacturers

### 5.2 User Personas

#### Persona 1: Max Mustermann (Homeowner)

```
┌─────────────────────────────────────────────────────────────────┐
│  Max Mustermann, 52, Wien Umgebung                              │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  Background:                                                    │
│  - Owns a single-family home                                    │
│  - Needs new fence for property                                 │
│  - Values quality and durability                                │
│                                                                 │
│  Behavior:                                                      │
│  - Researches online extensively                                │
│  - Requests multiple quotes                                     │
│  - Reads reviews and testimonials                               │
│                                                                 │
│  Decision Factors:                                              │
│  - Quality of materials                                         │
│  - Price/performance ratio                                      │
│  - Delivery time                                                │
│  - Warranty                                                     │
│  - Local manufacturer                                           │
│                                                                 │
│  Pain Points:                                                   │
│  - Confused by too many options                                 │
│  - Worried about installation                                   │
│  - Wants maintenance-free solution                              │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

#### Persona 2: Architekt Bauer (Architect)

```
┌─────────────────────────────────────────────────────────────────┐
│  Architekt Bauer, 45, Österreich                                │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  Background:                                                    │
│  - Works at architecture firm                                   │
│  - Specifies products for client projects                       │
│  - Recommends to clients                                        │
│                                                                 │
│  Behavior:                                                      │
│  - Looks for technical specifications                           │
│  - Values reliability and consistency                           │
│  - Needs CAD drawings and BIM models                            │
│                                                                 │
│  Decision Factors:                                              │
│  - Product quality                                              │
│  - Design aesthetics                                            │
│  - Technical support                                            │
│  - Availability                                                 │
│                                                                 │
│  Pain Points:                                                   │
│  - Lack of technical documentation                              │
│  - Inconsistent quality                                         │
│  - Poor communication                                           │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

---

## 6. Competitive Landscape

### 6.1 Direct Competitors

| Competitor | URL | Strengths | Weaknesses |
|------------|-----|-----------|------------|
| **Arrea** | arrea.at | Strong brand, video content | Limited product range |
| **Selt** | selt.com | Premium positioning, good UX | Higher prices |
| **MB Veranda** | mbveranda.de | Good SEO, wide range | Less premium feel |
| **Hörmann** | hoermann.com | Market leader, strong SEO | Corporate, impersonal |
| **Kaindl** | kaindl.com | Established brand | Outdated website |

### 6.2 Competitive Advantages

**ALUBRAM GMBH Advantages:**
1. ✅ Direct manufacturer (better prices)
2. ✅ Guaranteed delivery time (3-6 weeks)
3. ✅ 24/7 availability
4. ✅ Complete service (consultation to installation)
5. ✅ Austrian quality (Made in Austria)
6. ✅ Maintenance-free aluminum

### 6.3 Market Positioning

```
┌─────────────────────────────────────────────────────────────────┐
│                    POSITIONING MAP                              │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  Price ↑                                                        │
│   │                                                             │
│   │    Hörmann          Selt                                    │
│   │    (Premium)        (Luxury)                                │
│   │                                                             │
│   │         ALUBRAM                                             │
│   │         (Premium Value)                                     │
│   │                  Arrea                                      │
│   │                  (Mid-Premium)                              │
│   │                                             MB Veranda      │
│   │                                             (Mid)           │
│   └──────────────────────────────────────────→ Quality          │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

---

## 7. Brand Applications

### 7.1 Website

**Design Principles:**
- Modern, premium, metallic
- Industrial-elegant style
- Clean layouts with generous whitespace
- High-quality imagery
- Subtle animations

**Key Pages:**
- Homepage (Startseite)
- Products (Produkte)
- About Us (Über uns)
- References (Referenzen)
- Contact (Kontakt)

### 7.2 Print Materials

**Business Card:**
```
┌─────────────────────────────────────────┐
│  [LOGO]                                 │
│                                         │
│  ALUBRAM GMBH                           │
│  Hintere Ortsstraße 31                  │
│  2325 Himberg bei Wien                  │
│                                         │
│  T: +43 (0) 223 584 793                 │
│  M: +43 664 437 3954                    │
│  E: himberg@alubram.at                  │
│  W: alubram.at                          │
└─────────────────────────────────────────┘
```

**Letterhead:**
- Logo top-left or center
- Company details in footer
- Clean, professional layout

### 7.3 Social Media

**Platforms:**
- Facebook (3x/week)
- Instagram (daily stories, 3x/week posts)
- Pinterest (product pins)
- YouTube (video tutorials)

**Content Types:**
- Product showcases
- Project completions
- Behind-the-scenes
- Customer testimonials
- Tips & guides

### 7.4 Email Signature

```
Mit freundlichen Grüßen

[Your Name]
[Your Position]

ALUBRAM GMBH
Hintere Ortsstraße 31
2325 Himberg bei Wien, Österreich

T: +43 (0) 223 584 793
M: +43 664 437 3954
E: [email]@alubram.at
W: alubram.at

[LOGO - 240×72px]
```

---

## 8. Brand Compliance Checklist

Before publishing any material:

```
COLORS
□ Only brand colors used (:root variables)
□ Contrast ratio ≥ 4.5:1 for normal text (WCAG AA)
□ Gold (#C8A96E) NEVER on white as text

TYPOGRAPHY
□ Only defined fonts: Montserrat, Inter, Playfair Display
□ font-display: swap implemented
□ H1 — only one per page
□ Hierarchy H1 > H2 > H3 — maintained

LOGO
□ Correct logo variant for background (Navy/White/Gold)
□ Logo proportions — not distorted
□ Clear space around logo — maintained
□ Logo minimum 120px width on screen

IMAGES
□ alt="" — in German, descriptive, with keyword
□ loading="lazy" — for all images below fold
□ fetchpriority="high" — for hero/LCP image
□ Overlay on hero: opacity ≥ 0.65

COMMUNICATION
□ Sie-Form — not "du"
□ USPs included in page content
□ SEO keywords — naturally integrated
□ One H1 with keyword per page
□ CTA button — on every section/page
```

---

*BRAND-CONTEXT.md — ALUBRAM GMBH WordPress Project | v1.0.0 | 2026-02-26*
