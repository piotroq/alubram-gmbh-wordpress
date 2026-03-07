# PAGE-WIREFRAMES.md
# ALUBRAM GMBH — Pages Wireframes & Layout Specifications

> **Dokument:** Pages Wireframes & Layout Specifications  
> **Projekt:** alubram-gmbh-wordpress | Theme: `alubramat-child` | WordPress 6.9  
> **Version:** 1.0.0 | **Datum:** März 2026  
> **Vorbereitet für:** Herr Szpak Irek, ALUBRAM GMBH  
> **Sprache:** Deutsch (de_AT) | **Markt:** DACH — Österreich, Deutschland, Schweiz  

---

## 📋 INHALTSVERZEICHNIS

| # | Seite | URL |
|---|-------|-----|
| G | Globale Komponenten (Topbar, Header, Footer, Cookie) | — |
| 01 | Startseite (Homepage) | `/` |
| 02 | Über uns | `/uber-uns/` |
| 03 | Produkte Übersicht | `/produkte/` |
| 04 | Zäune & Zaunfelder (Kategorie) | `/produkte/zaune/` |
| 05 | Tore & Einfahrtstore (Kategorie) | `/produkte/tore/` |
| 06 | Carports | `/produkte/carports/` |
| 07 | Überdachungen (Kategorie) | `/produkte/ueberdachungen/` |
| 08 | Single Produkt (Template) | `/produkte/{kat}/{slug}/` |
| 09 | Referenzen & Galerie | `/referenzen/` |
| 10 | Leistungen | `/leistungen/` |
| 11 | Kontakt | `/kontakt/` |
| 12 | Standorte | `/kontakt/standorte/` |
| 13 | Ratgeber — Blog-Archiv | `/ratgeber/` |
| 14 | Single Blog-Artikel | `/ratgeber/{slug}/` |
| 15 | Aktionen & Angebote | `/aktionen/` |
| 16 | Karriere | `/karriere/` |
| 17 | Impressum / Datenschutz / AGB | `/impressum/` etc. |
| 18 | Lokale SEO Landing Pages | `/aluminiumzaun-wien/` etc. |
| KL | Komponenten-Bibliothek | — |
| AN | Animationen & Performance-Checkliste | — |

---

## DESIGN TOKEN REFERENZ

```
╔══════════════════════════════════════════════════════════════════════════╗
║                  ALUBRAM GMBH — DESIGN TOKENS (v1.0)                   ║
╠══════════════════════════════════════════════════════════════════════════╣
║  KERNFARBEN (Brandbook v1.0)                                            ║
║  ──────────────────────────────────────────────────────────────────────║
║  Red Primary    #E21212  ★ ALLE primären CTAs, Buttons, USP-Bar        ║
║  Red Secondary  #B73D3D  Hover-Zustände, Pressed States                ║
║  Navy Core      #233452  Topbar-BG, Header (scrolled), tiefer Hintergr.║
║  Navy Dark      #1A2840  Footer-BG, Hero-Overlay                       ║
║  Navy Darkest   #111B2D  Dunkelste Sektionen                           ║
║  Gold Accent    #C8A96E  Premium-Akzente, Badges, Trennlinien          ║
║  Gold Light     #E8D5A3  Hover-States, Highlights                      ║
║  Off-White      #F8F6F1  Seitenhintergrund (hell)                      ║
║  White          #FFFFFF  Karten, Formulare, reines Weiß               ║
║  Gray 800       #2D2D2D  Fließtext auf hellem Hintergrund              ║
║  Gray 500       #9E9E9E  Sekundärer Text, Metadaten                   ║
║  Aluminum       #8D9DB6  Industrielle Akzente, technische Bereiche     ║
║                                                                        ║
║  TYPOGRAFIE                                                            ║
║  ──────────────────────────────────────────────────────────────────────║
║  Heading:  Montserrat 800/700/600 | letter-spacing: -0.02em            ║
║  Body:     Inter 400/500 | line-height: 1.7                            ║
║  Accent:   Playfair Display italic (Quotes, Testimonials)              ║
║                                                                        ║
║  TYPE SCALE (fluid clamp)                                              ║
║  text-hero:  clamp(2.5rem, 2rem + 3.5vw, 5rem)    ← H1 Homepage-Hero  ║
║  text-h1:    clamp(2.25rem, 1.8rem + 2.5vw, 4rem) ← H1 Inner Pages    ║
║  text-h2:    clamp(1.75rem, 1.5rem + 1.5vw, 3rem) ← Sektions-Titel    ║
║  text-h3:    clamp(1.375rem,1.2rem + 1vw, 1.875rem) ← Karten-Titel    ║
║  text-lg:    clamp(1.125rem,1rem + 0.5vw, 1.375rem) ← Sublines        ║
║  text-base:  clamp(1rem, 0.95rem + 0.25vw, 1.125rem) ← Body           ║
║  text-sm:    clamp(0.875rem, 0.85rem + 0.1vw, 1rem)  ← Metadaten      ║
║                                                                        ║
║  SPACING                                                               ║
║  ──────────────────────────────────────────────────────────────────────║
║  Container max-width: 1280px | Auto-Margins                            ║
║  Section-Padding Desktop: 80px 0                                       ║
║  Section-Padding Mobile:  50px 0                                       ║
║  Grid-Gap Desktop: 2rem | Grid-Gap Mobile: 1.25rem                     ║
║  Container-Padding: 0 32px (desktop) | 0 20px (mobile)                ║
║                                                                        ║
║  RADIEN & SCHATTEN                                                     ║
║  ──────────────────────────────────────────────────────────────────────║
║  border-radius-sm:  4px  (Buttons, Tags, Badges)                       ║
║  border-radius-md:  8px  (Input-Felder, kleine Karten)                 ║
║  border-radius-lg: 12px  (Karten, große Panels)                        ║
║  shadow-sm: 0 2px 8px rgba(0,0,0,0.08)                                 ║
║  shadow-md: 0 8px 30px rgba(0,0,0,0.12)                                ║
║  shadow-lg: 0 20px 60px rgba(0,0,0,0.18)                               ║
║  shadow-red: 0 4px 24px rgba(226,18,18,0.38)                           ║
║  shadow-gold: 0 4px 20px rgba(200,169,110,0.30)                        ║
║                                                                        ║
║  BREAKPOINTS (Mobile-First)                                            ║
║  ──────────────────────────────────────────────────────────────────────║
║  Mobile:    < 768px   (default — Basis)                                ║
║  Tablet:   ≥ 768px   (md:)                                             ║
║  Desktop:  ≥ 1024px  (lg:)                                             ║
║  Wide:     ≥ 1280px  (xl:)                                             ║
╚══════════════════════════════════════════════════════════════════════════╝
```

---

## G — GLOBALE KOMPONENTEN

### G-01 — TOPBAR

```
╔════════════════════════════════════════════════════════════════════════╗
║  BG: #233452 | Höhe: 44px | Versteckt auf Mobile (hidden / md:flex)  ║
╠════════════════════════════════════════════════════════════════════════╣
║                                                                       ║
║  📍 Himberg bei Wien, NÖ  |  ☎ +43 (0) 223 584 793  |               ║
║                 ✉ himberg@alubram.at   |   🕐 Mustergarten 24/7     ║
║                                                                       ║
╚════════════════════════════════════════════════════════════════════════╝

SPEZIFIKATION:
  Hintergrund:  #233452
  Text:         #FFFFFF | Inter 400 | 13px
  Icon-Farbe:   #C8A96E (Material Symbols Outlined, 16px)
  Separator:    | (rgba(255,255,255,0.25))
  Link-Hover:   color: #C8A96E | transition: 0.2s ease
  Padding:      0 32px | max-width: 1280px margin: auto
  z-index:      200
```

---

### G-02 — HEADER & HAUPTNAVIGATION

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

DESKTOP — TRANSPARENT (scroll = 0, nur über Hero-Sektionen):
┌────────────────────────────────────────────────────────────────────────┐
│  Höhe: 80px  |  position: fixed  |  top: 44px  |  z-index: 999       │
│  BG: transparent  |  Logo: logo-white.svg  |  Links: #FFFFFF          │
│                                                                        │
│  [🔷 ALUBRAM weiß]   Über uns   Produkte▾   Leistungen   Referenzen   │
│                       Aktionen   Ratgeber    Kontakt   [ANGEBOT →] 🔴  │
└────────────────────────────────────────────────────────────────────────┘

DESKTOP — SOLID (scroll > 80px oder alle Inner-Pages ohne Video-Hero):
┌────────────────────────────────────────────────────────────────────────┐
│  BG: #FFFFFF  |  box-shadow: 0 2px 20px rgba(0,0,0,0.10)             │
│  Logo: logo.svg (navy)  |  Links: #1A2840                             │
│                                                                        │
│  [🔷 ALUBRAM navy]   Über uns   Produkte▾   Leistungen   Referenzen   │
│                       Aktionen   Ratgeber    Kontakt   [ANGEBOT →] 🔴  │
└────────────────────────────────────────────────────────────────────────┘

TRANSITION: background 0.35s ease | box-shadow 0.35s ease
Logo-Swap: .scrolled Klasse → src wechselt via JS

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

CTA-BUTTON SPEZIFIKATION (Header):
  Text:       "Angebot anfordern"
  BG:         #E21212  |  Hover: #B73D3D
  Color:      #FFFFFF
  Font:       Montserrat 600 | 14px
  Padding:    12px 22px  |  border-radius: 4px
  Shadow:     0 4px 24px rgba(226,18,18,0.38)
  Hover:      translateY(-2px) | shadow verstärkt
  Transition: all 0.25s ease

NAV-LINKS SPEZIFIKATION:
  Font:       Montserrat 500 | 14px | letter-spacing: 0.04em
  Transparent BG: color #FFFFFF
  Solid BG:   color #1A2840
  Hover:      color #E21212
  Active:     color #E21212 | border-bottom: 2px solid #E21212
  Padding:    8px 0

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

MEGA-MENU "PRODUKTE" (Desktop, erscheint bei Hover/Click):
┌──────────────────────────────────────────────────────────────────────────┐
│  BG: #FFFFFF  |  border-top: 3px solid #E21212  |  box-shadow: shadow-lg │
│  Animation: opacity 0→1 + translateY(-8px → 0) | 0.25s ease            │
│  Padding: 32px  |  max-width: 1280px  |  Grid: 4 Spalten               │
│                                                                          │
│  ┌─────────────────┐  ┌─────────────────┐  ┌─────────────────┐  ┌────┐  │
│  │ ZÄUNE &         │  │ TORE &          │  │ ÜBERDACHUNGEN   │  │MEHR│  │
│  │ ZAUNFELDER      │  │ EINFAHRTSTORE   │  │                 │  │    │  │
│  │ ─────────────   │  │ ─────────────   │  │ ─────────────   │  │─── │  │
│  │ → Zäune Übers.  │  │ → Tore Übers.   │  │ → Pergola       │  │Car-│  │
│  │ → Horizontal    │  │ → Schiebetor    │  │ → Vordach       │  │port│  │
│  │ → Vertikal      │  │ → Flügeltor     │  │ → Terrasse Prem.│  │    │  │
│  │ → Klassisch     │  │ → Eingangstor   │  │ → Terrasse Std. │  │Bal-│  │
│  │ → Blickdicht    │  │                 │  │                 │  │kone│  │
│  │ → Industrie     │  │                 │  │                 │  │    │  │
│  │ → Sondermodell  │  │                 │  │                 │  │Gelä│  │
│  └─────────────────┘  └─────────────────┘  └─────────────────┘  └────┘  │
│                                                                          │
│  ────────────────────────────────────────────────────────────────────   │
│  📷 Alle Referenzen →              ☎ Kostenlos beraten lassen → 🔴     │
└──────────────────────────────────────────────────────────────────────────┘

Kategorie-Titel: Montserrat 600 | 11px | letter-spacing: 0.12em | #9E9E9E | UPPERCASE
Menu-Links:      Inter 400 | 14px | #2D2D2D | Hover: #E21212
Hover-Effekt:    border-left: 2px solid #E21212 | padding-left: 8px | transition: 0.2s

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

MOBILE HEADER (< 768px):
┌────────────────────────────────────┐
│  Höhe: 64px  |  BG: #1A2840       │
│  (immer solid, kein transparent)  │
│                                    │
│  [ALUBRAM logo weiß]     [☰]  🔴  │
└────────────────────────────────────┘

MOBILE VOLLBILD-MENU (bei ☰ Klick):
┌────────────────────────────────────┐
│  BG: #111B2D  |  100vh  |  z:999  │
│  Slide-in von rechts | 0.35s ease │
│                                    │
│  [✕ Schließen]              🔴    │
│  ──────────────────────────────    │
│  STARTSEITE                        │
│  ÜBER UNS                          │
│  PRODUKTE ▾                        │
│    · Zäune & Zaunfelder            │
│    · Tore & Einfahrtstore          │
│    · Carports                      │
│    · Überdachungen                 │
│    · Balkone & Geländer            │
│  LEISTUNGEN                        │
│  REFERENZEN                        │
│  AKTIONEN                          │
│  RATGEBER                          │
│  KONTAKT                           │
│  ──────────────────────────────    │
│  ☎ +43 (0) 223 584 793            │
│  ✉ himberg@alubram.at             │
│  ──────────────────────────────    │
│  [ANGEBOT ANFORDERN →] 🔴         │
│  (voll breit, 54px Höhe)           │
└────────────────────────────────────┘

Nav-Links mobile: Montserrat 600 | 18px | #FFFFFF | padding: 18px 32px
Sub-Links mobile: Inter 400 | 15px | #B8C5D6 | padding: 10px 48px
Focus-Trap:       Aktiv (WCAG 2.1 AA Tastaturnavigation)
Touch-Geste:      Swipe-right = Menu schließen
```

---

### G-03 — FOOTER

```
╔══════════════════════════════════════════════════════════════════════════╗
║  DESKTOP FOOTER                                                         ║
║  BG: #111B2D  |  Padding-top: 80px  |  Padding-bottom: 40px           ║
╠══════════════════════════════════════════════════════════════════════════╣
║                                                                         ║
║  ┌─────────────────────────────────────────────────────────────────┐   ║
║  │  [ALUBRAM LOGO weiß — 200px]                                    │   ║
║  │                                                                 │   ║
║  │  "Wir sind nicht die Größten,                                   │   ║
║  │   aber die Besten und Schnellsten."                             │   ║
║  │   Playfair Display italic | 15px | #C8A96E                      │   ║
║  │                                                                 │   ║
║  │   Premium Aluminium · Direkt vom Hersteller · Seit 2020        │   ║
║  │   Inter 400 | 13px | #8D9DB6                                   │   ║
║  └─────────────────────────────────────────────────────────────────┘   ║
║                                                                         ║
║  ─────────── Gold Trennlinie (1px, rgba(200,169,110,0.25)) ──────────  ║
║                                                                         ║
║  ┌──────────────┐ ┌──────────────┐ ┌──────────────┐ ┌──────────────┐  ║
║  │ PRODUKTE     │ │ UNTERNEHMEN  │ │ SERVICE      │ │ KONTAKT      │  ║
║  │ ───────────  │ │ ───────────  │ │ ───────────  │ │ ───────────  │  ║
║  │ Zäune        │ │ Über uns     │ │ Kontakt      │ │ 📍 Himberg   │  ║
║  │ Tore         │ │ Leistungen   │ │ Standorte    │ │ Ortsstr. 31  │  ║
║  │ Carports     │ │ Referenzen   │ │ Katalog      │ │ 2325 Himberg │  ║
║  │ Überdachung  │ │ Aktionen     │ │ Karriere     │ │              │  ║
║  │ Balkone      │ │ Ratgeber     │ │ ───────────  │ │ ☎ +43 223    │  ║
║  │ Geländer     │ │ ───────────  │ │ [Instagram]  │ │ 584 793      │  ║
║  │ Zubehör      │ │ Impressum    │ │ [Facebook]   │ │ ✉ himberg@   │  ║
║  │              │ │ Datenschutz  │ │ [YouTube]    │ │ alubram.at   │  ║
║  │              │ │ AGB          │ │              │ │ 🕐 Muster-   │  ║
║  │              │ │              │ │              │ │ garten 24/7  │  ║
║  └──────────────┘ └──────────────┘ └──────────────┘ └──────────────┘  ║
║                                                                         ║
║  ─────────────────────────────────────────────────────────────────────  ║
║  © 2026 ALUBRAM GMBH · FN 535870 w · UID ATU75724307                  ║
║  [Impressum] · [Datenschutz] · [AGB] · [Cookie-Einstellungen]         ║
║  Inter 400 | 13px | #5A6A7E                                            ║
╚══════════════════════════════════════════════════════════════════════════╝

SPALTEN-TITEL:  Montserrat 600 | 11px | letter-spacing: 0.1em | #C8A96E | UPPERCASE
LINKS:          Inter 400 | 14px | #B8C5D6 | Hover: #FFFFFF | transition: 0.2s
SOCIAL ICONS:   Material Symbols | 20px | #8D9DB6 | Hover: #FFFFFF

MOBILE FOOTER: Accordion je Kategorie (aufklappbar per Tap)
               Gold-Pfeil ▶ / ▼ als Indikator | 1 Spalte
```

---

### G-04 — BREADCRUMBS (alle Seiten außer Homepage)

```
┌────────────────────────────────────────────────────────────────┐
│  Startseite  ›  Produkte  ›  Zäune  ›  Horizontal Zaun        │
└────────────────────────────────────────────────────────────────┘

Schema:    Schema.org BreadcrumbList JSON-LD (pflicht!)
Font:      Inter 400 | 13px
Farbe:     rgba(255,255,255,0.65) auf dunklen Heroes
           #9E9E9E auf hellen Sektionen
Separator: › | color: #C8A96E
Aktuelle:  color: #FFFFFF / #2D2D2D (letztes Element)
Position:  Innerhalb des Hero-Bereichs, oben links
```

---

### G-05 — COOKIE BANNER (Borlabs Cookie — DSGVO)

```
┌──────────────────────────────────────────────────────────────────────────┐
│  position: fixed bottom | BG: #0D0D0D | border-top: 3px solid #E21212  │
│  z-index: 9999 | padding: 20px 32px                                     │
│                                                                          │
│  🍪 Diese Website verwendet Cookies für eine optimale Nutzererfahrung.  │
│     Weitere Infos in unserer [Datenschutzerklärung].                    │
│                                                                          │
│  [Nur notwendige]    [Einstellungen ▾]    [Alle akzeptieren →] 🔴       │
│   outline weiß        ghost gray           BG #E21212 | R: 4px         │
└──────────────────────────────────────────────────────────────────────────┘

Google Maps:  Erst nach Akzeptanz von Karten-Cookies laden
Google Fonts: Lokal gehostet (DSGVO Österreich — kein CDN in Production)
```


---

## SEITE 01 — STARTSEITE (HOMEPAGE)

```
URL:        /
Template:   front-page.php
PHP-Datei:  front-page.php
Priorität:  ⭐⭐⭐⭐⭐ (Hauptseite)
Schema:     LocalBusiness + Manufacturer + WebSite + SearchAction
```

---

### S01.01 — HERO SECTION (100vh)

```
╔═════════════════════════════════════════════════════════════════════════╗
║  DESKTOP: 100vh | min-height: 640px                                    ║
╠═════════════════════════════════════════════════════════════════════════╣
║                                                                        ║
║  [HINTERGRUND: Autoplay-Video (MP4, muted, loop, playsinline)         ║
║   oder hochauflösendes Parallax-Drohnenaufnahme einer Zaunanlage]     ║
║  [Overlay: gradient-hero → rgba(17,27,45,0.90) 0% → rgba(35,52,82,0.95) 100%] ║
║                                                                        ║
║  ┌──────────────────────────────────────────────────────────────────┐  ║
║  │  [Topbar #233452]                                                │  ║
║  │  [Header transparent — Logo weiß — fixed]                       │  ║
║  └──────────────────────────────────────────────────────────────────┘  ║
║                                                                        ║
║  ┌── Container 1280px ───────────────────────────────────────────────┐ ║
║  │                                                                   │ ║
║  │  [BADGE: ⭐ Direkthersteller aus Österreich]                      │ ║
║  │   BG: rgba(200,169,110,0.15) | border: 1px rgba(200,169,110,0.4) │ ║
║  │   Montserrat 600 | 12px | #C8A96E | backdrop-blur: 4px | R: 4px  │ ║
║  │   data-aos="fade-down" data-aos-delay="0"                        │ ║
║  │                                                                   │ ║
║  │  H1: Hochwertige Aluminiumzäune,                                  │ ║
║  │      Tore & Carports                                              │ ║
║  │      aus Österreich.                                              │ ║
║  │   Montserrat 800 | clamp(2.5rem,2rem+3.5vw,5rem) | #FFFFFF       │ ║
║  │   line-height: 1.1 | letter-spacing: -0.02em                     │ ║
║  │   data-aos="fade-up" data-aos-delay="100"                        │ ║
║  │                                                                   │ ║
║  │  Subline: Direkt vom Hersteller — Lieferung in 3–6 Wochen.       │ ║
║  │  Montage inklusive. Mustergarten 24/7 geöffnet.                  │ ║
║  │   Inter 400 | 20px | rgba(255,255,255,0.85) | max-width: 620px   │ ║
║  │   data-aos="fade-up" data-aos-delay="250"                        │ ║
║  │                                                                   │ ║
║  │  ┌──────────────────────────┐  ┌──────────────────────────────┐  │ ║
║  │  │ [ANGEBOT ANFORDERN →] 🔴 │  │ [Produkte entdecken  ↓]      │  │ ║
║  │  │  BG: #E21212 | R: 4px    │  │  border: 2px solid #FFFFFF   │  │ ║
║  │  │  Montserrat 600 | 16px   │  │  Montserrat 600 | 16px       │  │ ║
║  │  │  Padding: 16px 32px      │  │  Padding: 14px 28px          │  │ ║
║  │  │  Shadow: shadow-red      │  │  color: #FFFFFF               │  │ ║
║  │  │  Hover: #B73D3D          │  │  Hover: rgba(fff,0.12) BG     │  │ ║
║  │  └──────────────────────────┘  └──────────────────────────────┘  │ ║
║  │   data-aos="fade-up" data-aos-delay="400"                        │ ║
║  │                                                                   │ ║
║  │  ┌──────────────────────────────────────────────────────────┐    │ ║
║  │  │  4 × USP BADGE (nebeneinander, glassmorphism)            │    │ ║
║  │  │  BG: rgba(17,27,45,0.50) | border: rgba(200,169,110,0.25)│    │ ║
║  │  │  backdrop-filter: blur(8px) | border-radius: 8px         │    │ ║
║  │  │  Padding: 12px 20px                                      │    │ ║
║  │  │                                                          │    │ ║
║  │  │  [🏭 Direkthersteller] [⚡ 3–6 Wochen] [🕐 24/7] [🔧 Montage]│   │ ║
║  │  │   MDI-Icon 18px #C8A96E  +  Inter 500 | 13px | #FFFFFF   │    │ ║
║  │  └──────────────────────────────────────────────────────────┘    │ ║
║  │   data-aos="fade-up" data-aos-delay="550"                        │ ║
║  └───────────────────────────────────────────────────────────────────┘ ║
║                                                                        ║
║  [▼ Scroll-Indicator — animation: alubram-float | color: #C8A96E]     ║
╚═════════════════════════════════════════════════════════════════════════╝

MOBILE (100svh):
┌──────────────────────────────────┐
│  [VIDEO / BILD BG]               │
│  [Hero-Overlay navy]             │
│  [Header 64px solid #1A2840]    │
│                                  │
│  [BADGE Direkthersteller]        │
│                                  │
│  H1: Hochwertige                 │
│  Aluminiumzäune,                 │
│  Tore & Carports                 │
│  aus Österreich.                 │
│  44px | Montserrat 800           │
│                                  │
│  Subline: 16px | 2–3 Zeilen     │
│                                  │
│  [ANGEBOT ANFORDERN →] 🔴        │
│  100% Breite | 54px Höhe         │
│                                  │
│  [Produkte entdecken] outline    │
│  100% Breite | 50px Höhe         │
│                                  │
│  [USP Badges — 2×2 Grid]         │
└──────────────────────────────────┘

TECHNISCHE DETAILS:
  <video autoplay muted loop playsinline preload="none">
  Fallback:  fetchpriority="high" | .avif/.webp/.jpg
  LCP-Ziel:  Fallback-Bild < 2.5s LCP
  H1 SEO:    enthält "Aluminiumzaun Hersteller Österreich"
```

---

### S01.02 — USP BAR

```
╔═════════════════════════════════════════════════════════════════════════╗
║  BG: #E21212  |  Höhe: 58px Desktop, auto Mobile  |  kein Section-Pad ║
╠═════════════════════════════════════════════════════════════════════════╣
║                                                                        ║
║  🏭 Direkthersteller  |  ⚡ Lieferung in 3–6 Wochen  |               ║
║  🕐 Mustergarten 24/7  |  🔧 Montage inklusive                        ║
║                                                                        ║
║  Montserrat 600 | 14px | #FFFFFF                                      ║
║  Icon: MDI 18px | Separator: rgba(255,255,255,0.3)                    ║
╚═════════════════════════════════════════════════════════════════════════╝
MOBILE: 2×2 Grid | padding: 20px | text-align: center
```

---

### S01.03 — PRODUKTE ÜBERSICHT

```
╔═════════════════════════════════════════════════════════════════════════╗
║  BG: #F8F6F1  |  Padding: 80px 0                                      ║
╠═════════════════════════════════════════════════════════════════════════╣
║                                                                        ║
║  [GOLD LABEL: Unsere Aluminium-Produkte]  data-aos="fade-in"          ║
║  H2: Von der Zaunanlage bis zum kompletten Außenbereich               ║
║  Montserrat 700 | text-center | #1A2840 | data-aos="fade-up"          ║
║  Subtext: Inter 400 | 18px | #9E9E9E | text-center                    ║
║                                                                        ║
║  GRID 4 Spalten × 2 Reihen (Desktop lg:4 md:2 sm:1):                 ║
║                                                                        ║
║  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  ║
║  │[BILD 320px] │  │[BILD 320px] │  │[BILD 320px] │  │[BILD 320px] │  ║
║  │ Hover-Zoom  │  │             │  │             │  │             │  ║
║  │ scale 1.05  │  │             │  │             │  │             │  ║
║  │ Overlay 0→  │  │             │  │             │  │             │  ║
║  │ 0.45 hover  │  │             │  │             │  │             │  ║
║  │─────────────│  │─────────────│  │─────────────│  │─────────────│  ║
║  │ ZÄUNE &     │  │ TORE &      │  │ CARPORTS    │  │ÜBERDACHUNGEN│  ║
║  │ ZAUNFELDER  │  │ EINFAHRTST. │  │             │  │             │  ║
║  │ 6 Modelle   │  │ 3 Ausführg. │  │ 2 Varianten │  │ 4 Varianten │  ║
║  │ [→ Gold]    │  │ [→ Gold]    │  │ [→ Gold]    │  │ [→ Gold]    │  ║
║  └─────────────┘  └─────────────┘  └─────────────┘  └─────────────┘  ║
║  data-aos="zoom-in-up" delay: 0/100/200/300ms                         ║
║                                                                        ║
║  ┌─────────────────────┐  ┌─────────────────────┐                     ║
║  │ [BILD]              │  │ [BILD]              │                     ║
║  │ BALKONE & GELÄNDER  │  │ ZUBEHÖR & SONSTIGES │                     ║
║  │ [→ Gold Pfeil]      │  │ [→ Gold Pfeil]      │                     ║
║  └─────────────────────┘  └─────────────────────┘                     ║
║                                                                        ║
║  [Alle Produkte ansehen →]  btn outline navy | zentriert              ║
║  data-aos="fade-up"                                                   ║
╚═════════════════════════════════════════════════════════════════════════╝

KARTE-SPEC:
  border-radius: 12px | overflow: hidden
  Bild:     object-fit: cover | transition: transform 0.6s cubic-bezier
  Overlay:  ::after pseudo | rgba(17,27,45,0.0) → rgba(17,27,45,0.55) hover
  Titel:    Montserrat 700 | 20px | #FFFFFF | absolute bottom-left 20px
  Kateg.:   Inter 400 | 13px | #C8A96E | über dem Titel
  Arrow →:  #C8A96E | translateX(0) hover | transition 0.3s

MOBILE: lg:4 → md:2 → sm:1 Spalten | Bild-Höhe: 240px
```

---

### S01.04 — WARUM ALUBRAM (Stats + Vorteile-Split)

```
╔═════════════════════════════════════════════════════════════════════════╗
║  BG: #1A2840 + Parallax Bild (data-parallax)  |  Padding: 80px 0     ║
║  Overlay: rgba(17,27,45,0.88)                                         ║
╠═════════════════════════════════════════════════════════════════════════╣
║                                                                        ║
║  [GOLD LABEL]  H2: Warum ALUBRAM GMBH wählen?                        ║
║  Montserrat 700 | text-center | #FFFFFF | data-aos="fade-up"          ║
║                                                                        ║
║  COUNTER-LEISTE (4 Spalten):                                          ║
║  ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐    ║
║  │  1.000+     │ │  3–6 Wo.   │ │    24/7     │ │   15 J.     │    ║
║  │ counter-JS  │ │ counter-JS  │ │ counter-JS  │ │ counter-JS  │    ║
║  │ Montserrat 9│ │ Montserrat 9│ │ Montserrat 9│ │ Montserrat 9│    ║
║  │ 56px #C8A96E│ │ 56px #C8A96E│ │ 56px #C8A96E│ │ 56px #C8A96E│    ║
║  │             │ │             │ │             │ │             │    ║
║  │ Realisierte │ │ Garantierte │ │ Mustergarten│ │ Branchen-   │    ║
║  │ Projekte    │ │ Lieferzeit  │ │ geöffnet    │ │ erfahrung   │    ║
║  │ Inter 14px  │ │ Inter 14px  │ │ Inter 14px  │ │ Inter 14px  │    ║
║  │ #B8C5D6     │ │ #B8C5D6     │ │ #B8C5D6     │ │ #B8C5D6     │    ║
║  └─────────────┘ └─────────────┘ └─────────────┘ └─────────────┘    ║
║  data-aos="fade-up" delay: 0/100/200/300ms                           ║
║                                                                        ║
║  ── Gold Trennlinie rgba(200,169,110,0.2) ─────────────────────────  ║
║                                                                        ║
║  SPLIT LAYOUT 50/50:                                                  ║
║  ┌──────────────────────────────┐  ┌────────────────────────────────┐ ║
║  │ [BILD: Montage-Team / Muster │  │ ✅ Direkthersteller            │ ║
║  │  garten beleuchtet]          │  │ Kein Zwischenhändler —         │ ║
║  │  aspect-ratio: 4/5           │  │ günstigere Preise              │ ║
║  │  border-radius: 12px         │  │                                │ ║
║  │  data-aos="fade-right"       │  │ ✅ Komplettservice             │ ║
║  │                              │  │ Beratung → Planung →          │ ║
║  │                              │  │ Lieferung → Montage            │ ║
║  │                              │  │                                │ ║
║  │                              │  │ ✅ Premium Aluminium           │ ║
║  │                              │  │ Rostfrei · Wartungsfrei ·     │ ║
║  │                              │  │ Pulverbeschichtet              │ ║
║  │                              │  │                                │ ║
║  │                              │  │ ✅ Alle RAL-Farben             │ ║
║  │                              │  │ inkl. Holzoptik Thermoprint    │ ║
║  │                              │  │                                │ ║
║  │                              │  │ [Mehr über uns →]              │ ║
║  │                              │  │  btn outline gold              │ ║
║  └──────────────────────────────┘  └────────────────────────────────┘ ║
║  data-aos="fade-left" für rechte Spalte | delay: 150ms               ║
╚═════════════════════════════════════════════════════════════════════════╝

COUNTER-ANIMATION: IntersectionObserver (threshold:0.5) | 2000ms | easeOutCubic
Format: DE-Tausender-Punkt  "1.000+" | requestAnimationFrame
```

---

### S01.05 — UNSER PROZESS (4 Schritte)

```
╔═════════════════════════════════════════════════════════════════════════╗
║  BG: #F8F6F1  |  Padding: 80px 0                                      ║
╠═════════════════════════════════════════════════════════════════════════╣
║                                                                        ║
║  [GOLD LABEL]  H2: Von der Idee zur fertigen Anlage — in 4 Schritten  ║
║  Montserrat 700 | text-center | #1A2840                               ║
║                                                                        ║
║  PROZESS-GRID (4 Karten nebeneinander, Pfeil dazwischen):             ║
║                                                                        ║
║  ┌──────────┐ → ┌──────────┐ → ┌──────────┐ → ┌──────────┐          ║
║  │ 01       │   │ 02       │   │ 03       │   │ 04       │          ║
║  │          │   │          │   │          │   │          │          ║
║  │ 💬       │   │ 📐       │   │ 🚚       │   │ 🔧       │          ║
║  │          │   │          │   │          │   │          │          ║
║  │ Beratung │   │ Planung  │   │ Lieferung│   │ Montage  │          ║
║  │          │   │          │   │          │   │          │          ║
║  │ Kostenlos│   │ Individ. │   │ Direkt v.│   │ Fachger. │          ║
║  │ Erstberatg│  │ Planung  │   │ Herstell.│   │ Montage  │          ║
║  │ Vor Ort/ │   │ nach Ihren│  │ in 3–6  │   │ vor Ort  │          ║
║  │ Telefon  │   │ Wünschen │   │ Wochen   │   │ durch    │          ║
║  │          │   │          │   │          │   │ Fachteam │          ║
║  └──────────┘   └──────────┘   └──────────┘   └──────────┘          ║
║  AOS: "fade-up" delay: 0/150/300/450ms                               ║
║                                                                        ║
║  Karte-BG:   #FFFFFF | border-top: 4px solid #E21212 | R: 12px       ║
║  Karte:      box-shadow: shadow-sm | padding: 32px                   ║
║  Nummer:     Montserrat 900 | 72px | rgba(200,169,110,0.12) | abs.   ║
║  MDI-Icon:   40px | color: #E21212                                    ║
║  Titel:      Montserrat 700 | 20px | #1A2840                         ║
║  Text:       Inter 400 | 15px | #9E9E9E                              ║
║  Pfeil →:    MDI arrow_forward_ios | 28px | #C8A96E                  ║
║                                                                        ║
║  "Fertigstellung innerhalb von 6 Wochen — garantiert."               ║
║  [Jetzt Beratungstermin vereinbaren →] BG: #E21212 | zentriert       ║
╚═════════════════════════════════════════════════════════════════════════╝
MOBILE: 1 Spalte vertikal | Pfeil nach unten ↓
```

---

### S01.06 — REFERENZEN GALERIE

```
╔═════════════════════════════════════════════════════════════════════════╗
║  BG: #1A2840  |  Padding: 80px 0                                      ║
╠═════════════════════════════════════════════════════════════════════════╣
║                                                                        ║
║  [GOLD LABEL]  H2: Über 1.000 erfolgreich realisierte Projekte       ║
║  Montserrat 700 | #FFFFFF | text-center                               ║
║                                                                        ║
║  SWIPER AUTOPLAY (3–4 Bilder sichtbar Desktop):                       ║
║  ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐                ║
║  │ [FOTO 1] │ │ [FOTO 2] │ │ [FOTO 3] │ │ [FOTO 4] │  → autoplay   ║
║  │  Zaun    │ │  Tor     │ │  Carport │ │  Überd.  │                ║
║  │  Wien    │ │  NÖ      │ │  Wien    │ │  Garten  │                ║
║  └──────────┘ └──────────┘ └──────────┘ └──────────┘                ║
║  [◀] ─────────── ● ● ● ● ● ● Pagination ─────────────── [▶]        ║
║                                                                        ║
║  MASONRY GRID (3 Spalten, unterhalb Slider):                          ║
║  ┌────────────────────┐  ┌────────────┐  ┌──────────────────────┐    ║
║  │                    │  │  [FOTO B]  │  │  [FOTO D — klein]    │    ║
║  │   [FOTO A]         │  │            │  │                      │    ║
║  │   2-Spalten-span   │  │  [FOTO C]  │  │  [FOTO E — klein]    │    ║
║  │   Großaufnahme     │  │            │  │  [FOTO F — klein]    │    ║
║  └────────────────────┘  └────────────┘  └──────────────────────┘    ║
║                                                                        ║
║  Hover-Overlay: rgba(226,18,18,0.70) + Projektname + Ort + Kategorie  ║
║  Klick: GLightbox (Swipe-Geste, Tastatur-Navigation)                 ║
║                                                                        ║
║  [Alle Referenzen ansehen →]  btn outline gold | zentriert           ║
╚═════════════════════════════════════════════════════════════════════════╝

Swiper: slidesPerView: 3 (lg) | 2 (md) | 1 (sm)
        autoplay: { delay: 4000, pauseOnMouseEnter: true }
Masonry: CSS columns: 3 (lg) | 2 (md) | 1 (sm) | break-inside: avoid
Bilder:  aspect-ratio: 4/3 | .avif srcset 600w/1200w
```

---

### S01.07 — ÜBER UNS TEASER

```
╔═════════════════════════════════════════════════════════════════════════╗
║  BG: #F8F6F1  |  Padding: 80px 0                                      ║
╠═════════════════════════════════════════════════════════════════════════╣
║  SPLIT LAYOUT 50/50:                                                  ║
║                                                                        ║
║  ┌──────────────────────────────┐  ┌────────────────────────────────┐ ║
║  │ [BILD: Mustergarten /        │  │ [BADGE: Gegründet 2020]        │ ║
║  │  Showroom beleuchtet]        │  │  BG: #E21212 | R: 4px | weiß  │ ║
║  │  aspect-ratio: 4/3 | R: 12px │  │                               │ ║
║  │                              │  │ [GOLD LABEL]                  │ ║
║  │  [▶ Video abspielen]         │  │ H2: Ihr direkter Hersteller   │ ║
║  │  Overlay-Button              │  │ aus Niederösterreich          │ ║
║  │  BG: rgba(226,18,18,0.90)    │  │ Montserrat 700 | 36px | navy  │ ║
║  │  Rund 64px | centered        │  │                               │ ║
║  │                              │  │ ALUBRAM GMBH ist Ihr direkter │ ║
║  │  data-aos="fade-right"       │  │ Aluminium-Hersteller aus NÖ.  │ ║
║  │  data-parallax="0.25"        │  │ [2–3 SEO-Paragraphen]         │ ║
║  │                              │  │                               │ ║
║  │                              │  │ ✅  3 Standorte in NÖ         │ ║
║  │                              │  │ ✅  Mustergarten 24/7         │ ║
║  │                              │  │ ✅  1.000+ Projekte           │ ║
║  │                              │  │ ✅  FN 535870 w               │ ║
║  │                              │  │                               │ ║
║  │                              │  │ [Mehr über uns →]  outline   │ ║
║  └──────────────────────────────┘  └────────────────────────────────┘ ║
║  data-aos="fade-left" für rechts | delay: 150ms                      ║
╚═════════════════════════════════════════════════════════════════════════╝
```

---

### S01.08 — KUNDENMEINUNGEN (Testimonials Slider)

```
╔═════════════════════════════════════════════════════════════════════════╗
║  BG: linear-gradient(135deg, #0F3460 → #1A2840)  |  Padding: 80px 0  ║
╠═════════════════════════════════════════════════════════════════════════╣
║                                                                        ║
║  [GOLD LABEL]  H2: Das sagen unsere Kunden                           ║
║  [⭐⭐⭐⭐⭐ 4.9/5 · Über 120 verifizierte Bewertungen]                  ║
║  Montserrat 500 | 14px | #C8A96E                                      ║
║                                                                        ║
║  ┌── SWIPER FADE SLIDER ──────────────────────────────────────────┐   ║
║  │  [◀]                                                       [▶] │   ║
║  │                                                               │   ║
║  │   ❝ (Playfair Display 120px rgba(200,169,110,0.12) abs.)      │   ║
║  │                                                               │   ║
║  │   "Wir sind absolut begeistert von unserer neuen Zaunanlage!  │   ║
║  │    ALUBRAM hat den gesamten Prozess von der Beratung bis zur  │   ║
║  │    Montage professionell abgewickelt. Lieferung in 4 Wochen   │   ║
║  │    — exakt wie versprochen!"                                  │   ║
║  │    Playfair Display italic | 18px | rgba(255,255,255,0.92)   │   ║
║  │                                                               │   ║
║  │   ⭐⭐⭐⭐⭐  (5/5 Sterne) | #C8A96E | 20px                       │   ║
║  │   — Familie Mayer, Wien                                       │   ║
║  │   Montserrat 600 | 15px | #FFFFFF                             │   ║
║  │   Gekauft: Aluminiumzaun BOLERO 40, Anthrazit RAL 7016       │   ║
║  │   Inter 400 | 13px | #C8A96E                                  │   ║
║  └────────────────────────────────────────────────────────────────┘   ║
║                                                                        ║
║  [● ○ ○ ○ ○]  Swiper Pagination | autoplay: 5500ms | effect: fade    ║
╚═════════════════════════════════════════════════════════════════════════╝

KARTE-SPEC:
  BG:     rgba(255,255,255,0.06) | border: 1px solid rgba(200,169,110,0.2)
  R: 16px | padding: 48px | max-width: 820px | margin: auto
```

---

### S01.09 — CTA BANNER (Kontaktformular Inline)

```
╔═════════════════════════════════════════════════════════════════════════╗
║  BG: #E21212 + Parallax Metalltextur  |  Padding: 80px 0              ║
║  Overlay: rgba(226,18,18,0.92)                                        ║
╠═════════════════════════════════════════════════════════════════════════╣
║                                                                        ║
║  H2: Bereit für Ihre neue Zaunanlage?                                 ║
║  Montserrat 800 | clamp(1.8rem,1.5rem+2vw,3rem) | #FFFFFF             ║
║  Erhalten Sie jetzt Ihr kostenloses, unverbindliches Angebot.         ║
║  Inter 400 | 18px | rgba(255,255,255,0.92)                            ║
║  data-aos="fade-up" data-aos-duration="1200"                          ║
║                                                                        ║
║  ┌──────────────────────────────────────────────────────────────────┐  ║
║  │ BG: rgba(255,255,255,0.10) | backdrop-blur: 10px | R: 12px      │  ║
║  │ border: 1px rgba(255,255,255,0.20) | padding: 40px              │  ║
║  │                                                                  │  ║
║  │  ┌────────────────┐ ┌────────────────┐ ┌──────────────────────┐ │  ║
║  │  │ Ihr Name *     │ │ E-Mail *       │ │ Telefon              │ │  ║
║  │  │ ______________ │ │ ______________ │ │ ____________________  │ │  ║
║  │  └────────────────┘ └────────────────┘ └──────────────────────┘ │  ║
║  │  ┌────────────────────────┐ ┌─────────────────────────────────┐ │  ║
║  │  │ Postleitzahl           │ │ Produktinteresse             ▾  │ │  ║
║  │  │ ______________________ │ │ Zäune / Tore / Carport / ...    │ │  ║
║  │  └────────────────────────┘ └─────────────────────────────────┘ │  ║
║  │  ┌───────────────────────────────────────────────────────────┐  │  ║
║  │  │ Ihre Nachricht (optional)                                 │  │  ║
║  │  │ __________________________________________                │  │  ║
║  │  └───────────────────────────────────────────────────────────┘  │  ║
║  │                                                                  │  ║
║  │  ☐ Ich stimme der Datenschutzerklärung zu. *  [Pflichtf. *]    │  ║
║  │                                                                  │  ║
║  │  [Jetzt kostenlos anfragen →]                                   │  ║
║  │   BG: #1A2840 | Hover: #111B2D | 100% Breite | 54px Höhe       │  ║
║  └──────────────────────────────────────────────────────────────────┘  ║
╚═════════════════════════════════════════════════════════════════════════╝

FORM-TECH: AJAX (kein Reload) | Inline-Erfolgsmeldung | wp_nonce_field()
           Honeypot | HTML5-Validierung + PHP sanitize | → himberg@alubram.at
```

---

### S01.10 — RATGEBER TEASER (Blog)

```
╔═════════════════════════════════════════════════════════════════════════╗
║  BG: #F8F6F1  |  Padding: 80px 0                                      ║
╠═════════════════════════════════════════════════════════════════════════╣
║                                                                        ║
║  [GOLD LABEL]  H2: Ratgeber & Wissenswertes                          ║
║  Tipps rund um Aluminium-Produkte für Ihr Zuhause                    ║
║                                                                        ║
║  ┌──────────────────┐ ┌──────────────────┐ ┌──────────────────┐      ║
║  │ [BILD 16/9]      │ │ [BILD 16/9]      │ │ [BILD 16/9]      │      ║
║  │                  │ │                  │ │                  │      ║
║  │ [KATEGORIE TAG]  │ │ [KATEGORIE TAG]  │ │ [KATEGORIE TAG]  │      ║
║  │  BG: #E21212     │ │  BG: #E21212     │ │  BG: #E21212     │      ║
║  │                  │ │                  │ │                  │      ║
║  │ Aluminiumzaun    │ │ Terrassenüberd.: │ │ Carport planen:  │      ║
║  │ kaufen: Der      │ │ Glas vs. Polyc.  │ │ So geht's        │      ║
║  │ komplette Guide  │ │                  │ │ richtig 2025     │      ║
║  │                  │ │                  │ │                  │      ║
║  │ 15. März 2026    │ │ 10. März 2026    │ │ 5. März 2026     │      ║
║  │ · 8 Min. Lesen   │ │ · 6 Min. Lesen   │ │ · 7 Min. Lesen   │      ║
║  │                  │ │                  │ │                  │      ║
║  │ Excerpt 2 Zeilen │ │ Excerpt 2 Zeilen │ │ Excerpt 2 Zeilen │      ║
║  │                  │ │                  │ │                  │      ║
║  │ [Weiterlesen →]  │ │ [Weiterlesen →]  │ │ [Weiterlesen →]  │      ║
║  └──────────────────┘ └──────────────────┘ └──────────────────┘      ║
║  data-aos="fade-up" delay: 0/100/200ms                               ║
║                                                                        ║
║  [Alle Beiträge ansehen →]  btn outline navy | zentriert             ║
╚═════════════════════════════════════════════════════════════════════════╝

KARTE: bg #FFFFFF | R: 12px | shadow-sm → shadow-md hover
Kategorie-Tag: BG #E21212 | weiß | 11px Montserrat 600 | R: 4px | padding: 4px 10px
MOBILE: Swiper (1.15 sichtbar, 0.15 Vorschau nächster Karte)
```

---

### S01.11 — KONTAKT TEASER

```
╔═════════════════════════════════════════════════════════════════════════╗
║  BG: #1A2840  |  Padding: 80px 0                                      ║
╠═════════════════════════════════════════════════════════════════════════╣
║                                                                        ║
║  ┌────────────────────────────────────────┐  ┌──────────────────────┐ ║
║  │  [GOOGLE MAPS EMBED — 100% Höhe]       │  │  Besuchen Sie uns!  │ ║
║  │  (nur nach Cookie-Akzeptanz)           │  │  H3 Montserrat 700  │ ║
║  │                                        │  │  #FFFFFF | 28px     │ ║
║  │  Platzhalter (vor Cookie-Akzeptanz):   │  │                     │ ║
║  │  [Karten-Bild + "Karte laden" Btn]    │  │  📍 Ortsstr. 31     │ ║
║  │  BG: #0F3460 | centered               │  │     2325 Himberg    │ ║
║  │                                        │  │                     │ ║
║  │                                        │  │  ☎ +43 223 584 793 │ ║
║  │                                        │  │  ☎ +43 664 437 3954│ ║
║  │                                        │  │  ✉ himberg@         │ ║
║  │                                        │  │    alubram.at       │ ║
║  │                                        │  │                     │ ║
║  │                                        │  │  ─────────────────  │ ║
║  │                                        │  │  🕐 Mustergarten    │ ║
║  │                                        │  │  24h · 7 Tage/Wo.  │ ║
║  │                                        │  │                     │ ║
║  │                                        │  │  [Kontaktseite →]   │ ║
║  │                                        │  │   BG: #E21212 🔴    │ ║
║  └────────────────────────────────────────┘  └──────────────────────┘ ║
║   60% Breite                                  40% Breite              ║
╚═════════════════════════════════════════════════════════════════════════╝
```


---

## SEITE 02 — ÜBER UNS

```
URL:       /uber-uns/
Template:  page-uber-uns.php
Schema:    Organization + LocalBusiness + ItemList (Standorte)
Priorität: ⭐⭐⭐⭐
```

```
[TOPBAR] [HEADER solid #FFFFFF]

┌──────────────────────────────────────────────────────────────────┐
│  S02.01 — INNER HERO (60vh)                                     │
│  BG: Parallax-Bild Mustergarten / Showroom                      │
│  Overlay: rgba(17,27,45,0.82)                                   │
│                                                                  │
│  [Breadcrumb: Startseite › Über uns]                           │
│  H1: Über ALUBRAM GMBH                                          │
│   Montserrat 800 | clamp(2.25rem,1.8rem+2.5vw,4rem) | #FFFFFF  │
│  Sub: Ihr direkter Aluminium-Hersteller aus NÖ                  │
│   Inter 400 | 20px | rgba(255,255,255,0.85)                    │
└──────────────────────────────────────────────────────────────────┘

┌──────────────────────────────────────────────────────────────────┐
│  S02.02 — FIRMENSTORY (Split Layout 50/50)                      │
│  BG: #F8F6F1 | Padding: 80px 0                                  │
│                                                                  │
│  ┌──────────────────────────┐  ┌──────────────────────────────┐ │
│  │ [GOLD QUOTE:             │  │ [BILD: Werkstatt oder        │ │
│  │  "Wir sind nicht die     │  │  Portrait Herr Szpak Irek]  │ │
│  │  Größten, aber die       │  │  aspect-ratio: 4/5          │ │
│  │  Besten und Schnellsten"]│  │  border-radius: 12px        │ │
│  │  Playfair italic | 22px  │  │                             │ │
│  │  #C8A96E | max-w: 480px  │  │  [BADGE: Gegr. 2020]       │ │
│  │                          │  │  BG #E21212 | weiß | R: 4px │ │
│  │  H2: Unsere Geschichte   │  │                             │ │
│  │  Montserrat 700 | #1A2840│  │  data-aos="fade-left"       │ │
│  │                          │  │                             │ │
│  │  [3–4 SEO-Paragraphen    │  │                             │ │
│  │   ca. 300–400 Wörter]    │  │                             │ │
│  │  Gegründet 2020 in       │  │                             │ │
│  │  Himberg bei Wien        │  │                             │ │
│  │  3 Standorte | 1.000+   │  │                             │ │
│  │  realisierte Projekte    │  │                             │ │
│  │                          │  │                             │ │
│  │  FN 535870 w             │  │                             │ │
│  │  UID ATU75724307         │  │                             │ │
│  │                          │  │                             │ │
│  │  data-aos="fade-right"   │  │                             │ │
│  └──────────────────────────┘  └──────────────────────────────┘ │
└──────────────────────────────────────────────────────────────────┘

┌──────────────────────────────────────────────────────────────────┐
│  S02.03 — ZAHLEN & FAKTEN (BG: #E21212)                        │
│  Padding: 50px 0                                                │
│                                                                  │
│  ┌─────────┐  ┌─────────┐  ┌─────────┐  ┌─────────┐           │
│  │ 1.000+  │  │  6 Wo.  │  │  24/7   │  │ 3 Std.  │           │
│  │ Projekte│  │ Lieferz.│  │ Muster- │  │ Stand-  │           │
│  │         │  │         │  │ garten  │  │ orte    │           │
│  └─────────┘  └─────────┘  └─────────┘  └─────────┘           │
│  Zahlen: Montserrat 900 | 52px | #FFFFFF | counter-animation   │
│  Labels: Inter 400 | 13px | rgba(255,255,255,0.80)             │
└──────────────────────────────────────────────────────────────────┘

┌──────────────────────────────────────────────────────────────────┐
│  S02.04 — UNSERE 3 STANDORTE                                    │
│  BG: #F8F6F1 | Padding: 80px 0                                  │
│                                                                  │
│  H2: Besuchen Sie uns — 3 Showrooms in NÖ                      │
│                                                                  │
│  ┌──────────────────┐ ┌──────────────────┐ ┌────────────────┐  │
│  │ [BILD Himberg]   │ │ [BILD D-Wagram]  │ │ [BILD Gloggnitz│  │
│  │                  │ │                  │ │                │  │
│  │ HIMBERG          │ │ DEUTSCH-WAGRAM   │ │ GLOGGNITZ      │  │
│  │ (Zentrale)       │ │ (Showroom)       │ │ (Showroom Süd) │  │
│  │ Ortsstr. 31      │ │ Auf Anfrage      │ │ Auf Anfrage    │  │
│  │ 2325 Himberg     │ │                  │ │                │  │
│  │ ★ Mustergarten   │ │                  │ │                │  │
│  │ 24h / 7 Tage     │ │                  │ │                │  │
│  │ [📍 Route →]     │ │ [📍 Route →]     │ │ [📍 Route →]   │  │
│  └──────────────────┘ └──────────────────┘ └────────────────┘  │
│  Karte: bg #FFF | border-top: 3px solid #E21212 | R: 12px      │
└──────────────────────────────────────────────────────────────────┘

┌──────────────────────────────────────────────────────────────────┐
│  S02.05 — UNSERE WERTE (4 USP-Karten)                          │
│  BG: #FFFFFF | Padding: 80px 0                                  │
│                                                                  │
│  H2: Was uns auszeichnet                                        │
│                                                                  │
│  ┌──────────────┐ ┌──────────────┐ ┌──────────────┐ ┌────────┐ │
│  │ [🏭 40px red]│ │ [⚡ 40px red]│ │ [🔧 40px red]│ │[✅ red]│ │
│  │ Direkt-      │ │ Schnelle     │ │ Komplett-    │ │Premium │ │
│  │ hersteller   │ │ Lieferung    │ │ service      │ │Qualität│ │
│  │ Kein         │ │ 3–6 Wochen   │ │ Alles aus    │ │Aluminium│ │
│  │ Zwischen-    │ │ garantiert   │ │ einer Hand   │ │wartungs│ │
│  │ händler      │ │              │ │              │ │frei    │ │
│  └──────────────┘ └──────────────┘ └──────────────┘ └────────┘ │
│  BG: #F8F6F1 | hover: translateY(-4px) + shadow-gold           │
└──────────────────────────────────────────────────────────────────┘

┌──────────────────────────────────────────────────────────────────┐
│  S02.06 — CTA BANNER (BG: #E21212)                             │
│                                                                  │
│  "Lernen Sie uns persönlich kennen —                           │
│   Mustergarten in Himberg, täglich 24 Stunden geöffnet."       │
│                                                                  │
│  [Mustergarten besuchen] outline weiß                           │
│  [Kontakt aufnehmen →] BG: #1A2840                             │
└──────────────────────────────────────────────────────────────────┘

[FOOTER]
```

---

## SEITE 03 — PRODUKTE ÜBERSICHT

```
URL:       /produkte/
Template:  page-produkte.php
Schema:    ItemList (ProductCollection) + BreadcrumbList
Priorität: ⭐⭐⭐⭐⭐
```

```
[INNER HERO 50vh]
  BG: Produktkollage / Studioaufnahme  |  Overlay Navy
  H1: Unsere Aluminium-Produkte — Übersicht
  Sub: Hochwertige Produkte direkt vom Hersteller

[SEO INTRO TEXT 300 Wörter — BG: #F8F6F1]
  H2 mit Keyword "Aluminiumprodukte Hersteller Österreich"
  Container 860px max-width (lesbar)

[FILTER-LEISTE]
  [Alle] [Zäune] [Tore] [Carports] [Überdachungen] [Balkone] [Zubehör]
  Aktiv: BG #E21212 | Inaktiv: border gray | JS-Filter
  Smooth: Isotope.js oder CSS Grid + transition

[PRODUKTKATEGORIE GRID (3 Spalten Desktop, 2 Tablet, 1 Mobile)]

┌─────────────────┐ ┌─────────────────┐ ┌─────────────────┐
│ [BILD 260px]    │ │ [BILD 260px]    │ │ [BILD 260px]    │
│ ZÄUNE &         │ │ TORE &          │ │ CARPORTS        │
│ ZAUNFELDER      │ │ EINFAHRTSTORE   │ │ ALUMINIUM       │
│ 6 Modelle       │ │ 3 Ausführungen  │ │ 2 Varianten     │
│ [→ Entdecken]   │ │ [→ Entdecken]   │ │ [→ Entdecken]   │
└─────────────────┘ └─────────────────┘ └─────────────────┘
┌─────────────────┐ ┌─────────────────┐ ┌─────────────────┐
│ ÜBERDACHUNGEN   │ │ BALKONE &       │ │ ZUBEHÖR &       │
│ 4 Varianten     │ │ GELÄNDER        │ │ SONSTIGES       │
│ [→ Entdecken]   │ │ [→ Entdecken]   │ │ [→ Entdecken]   │
└─────────────────┘ └─────────────────┘ └─────────────────┘
data-aos="zoom-in-up" delay gestaffelt je Karte

[USP LEISTE BG: #E21212]
[CTA KONTAKTFORMULAR BG: #1A2840]
[FOOTER]
```

---

## SEITE 04 — ZÄUNE & ZAUNFELDER (KATEGORIE)

```
URL:       /produkte/zaune/
Template:  page-zaune.php
Schema:    ItemList + BreadcrumbList + FAQPage
Keywords:  Aluminiumzaun, Aluzaun, Zaunfeld, wartungsfreier Zaun
Priorität: ⭐⭐⭐⭐⭐
```

```
[INNER HERO 55vh]
  BG: Parallax — moderne Zaunanlage im Garten, Abendlicht
  [Breadcrumb: Startseite › Produkte › Zäune & Zaunfelder]
  H1: Aluminiumzäune direkt vom Hersteller
  Sub: Qualität, Langlebigkeit & individuelles Design für Ihr Zuhause

[SEO INTRO TEXT — 500+ Wörter — BG: #F8F6F1]
  H2: "Aluminiumzaun kaufen — was Sie wissen müssen"
  2 Spalten: Text (70%) + Bild (30%)
  Keywords: Aluminiumzaun kaufen, wartungsfreier Zaun, Zaunfeld Aluminium
  [CTA inline: "Kostenlose Beratung →"]

[MODELLE GRID (6 Zaunmodelle, 3 Spalten Desktop)]

╔══════════════════════════════════════════════════════════════════╗
║                                                                 ║
║  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐            ║
║  │ [BILD]      │  │ [BILD]      │  │ [BILD]      │            ║
║  │ BOLERO 40   │  │ SONATA 80   │  │ ELEGIA       │           ║
║  │ HORIZONTAL  │  │ HORIZONTAL  │  │ VERTIKAL     │           ║
║  │ ZAUN        │  │ ZAUN        │  │ ZAUN         │           ║
║  │             │  │             │  │              │           ║
║  │ Modern      │  │ Breite      │  │ Zeitlos      │           ║
║  │ 40mm Lamell.│  │ 80mm Lamell.│  │ Eleganz      │           ║
║  │ [→ Details] │  │ [→ Details] │  │ [→ Details]  │           ║
║  └─────────────┘  └─────────────┘  └─────────────┘            ║
║  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐            ║
║  │ IDYLLA      │  │ LAMELLO     │  │ INDUSTRIE-  │            ║
║  │ KLASSISCHER │  │ BLICKDICHTER│  │ ZAUN        │            ║
║  │ ZAUN        │  │ ZAUN        │  │             │            ║
║  │             │  │             │  │ Gewerblich  │            ║
║  │ Dekorativ   │  │ Sichtschutz │  │ Robust      │            ║
║  │ Zeitlos     │  │ 100%        │  │ Hoch belastb│            ║
║  │ [→ Details] │  │ [→ Details] │  │ [→ Details] │            ║
║  └─────────────┘  └─────────────┘  └─────────────┘            ║
║  data-aos="zoom-in-up" delay: 0/100/200/0/100/200ms            ║
╚══════════════════════════════════════════════════════════════════╝

KARTE-SPEC:
  bg #FFFFFF | R: 12px | shadow-sm
  hover: shadow-md + translateY(-6px) | border-top: 3px solid #E21212
  Kategorie-Tag: BG #E21212 | 10px Montserrat 600

[ALUMINIUM-VORTEILE (4 Karten — BG: #1A2840)]
  [🛡 Rostfrei] [⚙ Wartungsfrei] [☀ Witterungsbeständig] [🎨 Alle RAL]

[RAL FARB-PALETTE VISUAL]
  Farbkreis / Swatches | 20px Kreise mit RAL-Nummer
  Hinweis: "Alle RAL-Farben + Holzoptik Thermoprint verfügbar"
  Swiper auf Mobile

[FAQ ZAUN (Accordion — Schema: FAQPage JSON-LD)]
  Q: Wie lange hält ein Aluminiumzaun?
  Q: Was kostet ein Aluminiumzaun pro Meter?
  Q: Welche Höhen sind möglich (800–2000 mm)?
  Q: Brauche ich eine Baugenehmigung in Österreich?
  Q: Wie lange dauert die Lieferung?
  Q: Ist Montage inklusive?
  Q: Kann ich Farbe und Höhe individuell wählen?
  Q: Wie pflege ich meinen Aluminiumzaun?

  Accordion: border-left: 3px solid #E21212 | bg: #F8F6F1 offen
  MDI expand_more | rotation 0→180° | transition: 0.3s ease

[CTA KONTAKTFORMULAR (BG: #E21212)]
[FOOTER]
```

---

## SEITE 05 — TORE & EINFAHRTSTORE (KATEGORIE)

```
URL:       /produkte/tore/
Template:  page-tore.php
Keywords:  Einfahrtstor Aluminium, Schiebetor kaufen, Hoftor Wien
Priorität: ⭐⭐⭐⭐⭐
```

```
[INNER HERO 55vh]
  H1: Aluminiumtore & Einfahrtstore — Sicher & Stilvoll
  [Breadcrumb: Startseite › Produkte › Tore & Einfahrtstore]

[SEO INTRO TEXT — 500+ Wörter]
  H2: "Einfahrtstor aus Aluminium kaufen — Sicherheit und Eleganz"
  Keywords: Einfahrtstor Aluminium, Schiebetor, Hoftor Wien

[PRODUKTKARTEN (3 Modelle — 3 Spalten)]

┌──────────────────┐  ┌──────────────────┐  ┌──────────────────┐
│ [BILD]           │  │ [BILD]           │  │ [BILD]           │
│                  │  │                  │  │                  │
│ SCHIEBETOR       │  │ FLÜGELTOR /      │  │ EINGANGSTOR /    │
│ ALUMINIUM        │  │ EINFAHRTSTOR     │  │ GEHTOR           │
│                  │  │                  │  │                  │
│ Elektrisch mot.  │  │ Zweiflügelig     │  │ Gartentor        │
│ Links- oder      │  │ mit Torantrieb   │  │ Einzel- oder     │
│ Rechtsantrieb    │  │ optional         │  │ zweiflügelig     │
│ Alle RAL-Farben  │  │ Alle RAL-Farben  │  │ Alle RAL-Farben  │
│                  │  │                  │  │                  │
│ [→ Details]      │  │ [→ Details]      │  │ [→ Details]      │
└──────────────────┘  └──────────────────┘  └──────────────────┘

[AUTOMATISIERUNG SEKTION (BG: #1A2840)]
  H2: Automatisierung & Smart Home Integration
  4 Karten:
  [📡 Torantrieb]    [🎮 Handsender]    [📱 GSM-Modul]    [🔔 Sprechanlage]
  Boschart, CAME, FAAC, ROGER — kompatibel

[KOMBINATIONSEMPFEHLUNG]
  "Tor + passender Zaun — aus einer Hand"
  3 Kombinations-Karten: Tor + Zaun-Modell | je [→ Details]

[FAQ TORE (6 Fragen — FAQPage Schema)]
  Q: Welches Tor passt zu meiner Einfahrtsbreite?
  Q: Ist Automatisierung inklusive oder optional?
  Q: Kann ich nachträglich einen Antrieb einbauen lassen?
  Q: Wie sicher sind Aluminiumtore?
  Q: Wie lange dauert Lieferung und Montage?
  Q: Welche Breiten und Höhen sind möglich?

[CTA BANNER BG: #E21212]
[FOOTER]
```

---

## SEITE 06 — CARPORTS

```
URL:       /produkte/carports/
Template:  page-carports.php
Keywords:  Carport Aluminium kaufen Wien, Carport Hersteller Österreich
Priorität: ⭐⭐⭐⭐⭐
```

```
[INNER HERO 55vh]
  H1: Carports aus Aluminium — Direkthersteller Österreich
  [Breadcrumb: Startseite › Produkte › Carports]

[SEO BESCHREIBUNG + SWIPER GALERIE (Split 55/45)]
  Links: Text 600–800 Wörter
    H2: "Carport aus Aluminium kaufen — Die clevere Lösung"
    Vorteile: Rostfrei, langlebig, maßgefertigt, alle RAL
    Ausführungen: Einzelcarport | Doppelcarport | Mit Abstellraum
  Rechts: Swiper (4 Bilder, Thumbnails unten)

[MODELLVARIANTEN (3 Karten)]

┌────────────────────┐  ┌────────────────────┐  ┌────────────────────┐
│ [BILD]             │  │ [BILD]             │  │ [BILD]             │
│ EINZELCARPORT      │  │ DOPPELCARPORT      │  │ CARPORT MIT        │
│                    │  │                    │  │ ABSTELLRAUM        │
│ Für 1 Fahrzeug     │  │ Für 2 Fahrzeuge    │  │ Stauraum           │
│ Breite: 2,5–3,5 m  │  │ Breite: 5–6 m     │  │ integriert         │
│ Tiefe:  4,8–7 m    │  │ Tiefe:  4,8–7 m   │  │                    │
│                    │  │                    │  │                    │
│ [→ Details]        │  │ [→ Details]        │  │ [→ Details]        │
└────────────────────┘  └────────────────────┘  └────────────────────┘

[TECHNISCHE DATEN TABELLE (BG: #F8F6F1)]
  | Merkmal      | Einzelcarport | Doppelcarport |
  | Breite       | 2,5–3,5 m    | 5,0–6,0 m    |
  | Tiefe        | 4,8–7,0 m    | 4,8–7,0 m    |
  | Dachhöhe     | ab 2,1 m     | ab 2,1 m     |
  | Traglast     | 150 kg/m²    | 150 kg/m²    |
  | Garantie     | 15 Jahre     | 15 Jahre     |
  Tabelle: alternierend #F8F6F1/#FFFFFF | header BG: #1A2840 weiß

[DACH-KONFIGURATIONSOPTIONEN VISUAL]
  Dachform:  [Flachdach] [Satteldach] [Pultdach]  (Toggle-Buttons)
  Material:  [Polycarbonat klar] [Polycarbonat opal] [Glas] [Sandwichpanel]
  Farbe:     RAL-Swatches (20px Kreise, 6 häufigste + "Alle RAL anfragen")

[FAQ CARPORT (6 Fragen)]
  Q: Brauche ich eine Baugenehmigung für einen Carport in Österreich?
  Q: Kann der Carport an die Hauswand gebaut werden?
  Q: Wie lange dauert Lieferung und Montage?
  Q: Welche Dachformen sind möglich?
  Q: Welche Schneelast trägt der Carport?
  Q: Kann ich den Carport nachträglich erweitern?

[ÄHNLICHE PRODUKTE (Überdachungen, Pergola)]
[CTA BANNER BG: #E21212]
[FOOTER]
```

---

## SEITE 07 — ÜBERDACHUNGEN (KATEGORIE)

```
URL:       /produkte/ueberdachungen/
Template:  page-ueberdachungen.php
Keywords:  Terrassenüberdachung Aluminium, Pergola kaufen, Vordach
Priorität: ⭐⭐⭐⭐⭐
```

```
[INNER HERO 55vh]
  H1: Aluminium-Überdachungen & Terrassendächer
  [Breadcrumb: Startseite › Produkte › Überdachungen]

[SEO INTRO TEXT 500+ Wörter]

[MODELL GRID (4 Varianten — 2×2 Desktop, 1 Col Mobile)]

╔══════════════════════════════════════════════════════════════════╗
║  ┌──────────────────────┐  ┌──────────────────────┐            ║
║  │ [BILD Pergola]       │  │ [BILD Vordach]       │            ║
║  │                      │  │                      │            ║
║  │ PERGOLA              │  │ VORDACH              │            ║
║  │ Freistehend oder     │  │ Eingangsüberdachung  │            ║
║  │ wandmontiert         │  │ Hauseingang, Türe    │            ║
║  │                      │  │                      │            ║
║  │ Offen oder           │  │ Kompakt, edel        │            ║
║  │ mit Dacheindeckung   │  │ alle RAL-Farben      │            ║
║  │ LED, Markise optional│  │                      │            ║
║  │ [→ Mehr Details]     │  │ [→ Mehr Details]     │            ║
║  └──────────────────────┘  └──────────────────────┘            ║
║  ┌──────────────────────┐  ┌──────────────────────┐            ║
║  │ [BILD Terr. Premium] │  │ [BILD Terr. Standard]│            ║
║  │                      │  │                      │            ║
║  │ TERRASSENÜBERD.      │  │ TERRASSENÜBERD.      │            ║
║  │ PREMIUM              │  │ STANDARD             │            ║
║  │ Comfort-Edition      │  │ Solide Ausführung    │            ║
║  │ GIGA-Regenrinne      │  │ GIGA-Regenrinne      │            ║
║  │ Profil 120×80 mm     │  │ Profil 80×60 mm      │            ║
║  │ LED, Markise optional│  │                      │            ║
║  │ [→ Mehr Details]     │  │ [→ Mehr Details]     │            ║
║  └──────────────────────┘  └──────────────────────┘            ║
╚══════════════════════════════════════════════════════════════════╝

[VERGLEICHSTABELLE Premium vs. Standard (BG: #F8F6F1)]
  | Feature             | PREMIUM       | STANDARD      |
  | Profil-Querschnitt  | 120 × 80 mm  | 80 × 60 mm   |
  | GIGA-Regenrinne     | ✅ inklusive  | ✅ inklusive  |
  | LED-Beleuchtung     | ⬜ Optional   | —            |
  | Markise             | ⬜ Optional   | —            |
  | Lamellenrollo       | ⬜ Optional   | —            |
  | Glasdach            | ⬜ Optional   | ⬜ Optional   |
  | Polycarbonat        | ⬜ Optional   | ⬜ Optional   |
  | Garantie            | 15 Jahre      | 15 Jahre      |
  Header: BG #1A2840 | weiß | ✅ = green #2D7D46 | — = #9E9E9E

[DACHEINDECKUNG OPTIONEN VISUAL]
  [🔷 Klarglas] [🔷 Satinato] [🔷 Polycarbonat klar] [🔷 Polycarbonat opal]
  Je Option: Bildvorschau + Beschreibung + Vorteile

[ZUBEHÖR OPTIONEN (4 Karten)]
  [💡 LED Beleuchtung] [🌿 Markise] [🪟 Lamellenrollo] [❄ Schneefang]

[FAQ ÜBERDACHUNGEN (7 Fragen — FAQPage Schema)]
  Q: Brauche ich eine Baugenehmigung für eine Terrassenüberdachung?
  Q: Welche Windlast und Schneelast ist zulässig?
  Q: Kann die Überdachung an die Hauswand befestigt werden?
  Q: Welche Abmessungen sind möglich?
  Q: Kann ich Glas oder Polycarbonat wählen?
  Q: Wie lange dauert die Montage?
  Q: Gibt es Farb- und Designoptionen?

[CTA BANNER BG: #E21212]
[FOOTER]
```


---

## SEITE 08 — SINGLE PRODUKT (Template)

```
URL:       /produkte/{kategorie}/{slug}/
Template:  single-alubram_product.php
Schema:    Product + BreadcrumbList + FAQPage + AggregateRating
Priorität: ⭐⭐⭐⭐
```

```
[TOPBAR] [HEADER solid]

┌──────────────────────────────────────────────────────────────────────┐
│  S08.01 — PRODUKT HERO / SPLIT LAYOUT                               │
│  BG: #F8F6F1 | min-height: 80vh                                     │
│  [Breadcrumb: Startseite › Produkte › Zäune › BOLERO 40]           │
│                                                                      │
│  ┌─────────────────────────────┐  ┌──────────────────────────────┐  │
│  │  SWIPER GALERIE (45%)       │  │  PRODUKTINFO (55%)           │  │
│  │  Thumbnails unten (4 Bilder)│  │                              │  │
│  │  Klick → Lightbox GLightbox │  │  [Kategorie-Tag BG #E21212]  │  │
│  │                             │  │  Zäune & Zaunfelder          │  │
│  │  [BILD HAUPTFOTO]           │  │                              │  │
│  │  aspect-ratio: 4/3          │  │  H1: BOLERO 40               │  │
│  │  .avif srcset               │  │   Aluminium-Horizontalzaun   │  │
│  │  data-aos="fade-right"      │  │   Montserrat 800 | 36px      │  │
│  │                             │  │   #1A2840                    │  │
│  │  [▸ BILD] [▸ BILD] [▸ BILD]│  │                              │  │
│  │  [▸ BILD]  Thumbnail-Bar   │  │  ⭐⭐⭐⭐⭐ 4.9 (38 Bewertungen) │  │
│  │  60px | border hover #E21212│  │   Inter 400 | 14px | #C8A96E │  │
│  │                             │  │                              │  │
│  │                             │  │  ─ Gold Trennlinie ──────    │  │
│  │                             │  │                              │  │
│  │                             │  │  ✅ Rostfrei, wartungsfrei   │  │
│  │                             │  │  ✅ Lieferung in 3–6 Wochen  │  │
│  │                             │  │  ✅ Montage inklusive        │  │
│  │                             │  │  ✅ Alle RAL-Farben          │  │
│  │                             │  │  ✅ 15 Jahre Garantie        │  │
│  │                             │  │                              │  │
│  │                             │  │  [STICKY SIDEBAR FORMULAR]   │  │
│  │                             │  │  BG: #1A2840 | R: 12px      │  │
│  │                             │  │  padding: 28px              │  │
│  │                             │  │                              │  │
│  │                             │  │  "Angebot anfordern"         │  │
│  │                             │  │  Montserrat 700 | 18px #FFF  │  │
│  │                             │  │                              │  │
│  │                             │  │  [Name *     ]               │  │
│  │                             │  │  [Telefon    ]               │  │
│  │                             │  │  [E-Mail *   ]               │  │
│  │                             │  │  [PLZ        ]               │  │
│  │                             │  │  [Nachricht  ]               │  │
│  │                             │  │  ☐ Datenschutz *             │  │
│  │                             │  │  [Jetzt anfragen →] #E21212  │  │
│  └─────────────────────────────┘  └──────────────────────────────┘  │
└──────────────────────────────────────────────────────────────────────┘

┌──────────────────────────────────────────────────────────────────────┐
│  S08.02 — INHALTS-TABS                                              │
│  BG: #FFFFFF                                                        │
│                                                                      │
│  [Beschreibung] [Technische Daten] [Farben & Varianten]             │
│  [Montage]      [FAQ]                                               │
│                                                                      │
│  Aktiver Tab: border-bottom: 3px solid #E21212 | color #E21212     │
│  Inaktiv:     color #9E9E9E | hover color #1A2840                   │
│  Montserrat 500 | 15px                                              │
│                                                                      │
│  TAB: BESCHREIBUNG                                                  │
│    H2 mit Produkt-Keyword                                           │
│    800+ Wörter SEO-Text | 2–3 Absätze                              │
│    Inline-Bild (float right, 340px)                                 │
│    data-aos="fade-up"                                               │
│                                                                      │
│  TAB: TECHNISCHE DATEN                                              │
│    Responsive Tabelle:                                              │
│    | Profil-Breite   | 40 mm / 80 mm        |                      │
│    | Profil-Höhe     | 800–2000 mm          |                      │
│    | Lamellenabstand | 50 mm                |                      │
│    | Material        | Aluminium EN AW-6063 |                      │
│    | Oberflächenb.   | Pulverbeschichtung   |                      │
│    | Farben          | Alle RAL + Holzoptik |                      │
│    | Lieferzeit      | 3–6 Wochen           |                      │
│    | Garantie        | 15 Jahre             |                      │
│                                                                      │
│  TAB: FARBEN & VARIANTEN                                            │
│    RAL-Swatches (30px Kreise, 20+ Farben)                          │
│    Hover: Tooltip mit RAL-Nummer + Name                            │
│    "Sonderfarben & Holzoptik Thermoprint auf Anfrage"              │
│                                                                      │
│  TAB: MONTAGE                                                       │
│    Schritt-für-Schritt Bild-Text                                    │
│    Montage durch ALUBRAM-Fachteam | Eigeninstallation möglich       │
│                                                                      │
│  TAB: FAQ                                                           │
│    Produktspezifische FAQs (Schema: FAQPage)                       │
└──────────────────────────────────────────────────────────────────────┘

┌──────────────────────────────────────────────────────────────────────┐
│  S08.03 — TECHNISCHE VORTEILE (4 Karten — BG: #F8F6F1)             │
│  ┌────────────┐ ┌────────────┐ ┌────────────┐ ┌────────────┐       │
│  │[🛡 MDI red]│ │[⚙ MDI red] │ │[☀ MDI red] │ │[🎨 MDI red]│       │
│  │ Rostfrei   │ │ Wartungs-  │ │ Witterungs-│ │ Alle RAL-  │       │
│  │ Aluminium  │ │ frei       │ │ beständig  │ │ Farben     │       │
│  └────────────┘ └────────────┘ └────────────┘ └────────────┘       │
└──────────────────────────────────────────────────────────────────────┘

┌──────────────────────────────────────────────────────────────────────┐
│  S08.04 — ÄHNLICHE PRODUKTE (3 Karten)                             │
│  H2: Das könnte Sie auch interessieren                              │
│  3 × Produktkarte (selbe Kategorie oder Ergänzungsprodukte)        │
└──────────────────────────────────────────────────────────────────────┘

[CTA BANNER BG: #E21212]
[FOOTER]

MOBILE SPEZIFIKATION:
┌──────────────────────────────────┐
│  [SWIPER GALERIE 100% Breite]    │
│  [Thumbnails als Scrollbar]      │
│  H1 | Tags | Sterne-Rating       │
│  USP Checkmarks                  │
│  [TABS → horizontal scrollbar]   │
│  Tab-Inhalt                      │
│  ─────────────────────────────── │
│  STICKY BOTTOM BAR (position:    │
│  fixed bottom 0 | BG: #E21212)  │
│  [📋 ANGEBOT ANFORDERN →]        │
│  tap → öffnet Modal-Formular     │
│  Höhe: 56px | 100% Breite        │
└──────────────────────────────────┘
```

---

## SEITE 09 — REFERENZEN & GALERIE

```
URL:       /referenzen/
Template:  page-referenzen.php
Schema:    ImageGallery + BreadcrumbList
Keywords:  Aluminiumzaun Referenzen Wien, Carport realisiert NÖ
Priorität: ⭐⭐⭐⭐
```

```
[INNER HERO 55vh]
  BG: Collage aus Projektfotos
  H1: Unsere realisierten Projekte — Über 1.000 Referenzen
  [Breadcrumb: Startseite › Referenzen]

┌──────────────────────────────────────────────────────────────────────┐
│  FILTER-LEISTE (Sticky oben beim Scrollen)                          │
│  BG: #FFFFFF | border-bottom: 1px solid #E8E8E8                    │
│  padding: 16px 0 | box-shadow: 0 2px 10px rgba(0,0,0,0.06)        │
│                                                                      │
│  [Alle]  [Zäune]  [Tore]  [Carports]  [Überdachungen]  [Kombination]│
│  [Wien]  [NÖ]  [Niederösterreich]  [Sonstige]                      │
│                                                                      │
│  Aktiv: BG #E21212 | weiß | R: 4px                                 │
│  Inaktiv: border: 1px solid #E8E8E8 | #2D2D2D                      │
│  JS: Isotope.js Filter | smooth animation                          │
└──────────────────────────────────────────────────────────────────────┘

┌──────────────────────────────────────────────────────────────────────┐
│  MASONRY GALERIE (4 Spalten Desktop / 2 Tablet / 1 Mobile)         │
│                                                                      │
│  ┌────────┐  ┌────────┐  ┌────────┐  ┌────────┐                   │
│  │        │  │  ████  │  │        │  │  ████  │                   │
│  │  ████  │  │  ████  │  │  ████  │  │  ████  │                   │
│  │  ████  │  │  ████  │  │  ████  │  │        │                   │
│  │        │  │        │  │        │  │  ████  │                   │
│  │        │  │  ████  │  │  ████  │  │  ████  │                   │
│  │  ████  │  │        │  │  ████  │  │        │                   │
│  └────────┘  └────────┘  └────────┘  └────────┘                   │
│  (Bilder variieren in Höhe — Masonry: CSS columns)                 │
│                                                                      │
│  Hover-Overlay (transform scale(1.02) + Overlay):                  │
│    BG: rgba(226,18,18,0.72)                                        │
│    [📷 VERGRÖSSERN] MDI icon weiß | zentriert                     │
│    Projektname | Ort | Kategorie-Badge                             │
│                                                                      │
│  Klick → GLightbox:                                                │
│    Navigation Pfeile | Tastatur | Swipe Mobile                     │
│    Caption: Projektname + Ort + Produktkategorie                   │
│                                                                      │
│  Infinite Scroll: Lade 12 weitere bei Scroll-Ende                  │
│  Loading Spinner: BG #E21212 | centered                           │
└──────────────────────────────────────────────────────────────────────┘

┌──────────────────────────────────────────────────────────────────────┐
│  STATISTIK BANNER (BG: #E21212)                                    │
│                                                                      │
│  [1.000+      ]  [15 J.       ]  [3 Standorte ]  [⭐⭐⭐⭐⭐ 4.9 ]   │
│  [Projekte    ]  [Erfahrung   ]  [in NÖ       ]  [Bewertung  ]    │
│  Zahlen: Montserrat 900 | 44px | #FFFFFF                          │
│  Labels: Inter 400 | 13px | rgba(255,255,255,0.85)                │
└──────────────────────────────────────────────────────────────────────┘

[CTA: "Ihr Projekt wird das nächste — Jetzt anfragen" BG: #1A2840]
[FOOTER]
```

---

## SEITE 10 — LEISTUNGEN

```
URL:       /leistungen/
Template:  page-leistungen.php
Schema:    Service + LocalBusiness + BreadcrumbList
Keywords:  Montage Zaunanlage Österreich, Aluminiumzaun Beratung Wien
Priorität: ⭐⭐⭐⭐
```

```
[INNER HERO 55vh]
  H1: Unsere Leistungen — Alles aus einer Hand
  [Breadcrumb: Startseite › Leistungen]

┌──────────────────────────────────────────────────────────────────────┐
│  PROZESS ÜBERSICHT — TIMELINE (BG: #F8F6F1)                        │
│                                                                      │
│  H2: Von der ersten Anfrage bis zur Fertigstellung                  │
│                                                                      │
│  ●━━━━━━━━━━━━━●━━━━━━━━━━━━━●━━━━━━━━━━━━━●━━━━━━━━━━━━━●         │
│  ↓             ↓             ↓             ↓             ↓          │
│  [01]          [02]          [03]          [04]          [05]        │
│  Anfrage       Beratung      Planung       Produktion    Montage     │
│  & Kontakt     vor Ort       & Angebot     & Lieferung   & Abnahme  │
│                                                                      │
│  Timeline: horizontal line #E21212 | Kreis BG #E21212 weiß Nr.     │
│  AOS: "fade-up" gestaffelt 0/100/200/300/400ms                     │
└──────────────────────────────────────────────────────────────────────┘

┌──────────────────────────────────────────────────────────────────────┐
│  LEISTUNGSDETAILS — AKKORDEON (BG: #FFFFFF)                        │
│  H2: Was wir für Sie tun                                           │
│                                                                      │
│  ▼ [🏠 Individuelle Beratung]                                       │
│     Kostenlose Erstberatung vor Ort oder telefonisch               │
│     Analyse der baulichen Gegebenheiten                            │
│     Vermessungsservice inklusive                                    │
│                                                                      │
│  ▶ [📐 Planung & Projektierung]                                     │
│  ▶ [🏭 Maßgefertigte Produktion]                                    │
│  ▶ [🚚 Direkte Lieferung]                                           │
│  ▶ [🔧 Professionelle Montage]                                      │
│  ▶ [✅ Qualitätskontrolle & Abnahme]                               │
│  ▶ [📞 After-Sales Service]                                         │
│                                                                      │
│  Akkordeon: max-height 0→auto | border-left: 3px solid #E21212     │
│  MDI 24px rot | Pfeil rotate 0°→180° | transition: 0.3s ease       │
└──────────────────────────────────────────────────────────────────────┘

┌──────────────────────────────────────────────────────────────────────┐
│  SERVICEGEBIET (Google Maps + Auflistung)                           │
│  BG: #1A2840                                                        │
│                                                                      │
│  H2: Unser Servicegebiet                                           │
│  Österreich, Schwerpunkt NÖ & Wien                                 │
│                                                                      │
│  [Maps Embed 60%] | [Regionen-Liste 40%]                           │
│  • Wien & Umgebung  • NÖ gesamt                                    │
│  • Burgenland        • Steiermark                                  │
│  • Auf Anfrage: gesamtes DACH-Gebiet                               │
└──────────────────────────────────────────────────────────────────────┘

┌──────────────────────────────────────────────────────────────────────┐
│  GARANTIE & QUALITÄT (BG: #F8F6F1)                                 │
│  3 Karten:                                                         │
│  [🛡 15 Jahre Garantie] [📋 Zertifiziert] [🏆 Premium Aluminium]   │
└──────────────────────────────────────────────────────────────────────┘

[CTA BANNER BG: #E21212]
[FOOTER]
```

---

## SEITE 11 — KONTAKT

```
URL:       /kontakt/
Template:  page-kontakt.php
Schema:    LocalBusiness + BreadcrumbList + ContactPage
Keywords:  Aluminiumzaun Beratung Wien, Zaunanlage Angebot einholen
Priorität: ⭐⭐⭐⭐⭐
```

```
[INNER HERO 45vh]
  H1: Kontaktieren Sie uns — Kostenlose Beratung
  [Breadcrumb: Startseite › Kontakt]
  Sub: Rufen Sie an, schreiben Sie oder besuchen Sie uns persönlich

┌──────────────────────────────────────────────────────────────────────┐
│  3 KONTAKTMETHODEN (Karten — BG: #F8F6F1)                          │
│                                                                      │
│  ┌──────────────────┐  ┌──────────────────┐  ┌──────────────────┐  │
│  │ [📞 MDI 48px rot]│  │ [✉ MDI 48px rot] │  │ [📍 MDI 48px rot]│  │
│  │                  │  │                  │  │                  │  │
│  │ Anrufen          │  │ E-Mail schreiben │  │ Persönlich       │  │
│  │                  │  │                  │  │ besuchen         │  │
│  │ +43 (0) 223      │  │ himberg@         │  │ Mustergarten     │  │
│  │ 584 793          │  │ alubram.at       │  │ Himberg 24/7     │  │
│  │                  │  │ wien@alubram.at  │  │                  │  │
│  │ Mo–So 8–20 Uhr   │  │ Antwort in 24h  │  │ Tägl. 0–24 Uhr   │  │
│  │                  │  │                  │  │                  │  │
│  │ [☎ Jetzt anrufen]│  │ [✉ E-Mail →]    │  │ [📍 Route planen]│  │
│  │  BG: #E21212     │  │  BG: #E21212     │  │  BG: #E21212     │  │
│  └──────────────────┘  └──────────────────┘  └──────────────────┘  │
│  data-aos="zoom-in-up" delay: 0/100/200ms                          │
│  Karte: BG #FFFFFF | R: 12px | shadow-sm | border-top: 3px #E21212 │
└──────────────────────────────────────────────────────────────────────┘

┌──────────────────────────────────────────────────────────────────────┐
│  KONTAKTFORMULAR + GOOGLE MAPS (2 Spalten 55/45)                   │
│  BG: #FFFFFF | Padding: 80px 0                                      │
│                                                                      │
│  ┌──────────────────────────────┐  ┌──────────────────────────────┐ │
│  │ H2: Anfrage stellen          │  │ [GOOGLE MAPS EMBED]          │ │
│  │     Montserrat 700 | #1A2840 │  │ Höhe: 500px | border-R: 12px │ │
│  │                              │  │                              │ │
│  │  [Name *         ]           │  │ (DSGVO: erst nach Cookie-    │ │
│  │  [Firma          ]           │  │  Zustimmung sichtbar)        │ │
│  │  [E-Mail *       ]           │  │                              │ │
│  │  [Telefon        ]           │  │ Platzhalter:                 │ │
│  │  [PLZ *          ]           │  │ BG: #F8F6F1                  │ │
│  │  [Produkt ▾      ]           │  │ Karten-Icon #E21212 centered │ │
│  │    Zäune / Tore / Carports   │  │ "Karte laden" — Button       │ │
│  │    Überdachungen / Sonstiges │  │ outline-red                  │ │
│  │  [Nachricht       ]          │  │                              │ │
│  │  [           3 Zeilen]       │  │ ── Adresse-Box ────────────  │ │
│  │  ☐ Datenschutz zustimmen *   │  │ 📍 Hintere Ortsstraße 31    │ │
│  │  ☐ Newsletter (optional)     │  │    2325 Himberg bei Wien     │ │
│  │                              │  │ ☎ +43 (0) 223 584 793       │ │
│  │  [Jetzt anfragen →] #E21212  │  │ ✉ himberg@alubram.at        │ │
│  │   100% Breite | 54px Höhe    │  │ 🕐 Mustergarten 24h/7 Tage  │ │
│  │   AJAX | inline Erfolg-MSG   │  │                              │ │
│  └──────────────────────────────┘  └──────────────────────────────┘ │
└──────────────────────────────────────────────────────────────────────┘

┌──────────────────────────────────────────────────────────────────────┐
│  3 STANDORT-KARTEN (BG: #F8F6F1)                                   │
│                                                                      │
│  H2: Besuchen Sie einen unserer Standorte                          │
│                                                                      │
│  ┌──────────────────┐  ┌──────────────────┐  ┌──────────────────┐  │
│  │ ★ HIMBERG        │  │ DEUTSCH-WAGRAM   │  │ GLOGGNITZ        │  │
│  │ (Zentrale)       │  │ (Showroom)       │  │ (Showroom Süd)   │  │
│  │ Ortsstr. 31      │  │                  │  │                  │  │
│  │ 2325 Himberg     │  │ +43 664 437 3954 │  │ Auf Anfrage      │  │
│  │                  │  │                  │  │                  │  │
│  │ +43 223 584 793  │  │ wien@alubram.at  │  │                  │  │
│  │ himberg@alubram  │  │                  │  │                  │  │
│  │                  │  │                  │  │                  │  │
│  │ 🕐 24h / 7 Tage  │  │ Mo–Fr 8–18 Uhr   │  │ Mo–Fr 8–17 Uhr   │  │
│  │ Mustergarten!    │  │ Sa 8–14 Uhr      │  │ Termine möglich  │  │
│  │                  │  │                  │  │                  │  │
│  │ [📍 Route →]     │  │ [📍 Route →]     │  │ [📍 Route →]     │  │
│  └──────────────────┘  └──────────────────┘  └──────────────────┘  │
│  Karte: BG #FFF | R: 12px | shadow-sm | border-top: 3px #E21212   │
└──────────────────────────────────────────────────────────────────────┘

┌──────────────────────────────────────────────────────────────────────┐
│  FAQ KONTAKT (Accordion — 5 Fragen)                                │
│  Q: Wie kann ich ein Angebot anfragen?                             │
│  Q: Wie lange dauert es bis zur Antwort?                           │
│  Q: Ist die Erstberatung kostenlos?                                │
│  Q: Kommen Sie zur Vermessung zu mir nach Hause?                   │
│  Q: Wann ist der Mustergarten geöffnet?                            │
└──────────────────────────────────────────────────────────────────────┘

[FOOTER]
```


---

## SEITE 12 — STANDORTE

```
URL:       /kontakt/standorte/
Template:  page-standorte.php
Schema:    LocalBusiness (3×) + BreadcrumbList
Priorität: ⭐⭐⭐
```

```
[INNER HERO 45vh]
  H1: Unsere Standorte — Besuchen Sie uns persönlich
  [Breadcrumb: Startseite › Kontakt › Standorte]

[3 STANDORT-KARTEN (detailliert) — gleich wie Kontaktseite, aber ausführlicher]
  + Google Maps Mini-Embed je Standort (inline, nach Cookie-Akzeptanz)
  + Öffnungszeiten Tabelle je Standort
  + Wegbeschreibung (2–3 Sätze)

[GOOGLE MAPS VOLLBILD (alle 3 Pins) — nach Cookie-Akzeptanz]
  Höhe: 500px | 3 rote Marker | Popup je Standort

[ÖFFNUNGSZEITEN ÜBERSICHT TABELLE]
  | Tag       | Himberg (Zentrale) | Deutsch-Wagram | Gloggnitz |
  | Montag    | 24h (Mustergarten) | 8:00–18:00     | 8:00–17:00|
  | Dienstag  | 24h (Mustergarten) | 8:00–18:00     | 8:00–17:00|
  | ...       | ...                | ...            | ...       |
  | Samstag   | 24h (Mustergarten) | 8:00–14:00     | auf Anfr. |
  | Sonntag   | 24h (Mustergarten) | geschlossen    | auf Anfr. |
  Header BG: #1A2840 weiß | Alternierend #F8F6F1/#FFFFFF

[CTA BANNER BG: #E21212]
[FOOTER]
```

---

## SEITE 13 — RATGEBER (BLOG-ARCHIV)

```
URL:       /ratgeber/
Template:  archive.php (WordPress Standard-Archiv)
Schema:    Blog + BreadcrumbList + ItemList
Keywords:  Aluminiumzaun Ratgeber, Carport planen Tipps, Terrassenüberdachung
Priorität: ⭐⭐⭐
```

```
[INNER HERO 40vh]
  H1: Ratgeber — Alles rund um Aluminium-Produkte
  Sub: Tipps, Kaufratgeber und Infos für Ihren Außenbereich
  [Breadcrumb: Startseite › Ratgeber]

┌──────────────────────────────────────────────────────────────────────┐
│  LAYOUT: 70% Inhalt + 30% Sidebar                                   │
│                                                                      │
│  KATEGORIE-FILTER (über Grid):                                      │
│  [Alle] [Zäune] [Tore] [Carports] [Überdachungen] [Kaufberatung]   │
│  Aktiv: BG #E21212 | Inaktiv: border gray                          │
│                                                                      │
│  FEATURED ARTIKEL (volle Breite 70%):                              │
│  ┌──────────────────────────────────────────────────────────────┐  │
│  │ [BILD 16:9 — 100% Breite]                                    │  │
│  │                                                              │  │
│  │ [FEATURED TAG BG #C8A96E]                                    │  │
│  │ H2: Aluminiumzaun kaufen 2026: Der komplette Guide           │  │
│  │ Inter 400 | 3-Zeilen Excerpt                                 │  │
│  │ 15. März 2026 · 8 Min. Lesen · [Zäune TAG]                  │  │
│  │ [Vollständig lesen →]                                        │  │
│  └──────────────────────────────────────────────────────────────┘  │
│                                                                      │
│  ARTIKEL GRID (3 Spalten, 9 pro Seite, Standard Karten):           │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐               │
│  │[BILD 16:9]  │  │[BILD 16:9]  │  │[BILD 16:9]  │               │
│  │[KAT #E21212]│  │[KAT #E21212]│  │[KAT #E21212]│               │
│  │ Titel H3    │  │ Titel H3    │  │ Titel H3    │               │
│  │ 10. März    │  │ 5. März     │  │ 28. Febr.   │               │
│  │ · 6 Min.    │  │ · 7 Min.    │  │ · 5 Min.    │               │
│  │ Excerpt...  │  │ Excerpt...  │  │ Excerpt...  │               │
│  │[Lesen →]    │  │[Lesen →]    │  │[Lesen →]    │               │
│  └─────────────┘  └─────────────┘  └─────────────┘               │
│  Karte: BG #FFF | R:12px | shadow-sm | hover shadow-md +Y(-6px)   │
│                                                                      │
│  PAGINATION:                                                        │
│  [◀ Zurück]  [1] [2] [3] ... [8]  [Weiter ▶]                      │
│  Aktiv: BG #E21212 | weiß | R: 4px                                │
└──────────────────────────────────────────────────────────────────────┘

┌──────────────────────────────────────────────────────────────────────┐
│  SIDEBAR (30%) — sticky top: 110px                                 │
│                                                                      │
│  [🔍 SUCHE]                                                         │
│  ____________________________________ [Suchen]                     │
│                                                                      │
│  [BELIEBTE BEITRÄGE]                                               │
│  1. Aluminiumzaun kaufen Guide                                     │
│  2. Terrassenüberdachung Planung                                   │
│  3. Carport oder Garage?                                           │
│                                                                      │
│  [KATEGORIEN]                                                      │
│  Zäune (12)                                                        │
│  Tore (8)                                                          │
│  Carports (6)                                                      │
│  Überdachungen (10)                                                │
│  Kaufberatung (15)                                                 │
│                                                                      │
│  [NEWSLETTER ANMELDUNG — BG: #1A2840]                             │
│  "Tipps & Angebote direkt ins Postfach"                           │
│  [E-Mail eingeben...] [Anmelden →]                                │
│  ☐ Datenschutz zustimmen                                          │
│                                                                      │
│  [CTA-WIDGET BG: #E21212]                                         │
│  "Kostenlose Beratung!"                                           │
│  ☎ Jetzt anrufen                                                  │
└──────────────────────────────────────────────────────────────────────┘

[FOOTER]

MOBILE: Sidebar unter Artikelgrid | Kategorie-Filter horizontal scrollbar
```

---

## SEITE 14 — SINGLE BLOG-ARTIKEL

```
URL:       /ratgeber/{slug}/
Template:  single.php
Schema:    Article + BreadcrumbList + Person (Autor) + FAQPage (opt.)
Keywords:  Long-tail Keyword aus Artikel-Thema
Priorität: ⭐⭐⭐
```

```
[INNER HERO 45vh — Artikel-Titelbild als parallax BG]
  [Breadcrumb: Startseite › Ratgeber › Aluminiumzaun kaufen 2026]
  [KATEGORIE-TAG BG #E21212]
  H1: Aluminiumzaun kaufen 2026: Der komplette Guide
  Montserrat 800 | #FFFFFF | clamp(2rem,1.7rem+2vw,3.5rem)
  [Autor: ALUBRAM Redaktion | Datum | Lesezeit: 8 Min.]

┌──────────────────────────────────────────────────────────────────────┐
│  LAYOUT: 75% Artikel + 25% Sidebar (sticky)                        │
│                                                                      │
│  ARTIKEL-INHALT:                                                    │
│  ┌────────────────────────────────────────────────────────────┐    │
│  │  INHALTSVERZEICHNIS (Box BG: #F8F6F1 | R: 8px | border-l  │    │
│  │  3px solid #E21212)                                        │    │
│  │  1. Was ist ein Aluminiumzaun?                             │    │
│  │  2. Vorteile gegenüber anderen Materialien                 │    │
│  │  3. Modelle & Ausführungen                                 │    │
│  │  4. Preise & Kosten                                        │    │
│  │  5. Montage: Selbst oder Profi?                            │    │
│  │  6. Fazit & Empfehlung                                     │    │
│  └────────────────────────────────────────────────────────────┘    │
│                                                                      │
│  H2 Sektionen: Montserrat 700 | 26px | #1A2840                     │
│  H3 Sektionen: Montserrat 600 | 21px | #1A2840                     │
│  Body-Text:    Inter 400 | 17px | #2D2D2D | line-height: 1.8       │
│  Links:        color #E21212 | hover border-bottom #E21212         │
│                                                                      │
│  INLINE CTA-BOX (nach 2. Absatz):                                  │
│  ┌────────────────────────────────────────────────────────────┐    │
│  │ BG: rgba(226,18,18,0.07) | border-left: 4px solid #E21212 │    │
│  │ 💡 Tipp: Lassen Sie sich kostenlos von unseren Experten   │    │
│  │ beraten. [Jetzt Beratung anfragen →] BG: #E21212           │    │
│  └────────────────────────────────────────────────────────────┘    │
│                                                                      │
│  BILDER: float right auf Desktop | 100% Mobile | .avif | lazy      │
│  Bildunterschrift: Inter 400 | 13px | #9E9E9E | text-center        │
│                                                                      │
│  FAZIT-BOX (am Ende):                                              │
│  ┌────────────────────────────────────────────────────────────┐    │
│  │ BG: #F8F6F1 | border-left: 4px solid #E21212 | R: 8px     │    │
│  │ H3: Fazit                                                  │    │
│  │ Zusammenfassung 3–5 Bullet Points                          │    │
│  │ [Zum Kontaktformular →] BG: #E21212                        │    │
│  └────────────────────────────────────────────────────────────┘    │
│                                                                      │
│  AUTOREN-BOX:                                                       │
│  ┌────────────────────────────────────────────────────────────┐    │
│  │ [Autor-Avatar 60px R:50%] ALUBRAM Redaktion               │    │
│  │ Experten-Team für Aluminium-Produkte | himberg@alubram.at  │    │
│  └────────────────────────────────────────────────────────────┘    │
│                                                                      │
│  TEILEN:                                                            │
│  [📘 Facebook] [🐦 Twitter/X] [💼 LinkedIn] [🔗 Link kopieren]     │
└──────────────────────────────────────────────────────────────────────┘

[ÄHNLICHE ARTIKEL (3 Karten volle Breite unter Artikel)]
  H2: Das könnte Sie auch interessieren
  3 × Blog-Karte | Swiper auf Mobile

[CTA BANNER BG: #E21212]
[FOOTER]

SIDEBAR:
  [STICKY top: 110px]
  Inhaltsverzeichnis (scroll-spy Highlight)
  Beliebte Artikel (3)
  CTA-Widget BG: #E21212
  Newsletter
```

---

## SEITE 15 — AKTIONEN & ANGEBOTE

```
URL:       /aktionen/
Template:  page-aktionen.php
Schema:    SpecialAnnouncement + BreadcrumbList
Priorität: ⭐⭐⭐
```

```
[INNER HERO 50vh — BG auffällig, rote Akzente]
  H1: Aktuelle Aktionen & Sonderangebote
  Sub: Direkt vom Hersteller — Sparen Sie jetzt!

┌──────────────────────────────────────────────────────────────────────┐
│  AKTIONEN GRID (2–3 Spalten)                                        │
│                                                                      │
│  ┌───────────────────────────────┐  ┌─────────────────────────────┐ │
│  │ [AKTIONS-BADGE: Frühjahr 2026]│  │ [AKTIONS-BADGE: Limitiert]  │ │
│  │ BG: #E21212 | weiß | R: 4px  │  │ BG: #C8A96E | navy | R: 4px │ │
│  │                               │  │                             │ │
│  │ [BILD]                        │  │ [BILD]                      │ │
│  │                               │  │                             │ │
│  │ Frühjahrsaktion: Zaunanlage   │  │ Carport Sonderedition       │ │
│  │ + Tor zum Kombipreis          │  │ Anlieferung Frühjahr 2026   │ │
│  │                               │  │                             │ │
│  │ ~~Preis auf Anfrage~~         │  │ Nur wenige Plätze frei      │ │
│  │ Gültig bis: 30. April 2026    │  │                             │ │
│  │ [Jetzt anfragen →] #E21212    │  │ [Jetzt anfragen →] #E21212  │ │
│  └───────────────────────────────┘  └─────────────────────────────┘ │
│  Karte: BG #FFF | R: 12px | shadow-md | border-top: 3px #E21212   │
└──────────────────────────────────────────────────────────────────────┘

[NEWSLETTER ANMELDUNG (BG: #1A2840)]
  "Keine Aktion verpassen — jetzt Newsletter abonnieren"
  [E-Mail] [Anmelden →] | ☐ Datenschutz

[CTA BANNER BG: #E21212]
[FOOTER]
```

---

## SEITE 16 — KARRIERE

```
URL:       /karriere/
Template:  page.php (Standard)
Schema:    JobPosting (je Stelle) + BreadcrumbList
Priorität: ⭐⭐
```

```
[INNER HERO 45vh]
  H1: Karriere bei ALUBRAM GMBH
  Sub: Werden Sie Teil unseres Teams in Himberg bei Wien

[VORTEILE ARBEITGEBER (4 Karten BG: #F8F6F1)]
  [💰 Faire Bezahlung] [📍 Arbeiten in NÖ] [🤝 Teamgeist] [📈 Wachstum]

[OFFENE STELLEN AKKORDEON (BG: #FFFFFF)]
  ▼ Montagetechniker (m/w/d) — Vollzeit — Himberg
    Aufgaben, Anforderungen, Angebot
    [Jetzt bewerben →] BG: #E21212
  ▶ Verkäufer / Kundenberater (m/w/d)
  ▶ CNC-Operateur / Produktionsmitarbeiter
  ▶ Fahrer / Lagermitarbeiter

[INITIATIVBEWERBUNG FORMULAR]
  Name, E-Mail, Telefon, Position, Lebenslauf Upload (PDF, max. 5MB)
  Motivationsschreiben (Textarea)
  ☐ Datenschutz | [Bewerben →] #E21212

[FOOTER]
```

---

## SEITE 17 — IMPRESSUM / DATENSCHUTZ / AGB

```
URLs:       /impressum/  |  /datenschutzerklaerung/  |  /agb/
Template:   page.php (Standard)
SEO:        <meta name="robots" content="noindex, nofollow">
Schema:     keine (Pflichtseiten, kein SEO-Wert)
Priorität:  ⭐
```

```
[KEIN HERO — nur simpler Page-Header (BG: #1A2840, 200px)]
  H1: Impressum / Datenschutzerklärung / AGB

[CONTENT-BEREICH: max-width: 860px | margin: auto | Padding: 80px 20px]

TYPOGRAFIE:
  H2: Montserrat 600 | 22px | #1A2840 | border-bottom: 2px solid #E21212
  H3: Montserrat 600 | 17px | #1A2840
  Body: Inter 400 | 16px | #2D2D2D | line-height: 1.8
  Links: color: #E21212

IMPRESSUM PFLICHTANGABEN (AT):
  Firmenname: ALUBRAM GMBH
  FN: 535870 w | Handelsgericht Niederösterreich
  UID: ATU75724307
  Adresse: Hintere Ortsstraße 31, 2325 Himberg bei Wien, Österreich
  Tel: +43 (0) 223 584 793 | E-Mail: himberg@alubram.at
  Geschäftsführer: Szpak Irek
  Zuständige Behörde: Bezirkshauptmannschaft Bruck an der Leitha
  Kammerzugehörigkeit: WKO NÖ
  Online-Streitbeilegung: https://ec.europa.eu/consumers/odr

DATENSCHUTZ:
  DSGVO-konforme Vollversion
  Google Analytics: nur nach Einwilligung (Borlabs Cookie)
  Google Fonts: lokal gehostet (kein CDN)
  Google Maps: nur nach Einwilligung
  Contact Form 7: Datenspeicherung
  Auftragsverarbeitung, Betroffenenrechte etc.

[FOOTER]
```

---

## SEITE 18 — LOKALE SEO LANDING PAGES

```
URLs:      /aluminiumzaun-wien/
           /aluminiumzaun-niederoesterreich/
           /carport-wien/
           /terrassenueberdachung-wien/
           (erweiterbar nach Bedarf)
Template:  page.php (Standard — individueller Inhalt)
Schema:    LocalBusiness + Service + BreadcrumbList + FAQPage
Priorität: ⭐⭐⭐⭐ (hoher SEO-Wert für lokale Suchen)
```

```
SEITENSTRUKTUR je Lokale Landing Page:

[INNER HERO 55vh]
  BG: Projektfoto aus der jeweiligen Region
  H1: Aluminiumzaun Wien — Direkthersteller ALUBRAM GMBH
      (mit Stadtname / Regionname im H1!)
  [Breadcrumb: Startseite › Aluminiumzaun Wien]

[LOKALER SEO TEXT — 800–1200 Wörter]
  H2: "Aluminiumzaun kaufen in Wien und Umgebung"
  Lokale Keywords:
  - Wien, Niederösterreich, DACH-Markt
  - "Aluminiumzaun Wien Hersteller"
  - "Zaunanlage Wien kaufen"
  - "Zaunhersteller Niederösterreich"
  Natürliche Einbindung von Ortsnamen (Wien, NÖ, Umgebung)
  Mind. 3 H2-Sektionen mit lokalen Keywords
  Keine Keyword-Stuffing — natürlicher Fließtext!

[PRODUKT-VORSCHAU 4 Karten]
  Beliebteste Produkte für diese Region

[TESTIMONIALS AUS REGION]
  3 Kundenmeinungen mit Ortsangabe Wien / NÖ
  Swiper Slider | Playfair italic | ⭐⭐⭐⭐⭐

[KONTAKTFORMULAR (wie CTA-Banner)]
  H2: "Kostenloses Angebot für Wien & Umgebung anfragen"
  Formular mit Pflichtfeld PLZ für Abdeckungsprüfung

[GOOGLE MAPS EMBED (DSGVO)]
  Zeigt Standort Himberg + Radius Wien/NÖ

[FAQ (5–7 Fragen — FAQPage Schema)]
  Q: Liefern Sie auch nach Wien und NÖ?
  Q: Wie lange dauert die Lieferung nach Wien?
  Q: Ist die Montage in Wien möglich?
  Q: Gibt es Referenzen in Wien?
  Q: Was kostet ein Aluminiumzaun in Wien?

[FOOTER]

VERLINKUNGS-STRATEGIE:
  Verlinkung von Hauptproduktseiten auf Landing Pages
  und zurück → Interne Linkstruktur für SEO
  Schema: "areaServed": "Wien" in LocalBusiness JSON-LD
```


---

## KL — KOMPONENTEN-BIBLIOTHEK

```
Datei:  alubramat-child/assets/css/custom/components.css
        alubramat-child/assets/js/custom/main.js
```

### KL-01 — BUTTONS

```
╔══════════════════════════════════════════════════════════════════════╗
║  BUTTON VARIANTEN                                                   ║
╠══════════════════════════════════════════════════════════════════════╣
║                                                                     ║
║  [PRIMARY — BG: #E21212]         [SECONDARY — outline #E21212]     ║
║  Montserrat 600 | 15px           Montserrat 600 | 15px             ║
║  padding: 14px 28px | R: 4px     padding: 12px 26px | R: 4px       ║
║  shadow: 0 4px 24px red 38%      bg: transparent | color: #E21212  ║
║  hover: BG #B73D3D + Y(-2px)     hover: BG #E21212 | color #FFF    ║
║  ::after shimmer-effect          transition: all 0.25s ease        ║
║                                                                     ║
║  [GHOST GOLD — outline #C8A96E]  [TEXT-LINK — kein BG]             ║
║  Montserrat 600 | 15px           Inter 500 | 15px                  ║
║  border: 2px solid #C8A96E       color: #E21212                    ║
║  color: #C8A96E                  border-bottom: 1px transparent     ║
║  hover: BG rgba(gold,0.1)        hover: border-bottom #E21212      ║
║                                                                     ║
║  [ICON BUTTON — nur Icon]        [LARGE — 54px Höhe]               ║
║  36px | R: 50% | BG: #E21212     padding: 16px 36px | Montserr. 600║
║  MDI Icon 20px | weiß            Full-width: width: 100%           ║
╚══════════════════════════════════════════════════════════════════════╝

CSS SHIMMER-EFFEKT (Primary Button):
  .btn-primary {
    position: relative;
    overflow: hidden;
  }
  .btn-primary::after {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(120deg,
      transparent 20%,
      rgba(255,255,255,0.18) 50%,
      transparent 80%);
    transform: translateX(-100%);
    transition: transform 0.6s ease;
  }
  .btn-primary:hover::after {
    transform: translateX(100%);
  }
```

---

### KL-02 — PRODUKT-KARTE

```
╔══════════════════════════════════════════════════════════════════════╗
║                                                                     ║
║  ┌─────────────────────────────────────┐                           ║
║  │  [BILD 100% Breite]                 │ ← overflow: hidden        ║
║  │  aspect-ratio: 4/3                  │   img: scale(1) →         ║
║  │                                     │         scale(1.05) hover ║
║  │  [OVERLAY rgba(0,0,0,0) →           │   transition: 0.6s cubic  ║
║  │            rgba(17,27,45,0.55) h.]  │                           ║
║  │                                     │                           ║
║  │  [Kategorie-Tag oben links]         │                           ║
║  │  BG: #E21212 | weiß | 11px | R:4px │                           ║
║  │  Montserrat 600 | padding: 4px 10px │                           ║
║  │                                     │                           ║
║  │  [Produktname abs. unten-links]     │                           ║
║  │  Montserrat 700 | 18px | #FFFFFF    │                           ║
║  │  (visible only on hover)            │                           ║
║  └─────────────────────────────────────┘                           ║
║  BG: #FFFFFF | border-radius: 12px | shadow-sm                     ║
║  hover: shadow-md + translateY(-6px)                               ║
║  transition: var(--transition-base)                                 ║
║                                                                     ║
║  Unterhalb des Bildes:                                              ║
║  ┌─────────────────────────────────────┐                           ║
║  │  Produktname H3 | Montserrat 700    │                           ║
║  │  Kurzbeschreibung | Inter 400 14px  │                           ║
║  │  [Mehr Details →] Gold Text-Link    │                           ║
║  └─────────────────────────────────────┘                           ║
║  padding: 20px                                                      ║
╚══════════════════════════════════════════════════════════════════════╝
```

---

### KL-03 — USP ICON CARD

```
╔══════════════════════════════════════════════════════════════════════╗
║  ┌────────────────────────────────────┐                            ║
║  │  [MDI Icon 40px — color: #E21212]  │                            ║
║  │  H3: Direkthersteller              │                            ║
║  │  Montserrat 700 | 19px | #1A2840   │                            ║
║  │  Text: Inter 400 | 14px | #9E9E9E  │                            ║
║  └────────────────────────────────────┘                            ║
║  BG: #F8F6F1 | R: 12px | padding: 32px                            ║
║  hover: shadow-gold + border-bottom: 3px solid #E21212             ║
║  transition: var(--transition-base)                                 ║
╚══════════════════════════════════════════════════════════════════════╝
```

---

### KL-04 — TESTIMONIAL KARTE

```
╔══════════════════════════════════════════════════════════════════════╗
║  BG: rgba(255,255,255,0.06) auf dunklen BGs                        ║
║  border: 1px solid rgba(200,169,110,0.20) | R: 16px | padding: 40px║
║                                                                     ║
║  ❝ (Playfair Display | 100px | rgba(200,169,110,0.10) | abs. top) ║
║                                                                     ║
║  "Zitat in Playfair Display italic | 17px | rgba(fff,0.92)"        ║
║                                                                     ║
║  ⭐⭐⭐⭐⭐  (color: #C8A96E | 18px)                                   ║
║                                                                     ║
║  — Kundenname, Ort            Montserrat 600 | 15px | #FFFFFF       ║
║  Gekauft: Produktname         Inter 400 | 13px | #C8A96E            ║
╚══════════════════════════════════════════════════════════════════════╝
```

---

### KL-05 — GOLD SECTION LABEL

```
[Goldene Overline über H2-Titeln]

  display: flex | align-items: center | gap: 12px
  margin-bottom: 12px

  ─────── (40px Linie | BG: #C8A96E | Höhe: 2px)
  UNSERE PRODUKTE (text | Montserrat 600 | 11px | #C8A96E | letter-spacing: 0.15em | UPPERCASE)

HTML:
  <span class="section-label">
    <span class="section-label__line"></span>
    <span class="section-label__text">UNSERE PRODUKTE</span>
  </span>
```

---

### KL-06 — FAQ AKKORDEON

```
╔══════════════════════════════════════════════════════════════════════╗
║  ┌──────────────────────────────────────────────────────────────┐  ║
║  │ Q: Wie lange hält ein Aluminiumzaun?             [▾ / ▲]    │  ║
║  │    Montserrat 600 | 16px | #1A2840   MDI expand_more rot 20px│  ║
║  ├──────────────────────────────────────────────────────────────┤  ║
║  │ A: Ein hochwertiger Aluminiumzaun... [offen]                 │  ║
║  │    border-left: 3px solid #E21212                           │  ║
║  │    Inter 400 | 15px | #2D2D2D | padding: 20px               │  ║
║  │    BG: rgba(226,18,18,0.03)                                  │  ║
║  └──────────────────────────────────────────────────────────────┘  ║
║  ┌────────────────────────── [geschlossen] ──────────────────── ┐  ║
║  │ Q: Was kostet ein Aluminiumzaun pro Meter?        [▾]        │  ║
║  └──────────────────────────────────────────────────────────────┘  ║
╚══════════════════════════════════════════════════════════════════════╝

JS-Implementierung (Vanilla, kein jQuery):
  max-height: 0 → max-height: 600px | overflow: hidden
  transition: max-height 0.35s ease | transform arrow: 0°→180°
  Schema: @type FAQPage + Question + acceptedAnswer
```

---

### KL-07 — FORM-FELDER

```
INPUT / TEXTAREA:
  border: 1px solid #E8E8E8
  border-radius: 4px
  padding: 14px 16px
  font: Inter 400 | 15px | #2D2D2D
  placeholder: #9E9E9E
  focus: border-color #E21212 | outline: 2px solid rgba(226,18,18,0.15)
  error: border-color #D32F2F | shake animation
  success: border-color #2D7D46
  transition: border-color 0.2s ease

SELECT:
  appearance: none
  background: url("chevron-down.svg") no-repeat right 14px center
  padding-right: 40px
  (gleiche Basis-Styles wie Input)

CHECKBOX:
  accent-color: #E21212
  width: 18px | height: 18px
  cursor: pointer

LABEL:
  Inter 500 | 13px | #2D2D2D | letter-spacing: 0.02em
  display: block | margin-bottom: 6px

PFLICHTFELD-STERN:
  color: #E21212 | margin-left: 2px

ERFOLG-NACHRICHT (AJAX):
  BG: rgba(45,125,70,0.08) | border: 1px solid #2D7D46
  border-left: 4px solid #2D7D46 | R: 4px | padding: 16px
  MDI check_circle 20px #2D7D46 | Inter 400 | 14px
  "Vielen Dank! Wir melden uns innerhalb von 24 Stunden."

FEHLER-NACHRICHT:
  BG: rgba(211,47,47,0.06) | border-left: 4px solid #D32F2F
```

---

### KL-08 — BREADCRUMBS

```
Startseite  ›  Produkte  ›  Zäune  ›  BOLERO 40

HTML:
  <nav aria-label="Breadcrumb" class="breadcrumbs">
    <ol itemscope itemtype="https://schema.org/BreadcrumbList">
      <li itemprop="itemListElement" itemscope itemtype="https://schema.org/ListItem">
        <a href="/" itemprop="item"><span itemprop="name">Startseite</span></a>
        <meta itemprop="position" content="1" />
      </li>
      ...
    </ol>
  </nav>

Stile:
  Separator: › | color: #C8A96E | margin: 0 8px
  Links: Inter 400 | 13px | rgba(fff,0.65) auf dunklen Heroes
  Aktuell: #FFFFFF / #2D2D2D | kein Link
  Hover: color: #FFFFFF
```

---

### KL-09 — PAGINATION

```
[◀ Zurück]    [1]    [2]    [3]    [...]    [8]    [Weiter ▶]

  Aktive Seite: BG #E21212 | color #FFFFFF | R: 4px
  Inaktive: BG transparent | color #2D2D2D | border: 1px solid #E8E8E8
  Hover: BG #F8F6F1 | border-color #E21212
  Buttons: Montserrat 500 | 14px | width: 40px | height: 40px
  Pfeil-Buttons: MDI arrow_back / arrow_forward | 20px
```

---

### KL-10 — STATS/COUNTER ANIMATION

```
JS-Implementierung (main.js):

  // IntersectionObserver startet Counter wenn sichtbar
  const counterObserver = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting && !entry.target.dataset.counted) {
        animateCounter(entry.target);
        entry.target.dataset.counted = 'true';
      }
    });
  }, { threshold: 0.5 });

  function animateCounter(el) {
    const target = parseInt(el.dataset.target, 10);
    const duration = 2000; // ms
    const start = performance.now();
    const easeOutCubic = t => 1 - Math.pow(1 - t, 3);

    function update(now) {
      const elapsed = now - start;
      const progress = Math.min(elapsed / duration, 1);
      const current = Math.round(easeOutCubic(progress) * target);
      el.textContent = current.toLocaleString('de-AT'); // "1.000"
      if (progress < 1) requestAnimationFrame(update);
    }
    requestAnimationFrame(update);
  }

  // Suffix (+ oder Einheit) separat via data-suffix="+"
  // Beispiel: <span class="counter" data-target="1000" data-suffix="+">0</span>
```


---

## AN — ANIMATIONEN & PERFORMANCE-CHECKLISTE

### AOS INITIALISIERUNG

```javascript
// alubramat-child/assets/js/custom/main.js

document.addEventListener('DOMContentLoaded', function () {

  // ─── AOS Init ────────────────────────────────────────────────────
  AOS.init({
    duration:        800,
    easing:          'ease-in-out-cubic',
    once:            true,
    offset:          80,
    delay:           0,
    anchorPlacement: 'top-bottom'
  });

  // ─── Header Scroll Transparent → Solid ───────────────────────────
  const header = document.getElementById('site-header');
  const SCROLL_THRESHOLD = 80;

  function handleHeaderScroll() {
    if (window.scrollY > SCROLL_THRESHOLD) {
      header.classList.add('scrolled');
    } else {
      header.classList.remove('scrolled');
    }
  }

  window.addEventListener('scroll', handleHeaderScroll, { passive: true });
  handleHeaderScroll();

  // ─── Mobile Menu Hamburger ────────────────────────────────────────
  const hamburger = document.getElementById('hamburger-btn');
  const mobileMenu = document.getElementById('mobile-menu');
  const menuClose  = document.getElementById('menu-close-btn');

  if (hamburger && mobileMenu) {
    hamburger.addEventListener('click', () => {
      mobileMenu.classList.add('open');
      document.body.style.overflow = 'hidden';
      hamburger.setAttribute('aria-expanded', 'true');
    });

    menuClose.addEventListener('click', () => {
      mobileMenu.classList.remove('open');
      document.body.style.overflow = '';
      hamburger.setAttribute('aria-expanded', 'false');
    });

    // Swipe right to close
    let startX = 0;
    mobileMenu.addEventListener('touchstart', e => {
      startX = e.touches[0].clientX;
    }, { passive: true });
    mobileMenu.addEventListener('touchend', e => {
      if (e.changedTouches[0].clientX - startX > 60) {
        mobileMenu.classList.remove('open');
        document.body.style.overflow = '';
      }
    }, { passive: true });

    // Focus Trap
    const focusable = mobileMenu.querySelectorAll(
      'a, button, input, [tabindex]:not([tabindex="-1"])'
    );
    const firstEl = focusable[0];
    const lastEl  = focusable[focusable.length - 1];
    mobileMenu.addEventListener('keydown', e => {
      if (e.key !== 'Tab') return;
      if (e.shiftKey && document.activeElement === firstEl) {
        e.preventDefault(); lastEl.focus();
      } else if (!e.shiftKey && document.activeElement === lastEl) {
        e.preventDefault(); firstEl.focus();
      }
    });
  }

  // ─── Parallax ────────────────────────────────────────────────────
  const parallaxEls = document.querySelectorAll('[data-parallax]');

  if (parallaxEls.length > 0 && window.matchMedia('(min-width: 768px)').matches) {
    window.addEventListener('scroll', () => {
      const scrollY = window.pageYOffset;
      parallaxEls.forEach(el => {
        const speed = parseFloat(el.dataset.parallaxSpeed || '0.4');
        el.style.transform = `translateY(${scrollY * speed}px)`;
      });
    }, { passive: true });
  }

  // ─── Mega Menu (Desktop) ─────────────────────────────────────────
  const megaMenuTrigger = document.querySelector('.has-mega-menu');
  const megaMenu = document.querySelector('.mega-menu');

  if (megaMenuTrigger && megaMenu) {
    let closeTimer;
    megaMenuTrigger.addEventListener('mouseenter', () => {
      clearTimeout(closeTimer);
      megaMenu.style.display = 'block';
      setTimeout(() => megaMenu.classList.add('open'), 10);
    });
    megaMenuTrigger.addEventListener('mouseleave', () => {
      closeTimer = setTimeout(() => {
        megaMenu.classList.remove('open');
        setTimeout(() => { megaMenu.style.display = 'none'; }, 300);
      }, 150);
    });
    megaMenu.addEventListener('mouseenter', () => clearTimeout(closeTimer));
    megaMenu.addEventListener('mouseleave', () => {
      megaMenu.classList.remove('open');
      setTimeout(() => { megaMenu.style.display = 'none'; }, 300);
    });
  }

  // ─── FAQ Akkordeon ───────────────────────────────────────────────
  document.querySelectorAll('.faq-item').forEach(item => {
    const btn = item.querySelector('.faq-question');
    const ans = item.querySelector('.faq-answer');
    const ico = item.querySelector('.faq-icon');

    btn.addEventListener('click', () => {
      const isOpen = item.classList.contains('active');
      // Schließe alle anderen
      document.querySelectorAll('.faq-item.active').forEach(other => {
        other.classList.remove('active');
        other.querySelector('.faq-answer').style.maxHeight = '0';
        other.querySelector('.faq-icon').style.transform   = 'rotate(0deg)';
      });
      if (!isOpen) {
        item.classList.add('active');
        ans.style.maxHeight = ans.scrollHeight + 'px';
        ico.style.transform = 'rotate(180deg)';
      }
    });
  });

  // ─── AJAX Kontaktformular ────────────────────────────────────────
  const contactForms = document.querySelectorAll('.alubram-contact-form');
  contactForms.forEach(form => {
    form.addEventListener('submit', async function (e) {
      e.preventDefault();
      const btn = form.querySelector('[type="submit"]');
      const orig = btn.textContent;
      btn.disabled = true;
      btn.textContent = 'Wird gesendet…';

      const formData = new FormData(form);
      formData.append('action', 'alubram_contact_form');

      try {
        const res  = await fetch(alubram_ajax.ajax_url, {
          method: 'POST', body: formData
        });
        const data = await res.json();
        if (data.success) {
          form.innerHTML = `
            <div class="form-success" role="alert">
              <span class="material-symbols-outlined">check_circle</span>
              Vielen Dank! Wir melden uns innerhalb von 24 Stunden bei Ihnen.
            </div>`;
        } else {
          showFormError(form, data.data?.message || 'Fehler beim Senden.');
          btn.disabled = false; btn.textContent = orig;
        }
      } catch {
        showFormError(form, 'Netzwerkfehler. Bitte versuchen Sie es erneut.');
        btn.disabled = false; btn.textContent = orig;
      }
    });
  });

});

function showFormError(form, msg) {
  const box = form.querySelector('.form-error') || document.createElement('div');
  box.className = 'form-error';
  box.setAttribute('role', 'alert');
  box.textContent = msg;
  form.prepend(box);
}
```

---

### CSS CUSTOM ANIMATIONS

```css
/* ── Floating Element (Scroll-Indikator, Badges) ──────────────── */
@keyframes alubram-float {
  0%, 100% { transform: translateY(0);     }
  50%       { transform: translateY(-10px); }
}
.alubram-float {
  animation: alubram-float 3s ease-in-out infinite;
}

/* ── Gold Pulsierender Glow (CTA-Badges, Wichtiges) ───────────── */
@keyframes alubram-pulse-red {
  0%, 100% { box-shadow: 0 0 0  0px rgba(226,18,18,0.4); }
  50%       { box-shadow: 0 0 0 16px rgba(226,18,18,0.0); }
}
.alubram-pulse-red {
  animation: alubram-pulse-red 2.5s ease-in-out infinite;
}

/* ── Shimmer (Skeleton Loading) ───────────────────────────────── */
@keyframes alubram-shimmer {
  0%   { background-position: -1000px 0; }
  100% { background-position:  1000px 0; }
}
.skeleton {
  background: linear-gradient(90deg, #E8E8E8 25%, #F5F5F5 50%, #E8E8E8 75%);
  background-size: 2000px 100%;
  animation: alubram-shimmer 1.8s linear infinite;
}

/* ── Counter Einblenden ───────────────────────────────────────── */
@keyframes alubram-count-up {
  from { opacity: 0; transform: translateY(20px); }
  to   { opacity: 1; transform: translateY(0);    }
}
.counter-visible {
  animation: alubram-count-up 0.6s ease forwards;
}

/* ── Header Transition ────────────────────────────────────────── */
#site-header {
  transition: background 0.35s ease,
              box-shadow  0.35s ease;
}
#site-header.scrolled {
  background: #FFFFFF !important;
  box-shadow: 0 2px 20px rgba(0,0,0,0.10);
}
#site-header.scrolled .nav-link         { color: #1A2840; }
#site-header.scrolled .site-logo-white  { display: none;  }
#site-header.scrolled .site-logo-dark   { display: block; }

/* ── Mobile Menu Slide-in ─────────────────────────────────────── */
#mobile-menu {
  transform: translateX(100%);
  transition: transform 0.35s cubic-bezier(0.4, 0, 0.2, 1);
}
#mobile-menu.open {
  transform: translateX(0);
}

/* ── Mega Menu Fade-Drop ──────────────────────────────────────── */
.mega-menu {
  opacity: 0;
  transform: translateY(-10px);
  transition: opacity 0.25s ease, transform 0.25s ease;
  pointer-events: none;
}
.mega-menu.open {
  opacity: 1;
  transform: translateY(0);
  pointer-events: auto;
}

/* ── Karte Hover ──────────────────────────────────────────────── */
.alubram-card {
  transition: transform 0.35s ease, box-shadow 0.35s ease;
}
.alubram-card:hover {
  transform: translateY(-6px);
  box-shadow: 0 20px 60px rgba(0,0,0,0.18);
}

/* ── Bild Zoom ────────────────────────────────────────────────── */
.alubram-card .card-img {
  overflow: hidden;
}
.alubram-card .card-img img {
  transition: transform 0.6s cubic-bezier(0.4, 0, 0.2, 1);
}
.alubram-card:hover .card-img img {
  transform: scale(1.05);
}

/* ── FAQ Akkordeon ────────────────────────────────────────────── */
.faq-answer {
  max-height: 0;
  overflow: hidden;
  transition: max-height 0.35s ease;
}
.faq-item.active .faq-answer {
  /* max-height wird per JS gesetzt */
}
.faq-icon {
  transition: transform 0.3s ease;
}
```

---

### AOS ATTRIBUTE — VERWENDUNGSGUIDE

```
SEKTIONEN:      data-aos="fade-up"        data-aos-delay="0"
                data-aos-duration="800"   data-aos-easing="ease-in-out-cubic"

KARTEN (Grid):  data-aos="zoom-in-up"     data-aos-delay="[Karte × 100]ms"
                (max. 4 × 100ms = 400ms)

TEXTE (links):  data-aos="fade-right"     data-aos-delay="0"
BILDER (recht): data-aos="fade-left"      data-aos-delay="150"

HERO BADGE:     data-aos="fade-down"      data-aos-delay="0"
HERO H1:        data-aos="fade-up"        data-aos-delay="100"
HERO SUBLINE:   data-aos="fade-up"        data-aos-delay="250"
HERO BUTTONS:   data-aos="fade-up"        data-aos-delay="400"
HERO BADGES:    data-aos="fade-up"        data-aos-delay="550"

COUNTER:        KEIN AOS — IntersectionObserver übernimmt

CTA BANNER:     data-aos="fade-up"        data-aos-duration="1200"
```

---

## ✅ PERFORMANCE & SEO CHECKLISTE

```
╔══════════════════════════════════════════════════════════════════════╗
║  CORE WEB VITALS — ZIELE                                           ║
╠══════════════════════════════════════════════════════════════════════╣
║  LCP  (Largest Contentful Paint):  < 2.5s   ← Ziel: < 1.5s       ║
║  FID / INP (Interactivity):        < 100ms  ← Ziel: < 50ms        ║
║  CLS  (Cumulative Layout Shift):   < 0.1    ← Ziel: < 0.05        ║
║  TTFB (Time to First Byte):        < 200ms                        ║
╠══════════════════════════════════════════════════════════════════════╣
║  LIGHTHOUSE SCORES — MINDESTZIELE                                  ║
║  Performance Desktop:  ≥ 95/100                                    ║
║  Performance Mobile:   ≥ 90/100                                    ║
║  Accessibility:        ≥ 90/100                                    ║
║  Best Practices:       ≥ 95/100                                    ║
║  SEO:                  100/100                                     ║
╚══════════════════════════════════════════════════════════════════════╝

IMAGES:
  ☐ Alle Bilder als .avif mit .webp und .jpg Fallback (<picture>)
  ☐ srcset + sizes für alle Bilder
  ☐ loading="lazy" decoding="async" auf alle Bilder below-fold
  ☐ fetchpriority="high" + loading="eager" nur auf Hero-LCP-Bild
  ☐ Explizite width + height Attribute (CLS vermeiden)
  ☐ Imagify / ShortPixel für automatische Kompression aktiviert
  ☐ Max. Dateigröße Hero: 180kB (.avif), sonstige: 80kB

FONTS:
  ☐ Google Fonts lokal gehostet (DSGVO Österreich — kein CDN)
  ☐ font-display: swap auf alle @font-face Definitionen
  ☐ Nur benötigte Weights laden (Montserrat: 600,700,800,900)
  ☐ <link rel="preload"> für Hauptschrift above-fold

HTML / CSS / JS:
  ☐ Critical CSS inline im <head> (above-fold Styles)
  ☐ Alle JS-Dateien mit defer oder async laden
  ☐ CSS/JS minifiziert (WP Rocket oder Autoptimize)
  ☐ Kein jQuery falls vermeidbar (Vanilla JS bevorzugt)
  ☐ HTTP/2 aktiviert am Webserver

WORDPRESS:
  ☐ WP Rocket: Page Caching + Browser Caching aktiviert
  ☐ WP Rocket: Gzip/Brotli Kompression
  ☐ WP Rocket: DNS Prefetch + Preconnect
  ☐ Yoast SEO: XML Sitemap aktiv (Pings an Google/Bing)
  ☐ Yoast SEO: Robots.txt korrekt konfiguriert
  ☐ Google Search Console: Property verifiziert
  ☐ Google Analytics 4: DSGVO-konform via Borlabs Cookie
  ☐ WP-Cron deaktiviert (echte Server-Cron stattdessen)

SEO ON-PAGE:
  ☐ Jede Seite: einzigartiger <title> (max. 60 Zeichen)
  ☐ Jede Seite: einzigartige Meta-Description (150–160 Zeichen)
  ☐ Jede Seite: genau 1× H1
  ☐ H2 enthalten primäres Keyword der Seite
  ☐ ALT-Attribute: alle Bilder, beschreibend, auf Deutsch, mit Keyword
  ☐ Canonical-Tag auf jeder Seite
  ☐ Hreflang: de-AT (oder de-DE falls nötig)
  ☐ Open Graph: og:title, og:description, og:image (1200×630px)
  ☐ Twitter Card: summary_large_image
  ☐ Schema.org JSON-LD: LocalBusiness auf Homepage
  ☐ Schema.org JSON-LD: Product auf Produktseiten
  ☐ Schema.org JSON-LD: FAQPage auf Seiten mit FAQ
  ☐ Schema.org JSON-LD: BreadcrumbList auf allen Unterseiten
  ☐ Interne Verlinkung: Hauptproduktseiten → Lokale Landing Pages
  ☐ Outbound Links: rel="noopener noreferrer" + target="_blank"
  ☐ Broken Links: 0 (regelmäßig prüfen mit Broken Link Checker)

DSGVO / AUSTRIA:
  ☐ Borlabs Cookie Banner aktiv und korrekt konfiguriert
  ☐ Google Analytics: opt-in only (nicht opt-out)
  ☐ Google Maps: nur nach Zustimmung laden
  ☐ Google Fonts: lokal gehostet (kein externer Request)
  ☐ Contact Form 7: Datenschutz-Checkbox Pflichtfeld
  ☐ Impressum: vollständige Pflichtangaben nach österr. Recht
  ☐ Datenschutzerklärung: DSGVO-konform, aktuell
  ☐ SSL-Zertifikat: A+ Rating (HSTS aktiviert)
  ☐ WordPress-Admin: 2FA aktiviert
  ☐ wp-config.php: Sicherheitskeys aktuell

ACCESSIBILITY (WCAG 2.1 AA):
  ☐ Alle interaktiven Elemente: focus-visible Styles
  ☐ Farbkontrast-Check: alle Farbkombinationen ≥ 4.5:1 (AA)
  ☐ ARIA-Labels auf Icons ohne sichtbaren Text
  ☐ Skip-Link: "Zum Hauptinhalt springen" (versteckt, bei Focus sichtbar)
  ☐ Tastaturnavigation: alle Funktionen erreichbar
  ☐ Mobile Menu: Focus-Trap aktiv, ESC zum Schließen
  ☐ Bilder: alt="" für dekorative Bilder, beschreibend für informative
  ☐ Formulare: Labels mit for/id korrekt verknüpft
  ☐ Fehlermeldungen: role="alert" für Screen Reader

SICHERHEIT:
  ☐ if (!defined('ABSPATH')) { exit; } in jedem PHP-Template
  ☐ Alle Outputs: esc_html(), esc_url(), esc_attr(), wp_kses_post()
  ☐ Alle Inputs: sanitize_text_field(), sanitize_email()
  ☐ Formulare: wp_nonce_field() + wp_verify_nonce()
  ☐ Honeypot Felder in allen Formularen
  ☐ file_editor deaktiviert in wp-config.php
  ☐ Wordfence oder Sucuri: aktiv und konfiguriert
  ☐ Datenbankpräfix: nicht wp_ (geändert bei Installation)
  ☐ XML-RPC: deaktiviert
  ☐ User-Enumeration: blockiert (?author=1 → 404)
```

---

## TEMPLATE-DATEI ZUORDNUNG

```
╔══════════════════════════════════════════════════════════════════════════╗
║  SEITE                    │ URL                        │ PHP-TEMPLATE   ║
╠══════════════════════════════════════════════════════════════════════════╣
║  Homepage                 │ /                          │ front-page.php ║
║  Über uns                 │ /uber-uns/                 │ page-templates/page-uber-uns.php ║
║  Produkte Übersicht       │ /produkte/                 │ page-templates/page-produkte.php ║
║  Zäune & Zaunfelder       │ /produkte/zaune/           │ page-templates/page-zaune.php ║
║  Tore & Einfahrtstore     │ /produkte/tore/            │ page-templates/page-tore.php ║
║  Carports                 │ /produkte/carports/        │ page-templates/page-carports.php ║
║  Überdachungen            │ /produkte/ueberdachungen/  │ page-templates/page-ueberdachungen.php ║
║  Single Produkt           │ /produkte/{kat}/{slug}/    │ single-alubram_product.php ║
║  Referenzen               │ /referenzen/               │ page-templates/page-referenzen.php ║
║  Leistungen               │ /leistungen/               │ page-templates/page-leistungen.php ║
║  Kontakt                  │ /kontakt/                  │ page-templates/page-kontakt.php ║
║  Standorte                │ /kontakt/standorte/        │ page-templates/page-standorte.php ║
║  Ratgeber (Archiv)        │ /ratgeber/                 │ archive.php ║
║  Single Artikel           │ /ratgeber/{slug}/          │ single.php ║
║  Aktionen                 │ /aktionen/                 │ page-templates/page-aktionen.php ║
║  Karriere                 │ /karriere/                 │ page.php ║
║  Impressum                │ /impressum/                │ page.php ║
║  Datenschutz              │ /datenschutzerklaerung/    │ page.php ║
║  AGB                      │ /agb/                      │ page.php ║
║  LP Aluminiumzaun Wien    │ /aluminiumzaun-wien/       │ page.php ║
║  LP Aluminiumzaun NÖ      │ /aluminiumzaun-niederoe./  │ page.php ║
║  LP Carport Wien          │ /carport-wien/             │ page.php ║
╠══════════════════════════════════════════════════════════════════════════╣
║  404                      │ *                          │ 404.php ║
║  Suche                    │ /?s=                       │ search.php ║
╚══════════════════════════════════════════════════════════════════════════╝
```

---

*PAGE-WIREFRAMES.md | ALUBRAM GMBH | WordPress 6.9 | Theme: alubramat-child*
*Version: 1.0.0 | März 2026 | Erstellt: Claude Sonnet 4.6 / Anthropic*
*GitHub: https://github.com/piotroq/alubram-gmbh-wordpress*

