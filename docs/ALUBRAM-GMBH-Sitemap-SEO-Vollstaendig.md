# ALUBRAM GMBH — Neue Website: Menüstruktur, Unterseiten & SEO-Spezifikationen
**Dokument-Version:** 1.0  
**Erstellt am:** März 2026  
**Projekt:** ALUBRAM GMBH — Premium WordPress Website (DE/AT)  
**Sprache der Inhalte:** Deutsch (de_AT / de_DE)  
**Zielmarkt:** DACH-Region (Österreich, Deutschland, Schweiz)  

---

> **Für den Kunden — Herr Szpak Irek, ALUBRAM GMBH, Himberg bei Wien**
>
> Dieses Dokument enthält den vollständigen Vorschlag für die neue Website-Struktur,
> einschließlich Menünavigation, aller Unterseiten sowie aller SEO-relevanten Metadaten
> (Meta-Tags, Open Graph, Schema.org JSON-LD) für jede einzelne Seite.

---

## INHALTSVERZEICHNIS

1. [Analyse der aktuellen Website](#1-analyse-der-aktuellen-website)
2. [Neue Menüstruktur — Übersicht](#2-neue-menüstruktur--übersicht)
3. [Navigationsmenüs im Detail](#3-navigationsmenüs-im-detail)
4. [Vollständige Seitenübersicht mit SEO-Spezifikationen](#4-vollständige-seitenübersicht-mit-seo-spezifikationen)
   - 4.1 Startseite (Homepage)
   - 4.2 Über uns
   - 4.3 Produkte — Übersichtsseite
   - 4.4 Zäune & Zaunfelder — Kategorienseite
   - 4.5 Horizontal Zaun
   - 4.6 Vertikal Zaun
   - 4.7 Klassischer Zaun
   - 4.8 Blickdichter Zaun (Sichtschutz)
   - 4.9 Industrie Zaun
   - 4.10 Sondermodell Zaun
   - 4.11 Tore & Einfahrtstore — Kategorienseite
   - 4.12 Schiebetor Aluminium
   - 4.13 Flügeltor & Einfahrtstor
   - 4.14 Eingangstor / Gehtor (Gartentor)
   - 4.15 Carports — Kategorienseite
   - 4.16 Überdachungen — Kategorienseite
   - 4.17 Pergola
   - 4.18 Vordach
   - 4.19 Terrassenüberdachung Premium
   - 4.20 Terrassenüberdachung Standard
   - 4.21 Balkone & Geländer
   - 4.22 Zubehör & Sonstiges
   - 4.23 Leistungen
   - 4.24 Referenzen & Bildergalerie
   - 4.25 Aktionen & Angebote
   - 4.26 Ratgeber (Blog)
   - 4.27 Blog-Einzelartikel (Template)
   - 4.28 Kontakt
   - 4.29 Standorte
   - 4.30 Karriere / Wir suchen
   - 4.31 Katalog & Downloads
   - 4.32 Impressum
   - 4.33 Datenschutzerklärung
   - 4.34 AGB
   - 4.35 Lokale Landingpages (Wien / NÖ / Graz)
5. [Zusammenfassung der SEO-Strategie](#5-zusammenfassung-der-seo-strategie)

---

## 1. ANALYSE DER AKTUELLEN WEBSITE

**URL:** https://alubram.at/  
**Aktuelle Plattform:** WordPress 6.7.2 (Upgrade auf 6.9 empfohlen)

### Kritische Probleme der aktuellen Navigation

| Problem | Beschreibung | Empfehlung |
|---|---|---|
| Doppelter Menüpunkt | „INDUSTRIE ZAUN" erscheint sowohl unter Produkte als auch separat im Hauptmenü | Zusammenführen unter Produkte → Zäune |
| Fehlende Produktkategorie | „Tore" sind im Menü nicht als eigene Kategorie sichtbar | Eigene Kategorie „Tore & Einfahrtstore" hinzufügen |
| Falsche Priorität | „Wir suchen" (Stellenangebote) im Hauptmenü lenkt von Conversions ab | In Footer verschieben |
| Kein CTA im Header | Kein „Jetzt Angebot anfordern"-Button | Primären CTA-Button hinzufügen |
| Kein Blog/Content | Kein Content-Marketing, kein Ratgeber | Blog/Ratgeber-Sektion aufbauen |
| Technische SEO-Fehler | Kein H1, keine Meta Descriptions, kein Schema.org, schlechte Alt-Tags | Komplette SEO-Überarbeitung |

---

## 2. NEUE MENÜSTRUKTUR — ÜBERSICHT

```
ALUBRAM GMBH — Neue Sitemap
│
├── 🏠 Startseite                           /
├── 👥 Über uns                             /uber-uns/
├── 📦 Produkte [MEGA MENU]                 /produkte/
│   ├── ⬛ ZÄUNE & ZAUNFELDER
│   │   ├── Zäune — Übersicht               /produkte/zaune/
│   │   ├── Horizontal Zaun                 /produkte/zaune/horizontal-zaun/
│   │   ├── Vertikal Zaun                   /produkte/zaune/vertikal-zaun/
│   │   ├── Klassischer Zaun                /produkte/zaune/klassischer-zaun/
│   │   ├── Blickdichter Zaun               /produkte/zaune/blickdichter-zaun/
│   │   ├── Industrie Zaun                  /produkte/zaune/industrie-zaun/
│   │   └── Sondermodell                    /produkte/zaune/sondermodell/
│   │
│   ├── 🚪 TORE & EINFAHRTSTORE
│   │   ├── Tore — Übersicht                /produkte/tore/
│   │   ├── Schiebetor                      /produkte/tore/schiebetor/
│   │   ├── Flügeltor & Einfahrtstor        /produkte/tore/fluegeltor/
│   │   └── Eingangstor / Gehtor            /produkte/tore/eingangstor/
│   │
│   ├── 🏠 CARPORTS
│   │   └── Carport Aluminium               /produkte/carports/
│   │
│   ├── ☂️ ÜBERDACHUNGEN
│   │   ├── Überdachungen — Übersicht       /produkte/ueberdachungen/
│   │   ├── Pergola                         /produkte/ueberdachungen/pergola/
│   │   ├── Vordach                         /produkte/ueberdachungen/vordach/
│   │   ├── Terrassenüberdachung Premium    /produkte/ueberdachungen/terrassenueberdachung-premium/
│   │   └── Terrassenüberdachung Standard   /produkte/ueberdachungen/terrassenueberdachung-standard/
│   │
│   ├── 🏗️ BALKONE & GELÄNDER
│   │   └── Balkone & Geländer              /produkte/balkone-gelaender/
│   │
│   └── 🔧 ZUBEHÖR & SONSTIGES
│       └── Zubehör & Sonstiges             /produkte/zubehoer/
│
├── ✅ Leistungen                           /leistungen/
├── 📷 Referenzen & Galerie                 /referenzen/
├── 🎁 Aktionen & Angebote                  /aktionen/
├── 📖 Ratgeber (Blog)                      /ratgeber/
│   └── Artikel-Template                    /ratgeber/{slug}/
├── 📞 Kontakt                              /kontakt/
│   └── Standorte                           /kontakt/standorte/
│
├── FOOTER-NAVIGATION
│   ├── Impressum                           /impressum/
│   ├── Datenschutzerklärung               /datenschutzerklaerung/
│   ├── AGB                                 /agb/
│   ├── Karriere                            /karriere/
│   └── Katalog & Downloads                 /katalog/
│
└── LOKALE LANDINGPAGES (SEO)
    ├── Aluminiumzaun Wien                  /aluminiumzaun-wien/
    ├── Aluminiumzaun Niederösterreich      /aluminiumzaun-niederoesterreich/
    └── Carport Wien kaufen                 /carport-wien/
```

---

## 3. NAVIGATIONSMENÜS IM DETAIL

### 3.1 Haupt-Navigation (Header — Desktop)

```
[LOGO]  Über uns  Produkte ▾  Leistungen  Referenzen  Aktionen  Ratgeber  Kontakt  [Jetzt Angebot anfordern →]
```

> **Topbar (über dem Header):**
> 📞 +43 (0) 223 584 793  |  ✉ himberg@alubram.at  |  🕐 Mustergarten geöffnet 24h / 7 Tage

---

### 3.2 Mega-Menu „Produkte"

```
┌────────────────────────────────────────────────────────────────────────────────┐
│  ZÄUNE & ZAUNFELDER    TORE & EINFAHRTSTORE   ÜBERDACHUNGEN    MEHR            │
│  ─────────────────     ──────────────────     ──────────────   ────            │
│  → Alle Zäune          → Alle Tore            → Pergola        → Carports      │
│  → Horizontal Zaun     → Schiebetor           → Vordach        → Balkone       │
│  → Vertikal Zaun       → Flügeltor            → Terrasse Prem. → Geländer      │
│  → Klassischer Zaun    → Eingangstor          → Terrasse Std.  → Zubehör       │
│  → Blickdichter Zaun                                                            │
│  → Industrie Zaun                                                               │
│  → Sondermodell                                                                 │
│                                                                                  │
│  [📷 Referenzen ansehen]                        [📞 Kostenlos beraten lassen]  │
└────────────────────────────────────────────────────────────────────────────────┘
```

---

### 3.3 Mobile Navigation (Hamburger Menu)

Komprimiert, Accordion-Prinzip — Tippen auf „Produkte" öffnet alle Unterkategorien.

---

### 3.4 Footer Navigation

```
PRODUKTE              UNTERNEHMEN           SERVICE               RECHTLICHES
──────────────        ───────────           ───────               ───────────
Zäune & Zaunfelder    Über uns              Kontakt               Impressum
Tore & Einfahrtstore  Leistungen            Standorte             Datenschutz
Carports              Referenzen            Katalog & Downloads   AGB
Überdachungen         Aktionen              Karriere              Cookie-Einstellungen
Balkone & Geländer    Ratgeber
```

---

## 4. VOLLSTÄNDIGE SEITENÜBERSICHT MIT SEO-SPEZIFIKATIONEN

> **Legende:**
> - `[KW]` = Fokus-Keyword
> - `[KW2]` = sekundäres Keyword
> - Alle URLs relativ zu `https://alubram.at`

---

### 4.1 STARTSEITE (Homepage)
**URL:** `/`  
**WordPress-Template:** `front-page.php`  
**Priorität:** ⭐⭐⭐⭐⭐ HÖCHSTE

#### Meta-Tags SEO
```html
<title>ALUBRAM GMBH — Aluminiumzäune, Tore & Carports Hersteller | Himberg bei Wien</title>
<meta name="description" content="Hersteller von Aluminiumzäunen, Einfahrtstoren, Carports & Überdachungen. Direktlieferung in 3–6 Wochen. Mustergarten 24/7 geöffnet. ✔ Kein Zwischenhändler ✔ Montage inklusive. Jetzt kostenlos beraten lassen!">
<meta name="keywords" content="Aluminiumzaun Hersteller Österreich, Zaunanlage Wien, Einfahrtstor Aluminium, Carport Aluminium kaufen, Überdachung Aluminium, Zaunhersteller DACH">
<meta name="robots" content="index, follow, max-snippet:-1, max-image-preview:large, max-video-preview:-1">
<link rel="canonical" href="https://alubram.at/">
<meta name="author" content="ALUBRAM GMBH">
<meta name="geo.region" content="AT-3">
<meta name="geo.placename" content="Himberg bei Wien">
<meta name="geo.position" content="48.0833;16.4500">
<meta name="ICBM" content="48.0833, 16.4500">
<meta name="language" content="de">
<meta name="content-language" content="de-AT">
```

#### Open Graph
```html
<meta property="og:type" content="website">
<meta property="og:title" content="ALUBRAM GMBH — Aluminiumzäune, Tore & Carports direkt vom Hersteller">
<meta property="og:description" content="Hochwertige Aluminium-Produkte für Ihren Garten & Einfahrt. Zäune, Tore, Carports & Überdachungen. Lieferung in 3–6 Wochen. Mustergarten 24/7.">
<meta property="og:url" content="https://alubram.at/">
<meta property="og:site_name" content="ALUBRAM GMBH">
<meta property="og:image" content="https://alubram.at/wp-content/themes/alubramat-child/assets/images/og-homepage.jpg">
<meta property="og:image:width" content="1200">
<meta property="og:image:height" content="630">
<meta property="og:image:alt" content="ALUBRAM GMBH – Aluminiumzäune und Tore Hersteller Österreich">
<meta property="og:locale" content="de_AT">
<meta property="og:locale:alternate" content="de_DE">
<!-- Twitter Card -->
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="ALUBRAM GMBH — Aluminiumzäune & Tore Hersteller Österreich">
<meta name="twitter:description" content="Direkthersteller: Zäune, Tore, Carports, Überdachungen. Lieferung 3–6 Wochen. Mustergarten 24/7.">
<meta name="twitter:image" content="https://alubram.at/wp-content/themes/alubramat-child/assets/images/og-homepage.jpg">
```

#### Schema.org JSON-LD
```json
[
  {
    "@context": "https://schema.org",
    "@type": ["LocalBusiness", "Manufacturer"],
    "@id": "https://alubram.at/#organization",
    "name": "ALUBRAM GMBH",
    "legalName": "ALUBRAM GmbH",
    "url": "https://alubram.at",
    "logo": {
      "@type": "ImageObject",
      "url": "https://alubram.at/wp-content/themes/alubramat-child/assets/images/logo.svg",
      "width": 300,
      "height": 80
    },
    "image": "https://alubram.at/wp-content/themes/alubramat-child/assets/images/og-homepage.jpg",
    "description": "Hersteller von hochwertigen Aluminiumzäunen, Einfahrtstoren, Carports und Überdachungen. Direktlieferung in 3–6 Wochen. Geöffnet 24/7.",
    "slogan": "Wir sind nicht die Größten, aber die Besten und Schnellsten",
    "foundingDate": "2020",
    "vatID": "ATU75724307",
    "address": {
      "@type": "PostalAddress",
      "streetAddress": "Hintere Ortsstraße 31",
      "addressLocality": "Himberg bei Wien",
      "addressRegion": "Niederösterreich",
      "postalCode": "2325",
      "addressCountry": "AT"
    },
    "geo": {
      "@type": "GeoCoordinates",
      "latitude": 48.0833,
      "longitude": 16.4500
    },
    "telephone": ["+43223584793", "+436644373954"],
    "email": "himberg@alubram.at",
    "openingHoursSpecification": [
      {
        "@type": "OpeningHoursSpecification",
        "dayOfWeek": ["Monday","Tuesday","Wednesday","Thursday","Friday","Saturday","Sunday"],
        "opens": "00:00",
        "closes": "23:59",
        "description": "Mustergarten 24/7 geöffnet"
      }
    ],
    "priceRange": "€€€",
    "currenciesAccepted": "EUR",
    "areaServed": [
      {"@type": "Country", "name": "Österreich"},
      {"@type": "Country", "name": "Deutschland"},
      {"@type": "Country", "name": "Schweiz"}
    ],
    "hasOfferCatalog": {
      "@type": "OfferCatalog",
      "name": "ALUBRAM Aluminium-Produktkatalog",
      "itemListElement": [
        {"@type": "Offer", "itemOffered": {"@type": "Product", "name": "Aluminiumzaun"}},
        {"@type": "Offer", "itemOffered": {"@type": "Product", "name": "Einfahrtstor Aluminium"}},
        {"@type": "Offer", "itemOffered": {"@type": "Product", "name": "Carport Aluminium"}},
        {"@type": "Offer", "itemOffered": {"@type": "Product", "name": "Terrassenüberdachung Aluminium"}}
      ]
    },
    "sameAs": [
      "https://www.facebook.com/alubram",
      "https://www.instagram.com/alubram19"
    ]
  },
  {
    "@context": "https://schema.org",
    "@type": "WebSite",
    "@id": "https://alubram.at/#website",
    "url": "https://alubram.at",
    "name": "ALUBRAM GMBH",
    "description": "Hersteller von Aluminiumzäunen, Toren, Carports und Überdachungen in Österreich",
    "publisher": {"@id": "https://alubram.at/#organization"},
    "potentialAction": {
      "@type": "SearchAction",
      "target": {"@type": "EntryPoint", "urlTemplate": "https://alubram.at/?s={search_term_string}"},
      "query-input": "required name=search_term_string"
    }
  }
]
```

---

### 4.2 ÜBER UNS
**URL:** `/uber-uns/`  
**WordPress-Template:** `page-uber-uns.php`  
**Priorität:** ⭐⭐⭐⭐

#### Meta-Tags SEO
```html
<title>Über uns — ALUBRAM GMBH | Ihr Aluminium-Hersteller aus Himberg bei Wien</title>
<meta name="description" content="ALUBRAM GMBH ist Ihr direkter Hersteller für Aluminiumzäune, Tore, Carports & Überdachungen in Österreich. Gegründet 2020. 3 Standorte in NÖ. ✔ Persönliche Beratung ✔ Alles aus einer Hand.">
<meta name="robots" content="index, follow">
<link rel="canonical" href="https://alubram.at/uber-uns/">
```

#### Open Graph
```html
<meta property="og:type" content="website">
<meta property="og:title" content="Über ALUBRAM GMBH — Ihr Aluminium-Hersteller aus Niederösterreich">
<meta property="og:description" content="Lernen Sie ALUBRAM kennen: Direkthersteller für Aluminiumzäune, Tore & Carports. 3 Standorte. Persönliche Beratung. Lieferung in 3–6 Wochen.">
<meta property="og:url" content="https://alubram.at/uber-uns/">
<meta property="og:image" content="https://alubram.at/wp-content/themes/alubramat-child/assets/images/og-uber-uns.jpg">
<meta property="og:image:alt" content="ALUBRAM GMBH Team und Mustergarten Himberg bei Wien">
<meta property="og:locale" content="de_AT">
```

#### Schema.org JSON-LD
```json
[
  {
    "@context": "https://schema.org",
    "@type": "AboutPage",
    "@id": "https://alubram.at/uber-uns/#webpage",
    "url": "https://alubram.at/uber-uns/",
    "name": "Über uns — ALUBRAM GMBH",
    "description": "Informationen über ALUBRAM GMBH, den Direkthersteller für Aluminium-Außenprodukte in Österreich.",
    "isPartOf": {"@id": "https://alubram.at/#website"},
    "about": {"@id": "https://alubram.at/#organization"},
    "breadcrumb": {
      "@type": "BreadcrumbList",
      "itemListElement": [
        {"@type": "ListItem", "position": 1, "name": "Startseite", "item": "https://alubram.at/"},
        {"@type": "ListItem", "position": 2, "name": "Über uns", "item": "https://alubram.at/uber-uns/"}
      ]
    }
  },
  {
    "@context": "https://schema.org",
    "@type": "Organization",
    "@id": "https://alubram.at/#organization",
    "name": "ALUBRAM GMBH",
    "foundingDate": "2020-06-18",
    "founder": {
      "@type": "Person",
      "name": "Ireneusz Szpak",
      "jobTitle": "Geschäftsführer"
    },
    "numberOfEmployees": {"@type": "QuantitativeValue", "value": "10-50"},
    "description": "ALUBRAM GMBH ist ein österreichischer Hersteller und Monteur von hochwertigen Aluminium-Außenprodukten: Zäune, Tore, Carports und Überdachungen."
  }
]
```

---

### 4.3 PRODUKTE — ÜBERSICHTSSEITE
**URL:** `/produkte/`  
**WordPress-Template:** `page-produkte.php`  
**Priorität:** ⭐⭐⭐⭐⭐

#### Meta-Tags SEO
```html
<title>Aluminium-Produkte — ALUBRAM GMBH | Zäune, Tore, Carports & Überdachungen</title>
<meta name="description" content="Entdecken Sie das komplette ALUBRAM-Sortiment: Aluminiumzäune, Einfahrtstoren, Carports, Überdachungen, Balkone & Geländer. Direkt vom Hersteller. Alle Farben RAL. Lieferung 3–6 Wochen.">
<meta name="robots" content="index, follow">
<link rel="canonical" href="https://alubram.at/produkte/">
```

#### Open Graph
```html
<meta property="og:type" content="website">
<meta property="og:title" content="Alle Aluminium-Produkte — ALUBRAM GMBH Österreich">
<meta property="og:description" content="Komplettes Sortiment: Zäune, Tore, Carports, Überdachungen & mehr. Direkthersteller Österreich. RAL-Farben. Günstig & schnell.">
<meta property="og:url" content="https://alubram.at/produkte/">
<meta property="og:image" content="https://alubram.at/wp-content/themes/alubramat-child/assets/images/og-produkte.jpg">
<meta property="og:locale" content="de_AT">
```

#### Schema.org JSON-LD
```json
{
  "@context": "https://schema.org",
  "@type": "CollectionPage",
  "@id": "https://alubram.at/produkte/#webpage",
  "url": "https://alubram.at/produkte/",
  "name": "Aluminium-Produkte — ALUBRAM GMBH",
  "description": "Komplettes Portfolio von Aluminium-Außenprodukten: Zäune, Tore, Carports, Überdachungen.",
  "isPartOf": {"@id": "https://alubram.at/#website"},
  "breadcrumb": {
    "@type": "BreadcrumbList",
    "itemListElement": [
      {"@type": "ListItem", "position": 1, "name": "Startseite", "item": "https://alubram.at/"},
      {"@type": "ListItem", "position": 2, "name": "Produkte", "item": "https://alubram.at/produkte/"}
    ]
  },
  "mainEntity": {
    "@type": "ItemList",
    "itemListElement": [
      {"@type": "ListItem", "position": 1, "name": "Zäune & Zaunfelder", "url": "https://alubram.at/produkte/zaune/"},
      {"@type": "ListItem", "position": 2, "name": "Tore & Einfahrtstore", "url": "https://alubram.at/produkte/tore/"},
      {"@type": "ListItem", "position": 3, "name": "Carports", "url": "https://alubram.at/produkte/carports/"},
      {"@type": "ListItem", "position": 4, "name": "Überdachungen", "url": "https://alubram.at/produkte/ueberdachungen/"},
      {"@type": "ListItem", "position": 5, "name": "Balkone & Geländer", "url": "https://alubram.at/produkte/balkone-gelaender/"}
    ]
  }
}
```

---

### 4.4 ZÄUNE & ZAUNFELDER — KATEGORIENSEITE
**URL:** `/produkte/zaune/`  
**WordPress-Template:** `taxonomy-product_category.php` oder `page-zaune.php`  
**Priorität:** ⭐⭐⭐⭐⭐

#### Meta-Tags SEO
```html
<title>Aluminiumzaun kaufen — Zäune & Zaunfelder | ALUBRAM GMBH Österreich</title>
<meta name="description" content="Hochwertige Aluminiumzäune direkt vom Hersteller: Horizontal, Vertikal, Klassisch, Blickdicht, Industrie & Sondermodelle. ✔ Rostfrei ✔ Wartungsfrei ✔ Pulverbeschichtet ✔ RAL-Farben ✔ Montage inkl.">
<meta name="robots" content="index, follow">
<link rel="canonical" href="https://alubram.at/produkte/zaune/">
```

#### Open Graph
```html
<meta property="og:type" content="website">
<meta property="og:title" content="Aluminiumzaun kaufen — 6 Modelle | ALUBRAM GMBH Direkthersteller">
<meta property="og:description" content="Aluminiumzäune in 6 Ausführungen: Horizontal, Vertikal, Klassisch, Blickdicht, Industrie. Alle RAL-Farben. Lieferung 3–6 Wochen. Österreich.">
<meta property="og:url" content="https://alubram.at/produkte/zaune/">
<meta property="og:image" content="https://alubram.at/wp-content/themes/alubramat-child/assets/images/og-zaune.jpg">
<meta property="og:locale" content="de_AT">
```

#### Schema.org JSON-LD
```json
{
  "@context": "https://schema.org",
  "@type": "CollectionPage",
  "url": "https://alubram.at/produkte/zaune/",
  "name": "Aluminiumzäune & Zaunfelder — ALUBRAM GMBH",
  "description": "Alle Aluminiumzaun-Modelle von ALUBRAM: 6 Produktlinien für jeden Bedarf.",
  "breadcrumb": {
    "@type": "BreadcrumbList",
    "itemListElement": [
      {"@type": "ListItem", "position": 1, "name": "Startseite", "item": "https://alubram.at/"},
      {"@type": "ListItem", "position": 2, "name": "Produkte", "item": "https://alubram.at/produkte/"},
      {"@type": "ListItem", "position": 3, "name": "Zäune & Zaunfelder", "item": "https://alubram.at/produkte/zaune/"}
    ]
  },
  "mainEntity": {
    "@type": "ItemList",
    "itemListElement": [
      {"@type": "ListItem", "position": 1, "name": "Horizontal Zaun", "url": "https://alubram.at/produkte/zaune/horizontal-zaun/"},
      {"@type": "ListItem", "position": 2, "name": "Vertikal Zaun", "url": "https://alubram.at/produkte/zaune/vertikal-zaun/"},
      {"@type": "ListItem", "position": 3, "name": "Klassischer Zaun", "url": "https://alubram.at/produkte/zaune/klassischer-zaun/"},
      {"@type": "ListItem", "position": 4, "name": "Blickdichter Zaun", "url": "https://alubram.at/produkte/zaune/blickdichter-zaun/"},
      {"@type": "ListItem", "position": 5, "name": "Industrie Zaun", "url": "https://alubram.at/produkte/zaune/industrie-zaun/"},
      {"@type": "ListItem", "position": 6, "name": "Sondermodell Zaun", "url": "https://alubram.at/produkte/zaune/sondermodell/"}
    ]
  }
}
```

---

### 4.5 HORIZONTAL ZAUN
**URL:** `/produkte/zaune/horizontal-zaun/`  
**WordPress-Template:** `single-alubram_product.php`  
**Priorität:** ⭐⭐⭐⭐⭐

#### Meta-Tags SEO
```html
<title>Horizontal Zaun Aluminium — BOLERO 40 & SONATA 80 | ALUBRAM GMBH</title>
<meta name="description" content="Horizontaler Aluminiumzaun BOLERO 40 & SONATA 80: Modernes Design, wartungsfrei, pulverbeschichtet. Alle RAL-Farben & Holzoptik. Direkthersteller Österreich. Lieferung 3–6 Wochen. Jetzt Angebot anfordern!">
<meta name="robots" content="index, follow">
<link rel="canonical" href="https://alubram.at/produkte/zaune/horizontal-zaun/">
```

#### Open Graph
```html
<meta property="og:type" content="product">
<meta property="og:title" content="Horizontaler Aluminiumzaun BOLERO 40 — Modernes Design | ALUBRAM">
<meta property="og:description" content="Horizontal Zaun aus Aluminium: rostfrei, wartungsfrei, alle RAL-Farben. Modell BOLERO 40 & SONATA 80. Direkthersteller Österreich.">
<meta property="og:url" content="https://alubram.at/produkte/zaune/horizontal-zaun/">
<meta property="og:image" content="https://alubram.at/wp-content/themes/alubramat-child/assets/images/og-horizontal-zaun.jpg">
<meta property="og:locale" content="de_AT">
```

#### Schema.org JSON-LD
```json
{
  "@context": "https://schema.org",
  "@type": "Product",
  "name": "Horizontal Zaun Aluminium — BOLERO 40",
  "description": "Moderner horizontaler Aluminiumzaun, wartungsfrei und pulverbeschichtet. Erhältlich in allen RAL-Farben und Holzoptik (Thermoprint). Direkthersteller ALUBRAM GMBH, Österreich.",
  "brand": {"@type": "Brand", "name": "ALUBRAM GMBH"},
  "manufacturer": {"@id": "https://alubram.at/#organization"},
  "url": "https://alubram.at/produkte/zaune/horizontal-zaun/",
  "image": "https://alubram.at/wp-content/themes/alubramat-child/assets/images/horizontal-zaun.jpg",
  "category": "Aluminiumzaun / Zaunanlage",
  "material": "Aluminium, pulverbeschichtet",
  "color": "Alle RAL-Farben, Holzoptik (Thermoprint)",
  "additionalProperty": [
    {"@type": "PropertyValue", "name": "Lieferzeit", "value": "3–6 Wochen"},
    {"@type": "PropertyValue", "name": "Garantie", "value": "15 Jahre auf Pulverbeschichtung"},
    {"@type": "PropertyValue", "name": "Material", "value": "Aluminium 6063-T6"},
    {"@type": "PropertyValue", "name": "Montageservice", "value": "Ja, inkl. Fachgerechte Montage"}
  ],
  "offers": {
    "@type": "Offer",
    "priceCurrency": "EUR",
    "priceSpecification": {"@type": "PriceSpecification", "description": "Preis auf Anfrage"},
    "availability": "https://schema.org/InStock",
    "seller": {"@id": "https://alubram.at/#organization"},
    "areaServed": ["AT", "DE", "CH"]
  },
  "breadcrumb": {
    "@type": "BreadcrumbList",
    "itemListElement": [
      {"@type": "ListItem", "position": 1, "name": "Startseite", "item": "https://alubram.at/"},
      {"@type": "ListItem", "position": 2, "name": "Produkte", "item": "https://alubram.at/produkte/"},
      {"@type": "ListItem", "position": 3, "name": "Zäune", "item": "https://alubram.at/produkte/zaune/"},
      {"@type": "ListItem", "position": 4, "name": "Horizontal Zaun", "item": "https://alubram.at/produkte/zaune/horizontal-zaun/"}
    ]
  }
}
```

---

### 4.6 VERTIKAL ZAUN
**URL:** `/produkte/zaune/vertikal-zaun/`  
**WordPress-Template:** `single-alubram_product.php`  
**Priorität:** ⭐⭐⭐⭐

#### Meta-Tags SEO
```html
<title>Vertikal Zaun Aluminium — ELEGIA 40 & IDYLLA 80 | ALUBRAM GMBH Österreich</title>
<meta name="description" content="Vertikaler Aluminiumzaun ELEGIA 40 & IDYLLA 80: Klassisch-modernes Design bis 3000 mm Höhe. Rostfrei, wartungsfrei, pulverbeschichtet. Direkthersteller Österreich. Kostenlos beraten lassen!">
<meta name="robots" content="index, follow">
<link rel="canonical" href="https://alubram.at/produkte/zaune/vertikal-zaun/">
```

#### Open Graph
```html
<meta property="og:type" content="product">
<meta property="og:title" content="Vertikaler Aluminiumzaun ELEGIA 40 — bis 3m Höhe | ALUBRAM">
<meta property="og:description" content="Vertikal Zaun aus Aluminium: zeitloses Design, bis 3000mm, alle RAL-Farben. Modell ELEGIA & IDYLLA. Österreich.">
<meta property="og:url" content="https://alubram.at/produkte/zaune/vertikal-zaun/">
<meta property="og:image" content="https://alubram.at/wp-content/themes/alubramat-child/assets/images/og-vertikal-zaun.jpg">
<meta property="og:locale" content="de_AT">
```

#### Schema.org JSON-LD
```json
{
  "@context": "https://schema.org",
  "@type": "Product",
  "name": "Vertikal Zaun Aluminium — ELEGIA 40",
  "description": "Vertikaler Aluminiumzaun ELEGIA 40 und IDYLLA 80, erhältlich bis 3000mm Höhe. Wartungsfrei, pulverbeschichtet, alle RAL-Farben.",
  "brand": {"@type": "Brand", "name": "ALUBRAM GMBH"},
  "manufacturer": {"@id": "https://alubram.at/#organization"},
  "url": "https://alubram.at/produkte/zaune/vertikal-zaun/",
  "category": "Aluminiumzaun / Zaunanlage",
  "material": "Aluminium, pulverbeschichtet",
  "additionalProperty": [
    {"@type": "PropertyValue", "name": "Maximale Höhe", "value": "3000 mm"},
    {"@type": "PropertyValue", "name": "Lieferzeit", "value": "3–6 Wochen"}
  ],
  "offers": {
    "@type": "Offer",
    "priceCurrency": "EUR",
    "availability": "https://schema.org/InStock",
    "seller": {"@id": "https://alubram.at/#organization"}
  },
  "breadcrumb": {
    "@type": "BreadcrumbList",
    "itemListElement": [
      {"@type": "ListItem", "position": 1, "name": "Startseite", "item": "https://alubram.at/"},
      {"@type": "ListItem", "position": 2, "name": "Produkte", "item": "https://alubram.at/produkte/"},
      {"@type": "ListItem", "position": 3, "name": "Zäune", "item": "https://alubram.at/produkte/zaune/"},
      {"@type": "ListItem", "position": 4, "name": "Vertikal Zaun", "item": "https://alubram.at/produkte/zaune/vertikal-zaun/"}
    ]
  }
}
```

---

### 4.7 KLASSISCHER ZAUN
**URL:** `/produkte/zaune/klassischer-zaun/`  
**WordPress-Template:** `single-alubram_product.php`  
**Priorität:** ⭐⭐⭐

#### Meta-Tags SEO
```html
<title>Klassischer Aluminiumzaun — Dekorativ & Elegant | ALUBRAM GMBH</title>
<meta name="description" content="Klassischer Aluminiumzaun in dekorativem Design: Zeitloses Erscheinungsbild, rostfrei, wartungsfrei. Alle RAL-Farben erhältlich. Direkthersteller aus Niederösterreich. Jetzt Angebot anfragen!">
<meta name="robots" content="index, follow">
<link rel="canonical" href="https://alubram.at/produkte/zaune/klassischer-zaun/">
```

#### Open Graph
```html
<meta property="og:type" content="product">
<meta property="og:title" content="Klassischer Aluminiumzaun — Dekoratives Design | ALUBRAM GMBH">
<meta property="og:description" content="Klassischer Zaun aus Aluminium: elegantes Erscheinungsbild, langlebig, wartungsfrei. Alle RAL-Farben. Österreich.">
<meta property="og:url" content="https://alubram.at/produkte/zaune/klassischer-zaun/">
<meta property="og:image" content="https://alubram.at/wp-content/themes/alubramat-child/assets/images/og-klassischer-zaun.jpg">
<meta property="og:locale" content="de_AT">
```

#### Schema.org JSON-LD
```json
{
  "@context": "https://schema.org",
  "@type": "Product",
  "name": "Klassischer Aluminiumzaun",
  "description": "Dekorativer klassischer Aluminiumzaun, wartungsfrei und pulverbeschichtet. Zeitloses Design für Haus und Garten.",
  "brand": {"@type": "Brand", "name": "ALUBRAM GMBH"},
  "manufacturer": {"@id": "https://alubram.at/#organization"},
  "url": "https://alubram.at/produkte/zaune/klassischer-zaun/",
  "category": "Aluminiumzaun / Dekorativzaun",
  "offers": {
    "@type": "Offer",
    "priceCurrency": "EUR",
    "availability": "https://schema.org/InStock",
    "seller": {"@id": "https://alubram.at/#organization"}
  },
  "breadcrumb": {
    "@type": "BreadcrumbList",
    "itemListElement": [
      {"@type": "ListItem", "position": 1, "name": "Startseite", "item": "https://alubram.at/"},
      {"@type": "ListItem", "position": 2, "name": "Produkte", "item": "https://alubram.at/produkte/"},
      {"@type": "ListItem", "position": 3, "name": "Zäune", "item": "https://alubram.at/produkte/zaune/"},
      {"@type": "ListItem", "position": 4, "name": "Klassischer Zaun", "item": "https://alubram.at/produkte/zaune/klassischer-zaun/"}
    ]
  }
}
```

---

### 4.8 BLICKDICHTER ZAUN (SICHTSCHUTZ)
**URL:** `/produkte/zaune/blickdichter-zaun/`  
**WordPress-Template:** `single-alubram_product.php`  
**Priorität:** ⭐⭐⭐⭐

#### Meta-Tags SEO
```html
<title>Blickdichter Zaun Aluminium — Sichtschutz LAMELLO | ALUBRAM GMBH Österreich</title>
<meta name="description" content="Blickdichter Aluminiumzaun LAMELLO: 100% Sichtschutz, wartungsfrei, pulverbeschichtet. Ideal für Gärten & Terrassen. Alle RAL-Farben. Direkthersteller Österreich. Lieferzeit 3–6 Wochen.">
<meta name="robots" content="index, follow">
<link rel="canonical" href="https://alubram.at/produkte/zaune/blickdichter-zaun/">
```

#### Open Graph
```html
<meta property="og:type" content="product">
<meta property="og:title" content="Blickdichter Aluminiumzaun LAMELLO — 100% Sichtschutz | ALUBRAM">
<meta property="og:description" content="Sichtschutzzaun aus Aluminium: volle Privatsphäre, langlebig, wartungsfrei. Modell LAMELLO. Direkthersteller AT.">
<meta property="og:url" content="https://alubram.at/produkte/zaune/blickdichter-zaun/">
<meta property="og:image" content="https://alubram.at/wp-content/themes/alubramat-child/assets/images/og-blickdichter-zaun.jpg">
<meta property="og:locale" content="de_AT">
```

#### Schema.org JSON-LD
```json
{
  "@context": "https://schema.org",
  "@type": "Product",
  "name": "Blickdichter Zaun Aluminium — LAMELLO",
  "description": "Blickdichter Aluminiumzaun für maximale Privatsphäre. Modell LAMELLO, pulverbeschichtet, wartungsfrei, alle RAL-Farben.",
  "brand": {"@type": "Brand", "name": "ALUBRAM GMBH"},
  "manufacturer": {"@id": "https://alubram.at/#organization"},
  "url": "https://alubram.at/produkte/zaune/blickdichter-zaun/",
  "category": "Sichtschutzzaun / Aluminiumzaun",
  "offers": {
    "@type": "Offer",
    "priceCurrency": "EUR",
    "availability": "https://schema.org/InStock",
    "seller": {"@id": "https://alubram.at/#organization"}
  },
  "breadcrumb": {
    "@type": "BreadcrumbList",
    "itemListElement": [
      {"@type": "ListItem", "position": 1, "name": "Startseite", "item": "https://alubram.at/"},
      {"@type": "ListItem", "position": 2, "name": "Produkte", "item": "https://alubram.at/produkte/"},
      {"@type": "ListItem", "position": 3, "name": "Zäune", "item": "https://alubram.at/produkte/zaune/"},
      {"@type": "ListItem", "position": 4, "name": "Blickdichter Zaun", "item": "https://alubram.at/produkte/zaune/blickdichter-zaun/"}
    ]
  }
}
```

---

### 4.9 INDUSTRIE ZAUN
**URL:** `/produkte/zaune/industrie-zaun/`  
**WordPress-Template:** `single-alubram_product.php`  
**Priorität:** ⭐⭐⭐

#### Meta-Tags SEO
```html
<title>Industrie Zaun Aluminium — Gewerbliche Zaunlösungen | ALUBRAM GMBH</title>
<meta name="description" content="Industrie-Zaunpanele aus Aluminium für gewerbliche & industrielle Anwendungen: robust, langlebig, wartungsfrei. Pulverbeschichtet. Direkthersteller Österreich. Angebot anfordern!">
<meta name="robots" content="index, follow">
<link rel="canonical" href="https://alubram.at/produkte/zaune/industrie-zaun/">
```

#### Open Graph
```html
<meta property="og:type" content="product">
<meta property="og:title" content="Industrie Zaun Aluminium — Gewerbliche Zaunlösungen | ALUBRAM">
<meta property="og:description" content="Industriezaun aus Aluminium: für Gewerbe, Firmen & Industrie. Robust, wartungsfrei. Direkthersteller AT.">
<meta property="og:url" content="https://alubram.at/produkte/zaune/industrie-zaun/">
<meta property="og:image" content="https://alubram.at/wp-content/themes/alubramat-child/assets/images/og-industrie-zaun.jpg">
<meta property="og:locale" content="de_AT">
```

#### Schema.org JSON-LD
```json
{
  "@context": "https://schema.org",
  "@type": "Product",
  "name": "Industrie Zaun Aluminium",
  "description": "Industrielle Aluminiumzaunpanele für gewerbliche Anwendungen. Robust, wartungsfrei, pulverbeschichtet.",
  "brand": {"@type": "Brand", "name": "ALUBRAM GMBH"},
  "manufacturer": {"@id": "https://alubram.at/#organization"},
  "url": "https://alubram.at/produkte/zaune/industrie-zaun/",
  "category": "Industriezaun / Gewerbezaun",
  "offers": {
    "@type": "Offer",
    "priceCurrency": "EUR",
    "availability": "https://schema.org/InStock",
    "seller": {"@id": "https://alubram.at/#organization"}
  },
  "breadcrumb": {
    "@type": "BreadcrumbList",
    "itemListElement": [
      {"@type": "ListItem", "position": 1, "name": "Startseite", "item": "https://alubram.at/"},
      {"@type": "ListItem", "position": 2, "name": "Produkte", "item": "https://alubram.at/produkte/"},
      {"@type": "ListItem", "position": 3, "name": "Zäune", "item": "https://alubram.at/produkte/zaune/"},
      {"@type": "ListItem", "position": 4, "name": "Industrie Zaun", "item": "https://alubram.at/produkte/zaune/industrie-zaun/"}
    ]
  }
}
```

---

### 4.10 SONDERMODELL ZAUN
**URL:** `/produkte/zaune/sondermodell/`  
**WordPress-Template:** `single-alubram_product.php`  
**Priorität:** ⭐⭐⭐

#### Meta-Tags SEO
```html
<title>Sondermodell Zaun — Individuelle Aluminiumzäune nach Maß | ALUBRAM GMBH</title>
<meta name="description" content="Individuelle Aluminiumzäune nach Maß: Sonderanfertigungen für besondere Anforderungen. ALUBRAM plant & fertigt Ihren Traumzaun. Alle Abmessungen möglich. Angebot anfordern!">
<meta name="robots" content="index, follow">
<link rel="canonical" href="https://alubram.at/produkte/zaune/sondermodell/">
```

#### Open Graph
```html
<meta property="og:type" content="product">
<meta property="og:title" content="Sondermodell Zaun — Individuelle Anfertigung nach Maß | ALUBRAM">
<meta property="og:description" content="Maßgefertigte Aluminiumzäune nach Ihren Wünschen. ALUBRAM realisiert Sonderlösungen. Österreich.">
<meta property="og:url" content="https://alubram.at/produkte/zaune/sondermodell/">
<meta property="og:image" content="https://alubram.at/wp-content/themes/alubramat-child/assets/images/og-sondermodell.jpg">
<meta property="og:locale" content="de_AT">
```

#### Schema.org JSON-LD
```json
{
  "@context": "https://schema.org",
  "@type": "Product",
  "name": "Sondermodell Zaun — Individuelle Aluminiumzäune nach Maß",
  "description": "Maßgefertigte Aluminiumzäune für individuelle Anforderungen. ALUBRAM plant und fertigt Sonderlösungen nach Kundenwunsch.",
  "brand": {"@type": "Brand", "name": "ALUBRAM GMBH"},
  "manufacturer": {"@id": "https://alubram.at/#organization"},
  "url": "https://alubram.at/produkte/zaune/sondermodell/",
  "category": "Sonderlösung / Maßanfertigung",
  "offers": {
    "@type": "Offer",
    "priceCurrency": "EUR",
    "availability": "https://schema.org/InStock",
    "seller": {"@id": "https://alubram.at/#organization"}
  },
  "breadcrumb": {
    "@type": "BreadcrumbList",
    "itemListElement": [
      {"@type": "ListItem", "position": 1, "name": "Startseite", "item": "https://alubram.at/"},
      {"@type": "ListItem", "position": 2, "name": "Produkte", "item": "https://alubram.at/produkte/"},
      {"@type": "ListItem", "position": 3, "name": "Zäune", "item": "https://alubram.at/produkte/zaune/"},
      {"@type": "ListItem", "position": 4, "name": "Sondermodell Zaun", "item": "https://alubram.at/produkte/zaune/sondermodell/"}
    ]
  }
}
```

---

### 4.11 TORE & EINFAHRTSTORE — KATEGORIENSEITE
**URL:** `/produkte/tore/`  
**WordPress-Template:** `page-tore.php`  
**Priorität:** ⭐⭐⭐⭐⭐

#### Meta-Tags SEO
```html
<title>Einfahrtstor & Hoftor Aluminium kaufen — ALUBRAM GMBH Österreich</title>
<meta name="description" content="Aluminium-Tore direkt vom Hersteller: Schiebetore, Flügeltore & Eingangstore. Elektrisch oder manuell. Alle RAL-Farben. ✔ Lieferzeit 3–6 Wochen ✔ Montage inkl. ✔ Wien & NÖ">
<meta name="robots" content="index, follow">
<link rel="canonical" href="https://alubram.at/produkte/tore/">
```

#### Open Graph
```html
<meta property="og:type" content="website">
<meta property="og:title" content="Einfahrtstor Aluminium kaufen — Schiebetor & Flügeltor | ALUBRAM GMBH">
<meta property="og:description" content="Hochwertige Aluminium-Tore: Schiebetore, Flügeltore, Eingangstore. Elektrisch & manuell. Direkthersteller AT.">
<meta property="og:url" content="https://alubram.at/produkte/tore/">
<meta property="og:image" content="https://alubram.at/wp-content/themes/alubramat-child/assets/images/og-tore.jpg">
<meta property="og:locale" content="de_AT">
```

#### Schema.org JSON-LD
```json
{
  "@context": "https://schema.org",
  "@type": "CollectionPage",
  "url": "https://alubram.at/produkte/tore/",
  "name": "Einfahrtstoren & Hoftore — ALUBRAM GMBH",
  "description": "Aluminium-Tore in drei Ausführungen: Schiebetore, Flügeltore, Eingangstore. Elektrisch oder manuell betrieben.",
  "breadcrumb": {
    "@type": "BreadcrumbList",
    "itemListElement": [
      {"@type": "ListItem", "position": 1, "name": "Startseite", "item": "https://alubram.at/"},
      {"@type": "ListItem", "position": 2, "name": "Produkte", "item": "https://alubram.at/produkte/"},
      {"@type": "ListItem", "position": 3, "name": "Tore & Einfahrtstore", "item": "https://alubram.at/produkte/tore/"}
    ]
  },
  "mainEntity": {
    "@type": "ItemList",
    "itemListElement": [
      {"@type": "ListItem", "position": 1, "name": "Schiebetor Aluminium", "url": "https://alubram.at/produkte/tore/schiebetor/"},
      {"@type": "ListItem", "position": 2, "name": "Flügeltor & Einfahrtstor", "url": "https://alubram.at/produkte/tore/fluegeltor/"},
      {"@type": "ListItem", "position": 3, "name": "Eingangstor / Gehtor", "url": "https://alubram.at/produkte/tore/eingangstor/"}
    ]
  }
}
```

---

### 4.12 SCHIEBETOR ALUMINIUM
**URL:** `/produkte/tore/schiebetor/`  
**WordPress-Template:** `single-alubram_product.php`  
**Priorität:** ⭐⭐⭐⭐⭐

#### Meta-Tags SEO
```html
<title>Schiebetor Aluminium kaufen — Elektrisch & freistehend | ALUBRAM GMBH</title>
<meta name="description" content="Aluminium-Schiebetor: elektrisch angetrieben, freistehend, mit Lichtschranke & Induktionsschlaufe. Alle RAL-Farben. Direkthersteller Österreich. Lieferzeit 3–6 Wochen. Angebot anfordern!">
<meta name="robots" content="index, follow">
<link rel="canonical" href="https://alubram.at/produkte/tore/schiebetor/">
```

#### Open Graph
```html
<meta property="og:type" content="product">
<meta property="og:title" content="Schiebetor Aluminium — Elektrisch, freistehend | ALUBRAM GMBH">
<meta property="og:description" content="Elektrisches Aluminiumschiebetor: wartungsfrei, langlebig, alle RAL-Farben. Direkthersteller Österreich.">
<meta property="og:url" content="https://alubram.at/produkte/tore/schiebetor/">
<meta property="og:image" content="https://alubram.at/wp-content/themes/alubramat-child/assets/images/og-schiebetor.jpg">
<meta property="og:locale" content="de_AT">
```

#### Schema.org JSON-LD
```json
{
  "@context": "https://schema.org",
  "@type": "Product",
  "name": "Schiebetor Aluminium — Elektrisch & freistehend",
  "description": "Elektrisch betriebenes Aluminium-Schiebetor, freistehend. Mit Lichtschranken, Induktionsschlaufe und GSM-Modul. Pulverbeschichtet, alle RAL-Farben.",
  "brand": {"@type": "Brand", "name": "ALUBRAM GMBH"},
  "manufacturer": {"@id": "https://alubram.at/#organization"},
  "url": "https://alubram.at/produkte/tore/schiebetor/",
  "category": "Einfahrtstor / Schiebetor",
  "additionalProperty": [
    {"@type": "PropertyValue", "name": "Antrieb", "value": "Elektrisch (optional manuell)"},
    {"@type": "PropertyValue", "name": "Sicherheit", "value": "Lichtschranke, Induktionsschlaufe"},
    {"@type": "PropertyValue", "name": "Steuerung", "value": "Funk, GSM-Modul, Timer"},
    {"@type": "PropertyValue", "name": "Lieferzeit", "value": "3–6 Wochen"}
  ],
  "offers": {
    "@type": "Offer",
    "priceCurrency": "EUR",
    "availability": "https://schema.org/InStock",
    "seller": {"@id": "https://alubram.at/#organization"}
  },
  "breadcrumb": {
    "@type": "BreadcrumbList",
    "itemListElement": [
      {"@type": "ListItem", "position": 1, "name": "Startseite", "item": "https://alubram.at/"},
      {"@type": "ListItem", "position": 2, "name": "Produkte", "item": "https://alubram.at/produkte/"},
      {"@type": "ListItem", "position": 3, "name": "Tore", "item": "https://alubram.at/produkte/tore/"},
      {"@type": "ListItem", "position": 4, "name": "Schiebetor", "item": "https://alubram.at/produkte/tore/schiebetor/"}
    ]
  }
}
```

---

### 4.13 FLÜGELTOR & EINFAHRTSTOR
**URL:** `/produkte/tore/fluegeltor/`  
**WordPress-Template:** `single-alubram_product.php`  
**Priorität:** ⭐⭐⭐⭐

#### Meta-Tags SEO
```html
<title>Flügeltor & Einfahrtstor Aluminium — Einflügel & Zweiflügel | ALUBRAM GMBH</title>
<meta name="description" content="Aluminium-Flügeltor: Ein- und Zweiflügelig, manuell oder elektrisch angetrieben. Ideal als Einfahrtstor. Alle RAL-Farben. Direkthersteller Österreich. Angebot anfordern!">
<meta name="robots" content="index, follow">
<link rel="canonical" href="https://alubram.at/produkte/tore/fluegeltor/">
```

#### Open Graph
```html
<meta property="og:type" content="product">
<meta property="og:title" content="Flügeltor Aluminium — Einfahrtstor Ein- & Zweiflügelig | ALUBRAM">
<meta property="og:description" content="Aluminium-Flügeltor als Einfahrtstor: klassische Optik, langlebig. Elektrisch oder manuell. Direkthersteller AT.">
<meta property="og:url" content="https://alubram.at/produkte/tore/fluegeltor/">
<meta property="og:image" content="https://alubram.at/wp-content/themes/alubramat-child/assets/images/og-fluegeltor.jpg">
<meta property="og:locale" content="de_AT">
```

#### Schema.org JSON-LD
```json
{
  "@context": "https://schema.org",
  "@type": "Product",
  "name": "Flügeltor & Einfahrtstor Aluminium",
  "description": "Aluminium-Flügeltor als ein- oder zweiflügeliges Einfahrtstor. Manuell oder elektrisch. Pulverbeschichtet, wartungsfrei.",
  "brand": {"@type": "Brand", "name": "ALUBRAM GMBH"},
  "manufacturer": {"@id": "https://alubram.at/#organization"},
  "url": "https://alubram.at/produkte/tore/fluegeltor/",
  "category": "Flügeltor / Einfahrtstor",
  "additionalProperty": [
    {"@type": "PropertyValue", "name": "Varianten", "value": "Einflügelig, Zweiflügelig"},
    {"@type": "PropertyValue", "name": "Antrieb", "value": "Manuell oder elektrisch"},
    {"@type": "PropertyValue", "name": "Lieferzeit", "value": "3–6 Wochen"}
  ],
  "offers": {
    "@type": "Offer",
    "priceCurrency": "EUR",
    "availability": "https://schema.org/InStock",
    "seller": {"@id": "https://alubram.at/#organization"}
  },
  "breadcrumb": {
    "@type": "BreadcrumbList",
    "itemListElement": [
      {"@type": "ListItem", "position": 1, "name": "Startseite", "item": "https://alubram.at/"},
      {"@type": "ListItem", "position": 2, "name": "Produkte", "item": "https://alubram.at/produkte/"},
      {"@type": "ListItem", "position": 3, "name": "Tore", "item": "https://alubram.at/produkte/tore/"},
      {"@type": "ListItem", "position": 4, "name": "Flügeltor & Einfahrtstor", "item": "https://alubram.at/produkte/tore/fluegeltor/"}
    ]
  }
}
```

---

### 4.14 EINGANGSTOR / GEHTOR (GARTENTOR)
**URL:** `/produkte/tore/eingangstor/`  
**WordPress-Template:** `single-alubram_product.php`  
**Priorität:** ⭐⭐⭐⭐

#### Meta-Tags SEO
```html
<title>Eingangstor & Gartentor Aluminium — Gehtor für Fußgänger | ALUBRAM GMBH</title>
<meta name="description" content="Aluminium Eingangstor & Gartentor für Fußgänger: elegant, wartungsfrei, alle RAL-Farben. Passend zu Ihrer Zaunanlage. Direkthersteller Österreich. Lieferzeit 3–6 Wochen.">
<meta name="robots" content="index, follow">
<link rel="canonical" href="https://alubram.at/produkte/tore/eingangstor/">
```

#### Open Graph
```html
<meta property="og:type" content="product">
<meta property="og:title" content="Eingangstor & Gartentor Aluminium — Gehtor | ALUBRAM GMBH">
<meta property="og:description" content="Aluminium-Gartentor als Eingangstor: wartungsfrei, alle RAL-Farben, passend zur Zaunanlage. Direkthersteller AT.">
<meta property="og:url" content="https://alubram.at/produkte/tore/eingangstor/">
<meta property="og:image" content="https://alubram.at/wp-content/themes/alubramat-child/assets/images/og-eingangstor.jpg">
<meta property="og:locale" content="de_AT">
```

#### Schema.org JSON-LD
```json
{
  "@context": "https://schema.org",
  "@type": "Product",
  "name": "Eingangstor / Gehtor Aluminium",
  "description": "Aluminium-Eingangstor für Fußgänger, passend zu allen ALUBRAM Zaunanlagen. Wartungsfrei, pulverbeschichtet, alle RAL-Farben.",
  "brand": {"@type": "Brand", "name": "ALUBRAM GMBH"},
  "manufacturer": {"@id": "https://alubram.at/#organization"},
  "url": "https://alubram.at/produkte/tore/eingangstor/",
  "category": "Eingangstor / Gartentor / Gehtor",
  "offers": {
    "@type": "Offer",
    "priceCurrency": "EUR",
    "availability": "https://schema.org/InStock",
    "seller": {"@id": "https://alubram.at/#organization"}
  },
  "breadcrumb": {
    "@type": "BreadcrumbList",
    "itemListElement": [
      {"@type": "ListItem", "position": 1, "name": "Startseite", "item": "https://alubram.at/"},
      {"@type": "ListItem", "position": 2, "name": "Produkte", "item": "https://alubram.at/produkte/"},
      {"@type": "ListItem", "position": 3, "name": "Tore", "item": "https://alubram.at/produkte/tore/"},
      {"@type": "ListItem", "position": 4, "name": "Eingangstor / Gehtor", "item": "https://alubram.at/produkte/tore/eingangstor/"}
    ]
  }
}
```

---

### 4.15 CARPORTS — KATEGORIENSEITE
**URL:** `/produkte/carports/`  
**WordPress-Template:** `single-alubram_product.php`  
**Priorität:** ⭐⭐⭐⭐⭐

#### Meta-Tags SEO
```html
<title>Carport Aluminium kaufen — Wiata garażowa | ALUBRAM GMBH Wien Österreich</title>
<meta name="description" content="Aluminium-Carport direkt vom Hersteller: freistehend, robust, wartungsfrei. Verschiedene Dacheindeckungen: Glas, Polycarbonat, Blech. Alle RAL-Farben. Lieferzeit 3–6 Wochen. Wien & NÖ.">
<meta name="robots" content="index, follow">
<link rel="canonical" href="https://alubram.at/produkte/carports/">
```

#### Open Graph
```html
<meta property="og:type" content="product">
<meta property="og:title" content="Carport Aluminium kaufen — Direkt vom Hersteller | ALUBRAM GMBH Wien">
<meta property="og:description" content="Aluminium-Carport: stilvoll, robust, wartungsfrei. Glas, Polycarbonat oder Blech. Direkthersteller Wien/NÖ. Lieferung 3–6 Wochen.">
<meta property="og:url" content="https://alubram.at/produkte/carports/">
<meta property="og:image" content="https://alubram.at/wp-content/themes/alubramat-child/assets/images/og-carport.jpg">
<meta property="og:locale" content="de_AT">
```

#### Schema.org JSON-LD
```json
{
  "@context": "https://schema.org",
  "@type": "Product",
  "name": "Carport Aluminium — ALUBRAM GMBH",
  "description": "Aluminium-Carport für 1–3 Fahrzeuge. Dacheindeckung: Glas, Polycarbonat oder Blech. Optional mit LED-Beleuchtung. Wartungsfrei, pulverbeschichtet. Direkthersteller Österreich.",
  "brand": {"@type": "Brand", "name": "ALUBRAM GMBH"},
  "manufacturer": {"@id": "https://alubram.at/#organization"},
  "url": "https://alubram.at/produkte/carports/",
  "category": "Carport / Überdachung",
  "additionalProperty": [
    {"@type": "PropertyValue", "name": "Kapazität", "value": "1–3 Fahrzeuge"},
    {"@type": "PropertyValue", "name": "Dachoptionen", "value": "Glas, Polycarbonat, Blech, Sandwichpaneel"},
    {"@type": "PropertyValue", "name": "Extras", "value": "LED-Beleuchtung, Markisen, Lamellen"},
    {"@type": "PropertyValue", "name": "Lieferzeit", "value": "3–6 Wochen"},
    {"@type": "PropertyValue", "name": "Garantie", "value": "Langfristig auf Aluminium-Konstruktion"}
  ],
  "offers": {
    "@type": "Offer",
    "priceCurrency": "EUR",
    "availability": "https://schema.org/InStock",
    "seller": {"@id": "https://alubram.at/#organization"}
  },
  "breadcrumb": {
    "@type": "BreadcrumbList",
    "itemListElement": [
      {"@type": "ListItem", "position": 1, "name": "Startseite", "item": "https://alubram.at/"},
      {"@type": "ListItem", "position": 2, "name": "Produkte", "item": "https://alubram.at/produkte/"},
      {"@type": "ListItem", "position": 3, "name": "Carports", "item": "https://alubram.at/produkte/carports/"}
    ]
  }
}
```

---

### 4.16 ÜBERDACHUNGEN — KATEGORIENSEITE
**URL:** `/produkte/ueberdachungen/`  
**WordPress-Template:** `page-ueberdachungen.php`  
**Priorität:** ⭐⭐⭐⭐⭐

#### Meta-Tags SEO
```html
<title>Überdachungen Aluminium kaufen — Pergola, Vordach & Terrasse | ALUBRAM GMBH</title>
<meta name="description" content="Aluminium-Überdachungen vom Hersteller: Pergola, Vordach, Terrassenüberdachung Premium & Standard. Glas, Polycarbonat oder Blech. ✔ Wartungsfrei ✔ Lieferzeit 3–6 Wochen ✔ Montage inkl.">
<meta name="robots" content="index, follow">
<link rel="canonical" href="https://alubram.at/produkte/ueberdachungen/">
```

#### Open Graph
```html
<meta property="og:type" content="website">
<meta property="og:title" content="Überdachungen Aluminium — Pergola, Terrasse & Vordach | ALUBRAM GMBH">
<meta property="og:description" content="Alle Aluminium-Überdachungen von ALUBRAM: Pergola, Vordach, Terrassenüberdachung. Direkthersteller. Wien/NÖ/AT.">
<meta property="og:url" content="https://alubram.at/produkte/ueberdachungen/">
<meta property="og:image" content="https://alubram.at/wp-content/themes/alubramat-child/assets/images/og-ueberdachungen.jpg">
<meta property="og:locale" content="de_AT">
```

#### Schema.org JSON-LD
```json
{
  "@context": "https://schema.org",
  "@type": "CollectionPage",
  "url": "https://alubram.at/produkte/ueberdachungen/",
  "name": "Überdachungen aus Aluminium — ALUBRAM GMBH",
  "description": "Komplettes Überdachungssortiment: Pergola, Vordach, Terrassenüberdachung Premium und Standard.",
  "breadcrumb": {
    "@type": "BreadcrumbList",
    "itemListElement": [
      {"@type": "ListItem", "position": 1, "name": "Startseite", "item": "https://alubram.at/"},
      {"@type": "ListItem", "position": 2, "name": "Produkte", "item": "https://alubram.at/produkte/"},
      {"@type": "ListItem", "position": 3, "name": "Überdachungen", "item": "https://alubram.at/produkte/ueberdachungen/"}
    ]
  }
}
```

---

### 4.17 PERGOLA
**URL:** `/produkte/ueberdachungen/pergola/`  
**WordPress-Template:** `single-alubram_product.php`  
**Priorität:** ⭐⭐⭐⭐

#### Meta-Tags SEO
```html
<title>Pergola Aluminium kaufen — Freisitz & Terrassenüberdachung | ALUBRAM GMBH</title>
<meta name="description" content="Aluminium-Pergola: moderner Freisitz, wartungsfrei, sturmfest. Optional mit Lamellendach, Markise & LED-Beleuchtung. Alle RAL-Farben. Direkthersteller Österreich. Lieferzeit 3–6 Wochen.">
<meta name="robots" content="index, follow">
<link rel="canonical" href="https://alubram.at/produkte/ueberdachungen/pergola/">
```

#### Open Graph
```html
<meta property="og:type" content="product">
<meta property="og:title" content="Pergola Aluminium — Moderner Freisitz für Terrasse & Garten | ALUBRAM">
<meta property="og:description" content="Aluminium-Pergola: stilvoll, langlebig, wartungsfrei. Lamellen, Markise, LED. Direkthersteller AT.">
<meta property="og:url" content="https://alubram.at/produkte/ueberdachungen/pergola/">
<meta property="og:image" content="https://alubram.at/wp-content/themes/alubramat-child/assets/images/og-pergola.jpg">
<meta property="og:locale" content="de_AT">
```

#### Schema.org JSON-LD
```json
{
  "@context": "https://schema.org",
  "@type": "Product",
  "name": "Pergola Aluminium",
  "description": "Aluminium-Pergola als stilvoller Freisitz für Terrasse und Garten. Optional mit Lamellendach, Markise und LED-Beleuchtung. Wartungsfrei, alle RAL-Farben.",
  "brand": {"@type": "Brand", "name": "ALUBRAM GMBH"},
  "manufacturer": {"@id": "https://alubram.at/#organization"},
  "url": "https://alubram.at/produkte/ueberdachungen/pergola/",
  "category": "Pergola / Überdachung",
  "additionalProperty": [
    {"@type": "PropertyValue", "name": "Optionen", "value": "Lamellendach, Markise, LED-Beleuchtung"},
    {"@type": "PropertyValue", "name": "Lieferzeit", "value": "3–6 Wochen"}
  ],
  "offers": {
    "@type": "Offer",
    "priceCurrency": "EUR",
    "availability": "https://schema.org/InStock",
    "seller": {"@id": "https://alubram.at/#organization"}
  },
  "breadcrumb": {
    "@type": "BreadcrumbList",
    "itemListElement": [
      {"@type": "ListItem", "position": 1, "name": "Startseite", "item": "https://alubram.at/"},
      {"@type": "ListItem", "position": 2, "name": "Produkte", "item": "https://alubram.at/produkte/"},
      {"@type": "ListItem", "position": 3, "name": "Überdachungen", "item": "https://alubram.at/produkte/ueberdachungen/"},
      {"@type": "ListItem", "position": 4, "name": "Pergola", "item": "https://alubram.at/produkte/ueberdachungen/pergola/"}
    ]
  }
}
```

---

### 4.18 VORDACH
**URL:** `/produkte/ueberdachungen/vordach/`  
**WordPress-Template:** `single-alubram_product.php`  
**Priorität:** ⭐⭐⭐

#### Meta-Tags SEO
```html
<title>Vordach Aluminium kaufen — Haustürvordach & Eingangsüberdachung | ALUBRAM GMBH</title>
<meta name="description" content="Aluminium-Vordach für Haustür & Eingang: modernes Design, wetterfest, wartungsfrei. Glas- oder Polycarbonat-Überdachung. Alle RAL-Farben. Direkthersteller Österreich. Angebot anfordern!">
<meta name="robots" content="index, follow">
<link rel="canonical" href="https://alubram.at/produkte/ueberdachungen/vordach/">
```

#### Open Graph
```html
<meta property="og:type" content="product">
<meta property="og:title" content="Vordach Aluminium — Eingangsüberdachung für Haustür | ALUBRAM GMBH">
<meta property="og:description" content="Aluminium-Vordach: stilvoller Schutz für Ihren Eingang. Glas oder Polycarbonat. Direkthersteller AT.">
<meta property="og:url" content="https://alubram.at/produkte/ueberdachungen/vordach/">
<meta property="og:image" content="https://alubram.at/wp-content/themes/alubramat-child/assets/images/og-vordach.jpg">
<meta property="og:locale" content="de_AT">
```

#### Schema.org JSON-LD
```json
{
  "@context": "https://schema.org",
  "@type": "Product",
  "name": "Vordach Aluminium",
  "description": "Aluminium-Vordach als Eingangsüberdachung für Haustüren und Zugänge. Mit Glas oder Polycarbonat, wartungsfrei und wetterfest.",
  "brand": {"@type": "Brand", "name": "ALUBRAM GMBH"},
  "manufacturer": {"@id": "https://alubram.at/#organization"},
  "url": "https://alubram.at/produkte/ueberdachungen/vordach/",
  "category": "Vordach / Eingangsüberdachung",
  "offers": {
    "@type": "Offer",
    "priceCurrency": "EUR",
    "availability": "https://schema.org/InStock",
    "seller": {"@id": "https://alubram.at/#organization"}
  },
  "breadcrumb": {
    "@type": "BreadcrumbList",
    "itemListElement": [
      {"@type": "ListItem", "position": 1, "name": "Startseite", "item": "https://alubram.at/"},
      {"@type": "ListItem", "position": 2, "name": "Produkte", "item": "https://alubram.at/produkte/"},
      {"@type": "ListItem", "position": 3, "name": "Überdachungen", "item": "https://alubram.at/produkte/ueberdachungen/"},
      {"@type": "ListItem", "position": 4, "name": "Vordach", "item": "https://alubram.at/produkte/ueberdachungen/vordach/"}
    ]
  }
}
```

---

### 4.19 TERRASSENÜBERDACHUNG PREMIUM
**URL:** `/produkte/ueberdachungen/terrassenueberdachung-premium/`  
**WordPress-Template:** `single-alubram_product.php`  
**Priorität:** ⭐⭐⭐⭐⭐

#### Meta-Tags SEO
```html
<title>Terrassenüberdachung Aluminium Premium — GIGA-Rinne | ALUBRAM GMBH Österreich</title>
<meta name="description" content="Terrassenüberdachung Premium aus Aluminium mit GIGA-Rinnen: maximaler Wetterschutz, erstklassige Optik. Glas, Polycarbonat oder Blecheindeckung. Direkthersteller. Lieferzeit 3–6 Wochen.">
<meta name="robots" content="index, follow">
<link rel="canonical" href="https://alubram.at/produkte/ueberdachungen/terrassenueberdachung-premium/">
```

#### Open Graph
```html
<meta property="og:type" content="product">
<meta property="og:title" content="Terrassenüberdachung Aluminium Premium — GIGA-Rinne | ALUBRAM">
<meta property="og:description" content="Premium Terrassenüberdachung mit GIGA-Rinnen: Top-Qualität, maximaler Schutz. Direkthersteller Österreich.">
<meta property="og:url" content="https://alubram.at/produkte/ueberdachungen/terrassenueberdachung-premium/">
<meta property="og:image" content="https://alubram.at/wp-content/themes/alubramat-child/assets/images/og-terrasse-premium.jpg">
<meta property="og:locale" content="de_AT">
```

#### Schema.org JSON-LD
```json
{
  "@context": "https://schema.org",
  "@type": "Product",
  "name": "Terrassenüberdachung Aluminium Premiumklasse",
  "description": "Hochwertige Terrassenüberdachung der Premiumklasse mit GIGA-Rinnen. Eindeckungsoptionen: Glas, Polycarbonat, Blechpaneele. Wartungsfrei, langlebig, alle RAL-Farben.",
  "brand": {"@type": "Brand", "name": "ALUBRAM GMBH"},
  "manufacturer": {"@id": "https://alubram.at/#organization"},
  "url": "https://alubram.at/produkte/ueberdachungen/terrassenueberdachung-premium/",
  "category": "Terrassenüberdachung Premium",
  "additionalProperty": [
    {"@type": "PropertyValue", "name": "Klasse", "value": "Premiumklasse"},
    {"@type": "PropertyValue", "name": "Rinnen", "value": "GIGA-Rinnen"},
    {"@type": "PropertyValue", "name": "Eindeckung", "value": "Glas, Polycarbonat, Blech, Sandwichpaneel"},
    {"@type": "PropertyValue", "name": "Extras", "value": "LED, Markisen, Lamellenvorhänge"},
    {"@type": "PropertyValue", "name": "Lieferzeit", "value": "3–6 Wochen"}
  ],
  "offers": {
    "@type": "Offer",
    "priceCurrency": "EUR",
    "availability": "https://schema.org/InStock",
    "seller": {"@id": "https://alubram.at/#organization"}
  },
  "breadcrumb": {
    "@type": "BreadcrumbList",
    "itemListElement": [
      {"@type": "ListItem", "position": 1, "name": "Startseite", "item": "https://alubram.at/"},
      {"@type": "ListItem", "position": 2, "name": "Produkte", "item": "https://alubram.at/produkte/"},
      {"@type": "ListItem", "position": 3, "name": "Überdachungen", "item": "https://alubram.at/produkte/ueberdachungen/"},
      {"@type": "ListItem", "position": 4, "name": "Terrassenüberdachung Premium", "item": "https://alubram.at/produkte/ueberdachungen/terrassenueberdachung-premium/"}
    ]
  }
}
```

---

### 4.20 TERRASSENÜBERDACHUNG STANDARD
**URL:** `/produkte/ueberdachungen/terrassenueberdachung-standard/`  
**WordPress-Template:** `single-alubram_product.php`  
**Priorität:** ⭐⭐⭐⭐

#### Meta-Tags SEO
```html
<title>Terrassenüberdachung Aluminium Standard — Günstig & Hochwertig | ALUBRAM GMBH</title>
<meta name="description" content="Terrassenüberdachung Standard aus Aluminium: günstiger Einstieg, hohe Qualität. Polycarbonat oder Blecheindeckung. Alle RAL-Farben. Direkthersteller Österreich. Lieferzeit 3–6 Wochen.">
<meta name="robots" content="index, follow">
<link rel="canonical" href="https://alubram.at/produkte/ueberdachungen/terrassenueberdachung-standard/">
```

#### Open Graph
```html
<meta property="og:type" content="product">
<meta property="og:title" content="Terrassenüberdachung Standard Aluminium — Preis-Leistung | ALUBRAM">
<meta property="og:description" content="Terrassenüberdachung Standard: optimales Preis-Leistungs-Verhältnis. Aluminium, wartungsfrei. Direkthersteller AT.">
<meta property="og:url" content="https://alubram.at/produkte/ueberdachungen/terrassenueberdachung-standard/">
<meta property="og:image" content="https://alubram.at/wp-content/themes/alubramat-child/assets/images/og-terrasse-standard.jpg">
<meta property="og:locale" content="de_AT">
```

#### Schema.org JSON-LD
```json
{
  "@context": "https://schema.org",
  "@type": "Product",
  "name": "Terrassenüberdachung Aluminium Standard (Mittelklasse)",
  "description": "Terrassenüberdachung der Mittelklasse aus Aluminium. Gutes Preis-Leistungs-Verhältnis. Polycarbonat oder Blecheindeckung, wartungsfrei, alle RAL-Farben.",
  "brand": {"@type": "Brand", "name": "ALUBRAM GMBH"},
  "manufacturer": {"@id": "https://alubram.at/#organization"},
  "url": "https://alubram.at/produkte/ueberdachungen/terrassenueberdachung-standard/",
  "category": "Terrassenüberdachung Mittelklasse",
  "additionalProperty": [
    {"@type": "PropertyValue", "name": "Klasse", "value": "Mittelklasse / Standard"},
    {"@type": "PropertyValue", "name": "Eindeckung", "value": "Polycarbonat, Blech"},
    {"@type": "PropertyValue", "name": "Lieferzeit", "value": "3–6 Wochen"}
  ],
  "offers": {
    "@type": "Offer",
    "priceCurrency": "EUR",
    "availability": "https://schema.org/InStock",
    "seller": {"@id": "https://alubram.at/#organization"}
  },
  "breadcrumb": {
    "@type": "BreadcrumbList",
    "itemListElement": [
      {"@type": "ListItem", "position": 1, "name": "Startseite", "item": "https://alubram.at/"},
      {"@type": "ListItem", "position": 2, "name": "Produkte", "item": "https://alubram.at/produkte/"},
      {"@type": "ListItem", "position": 3, "name": "Überdachungen", "item": "https://alubram.at/produkte/ueberdachungen/"},
      {"@type": "ListItem", "position": 4, "name": "Terrassenüberdachung Standard", "item": "https://alubram.at/produkte/ueberdachungen/terrassenueberdachung-standard/"}
    ]
  }
}
```

---

### 4.21 BALKONE & GELÄNDER
**URL:** `/produkte/balkone-gelaender/`  
**WordPress-Template:** `single-alubram_product.php`  
**Priorität:** ⭐⭐⭐⭐

#### Meta-Tags SEO
```html
<title>Balkone & Geländer Aluminium — BOLERO 40 System | ALUBRAM GMBH Österreich</title>
<meta name="description" content="Aluminium-Balkone & Geländer: System BOLERO 40, max. Spannweite 2200mm. Mit Glas, Stäben oder Füllung. Wartungsfrei, pulverbeschichtet. Direkthersteller Österreich. Angebot anfordern!">
<meta name="robots" content="index, follow">
<link rel="canonical" href="https://alubram.at/produkte/balkone-gelaender/">
```

#### Open Graph
```html
<meta property="og:type" content="product">
<meta property="og:title" content="Balkone & Geländer aus Aluminium — BOLERO System | ALUBRAM GMBH">
<meta property="og:description" content="Aluminium-Balkone & Geländer: System BOLERO 40, bis 2200mm Spannweite. Glas, Stäbe, Füllung. Direkthersteller AT.">
<meta property="og:url" content="https://alubram.at/produkte/balkone-gelaender/">
<meta property="og:image" content="https://alubram.at/wp-content/themes/alubramat-child/assets/images/og-balkone.jpg">
<meta property="og:locale" content="de_AT">
```

#### Schema.org JSON-LD
```json
{
  "@context": "https://schema.org",
  "@type": "Product",
  "name": "Balkone & Geländer Aluminium — BOLERO 40",
  "description": "Aluminium-Balkonsysteme und Geländer BOLERO 40 mit maximaler Spannweite von 2200mm. Varianten: mit Füllung, Glas oder Stäben. Wartungsfrei, pulverbeschichtet.",
  "brand": {"@type": "Brand", "name": "ALUBRAM GMBH"},
  "manufacturer": {"@id": "https://alubram.at/#organization"},
  "url": "https://alubram.at/produkte/balkone-gelaender/",
  "category": "Balkon / Geländer",
  "additionalProperty": [
    {"@type": "PropertyValue", "name": "Systembezeichnung", "value": "BOLERO 40"},
    {"@type": "PropertyValue", "name": "Maximale Spannweite", "value": "2200 mm"},
    {"@type": "PropertyValue", "name": "Varianten", "value": "Mit Füllung, Glas, Stäbe"},
    {"@type": "PropertyValue", "name": "Lieferzeit", "value": "3–6 Wochen"}
  ],
  "offers": {
    "@type": "Offer",
    "priceCurrency": "EUR",
    "availability": "https://schema.org/InStock",
    "seller": {"@id": "https://alubram.at/#organization"}
  },
  "breadcrumb": {
    "@type": "BreadcrumbList",
    "itemListElement": [
      {"@type": "ListItem", "position": 1, "name": "Startseite", "item": "https://alubram.at/"},
      {"@type": "ListItem", "position": 2, "name": "Produkte", "item": "https://alubram.at/produkte/"},
      {"@type": "ListItem", "position": 3, "name": "Balkone & Geländer", "item": "https://alubram.at/produkte/balkone-gelaender/"}
    ]
  }
}
```

---

### 4.22 ZUBEHÖR & SONSTIGES
**URL:** `/produkte/zubehoer/`  
**WordPress-Template:** `page-zubehoer.php`  
**Priorität:** ⭐⭐

#### Meta-Tags SEO
```html
<title>Zubehör & Sonstiges — Gartenhütte, Garagentor & mehr | ALUBRAM GMBH</title>
<meta name="description" content="ALUBRAM Zubehör: Gartenhütten, Garagentore (Sektional & Kipp), Gartenmöbel, Mülltonnenboxen, Schiebetür-Sets, Schutters & Sonderzubehör. Direkthersteller Österreich.">
<meta name="robots" content="index, follow">
<link rel="canonical" href="https://alubram.at/produkte/zubehoer/">
```

#### Open Graph
```html
<meta property="og:type" content="website">
<meta property="og:title" content="Zubehör & Sonstiges — ALUBRAM GMBH Österreich">
<meta property="og:description" content="ALUBRAM Zubehör: Gartenhütten, Garagentore, Gartenmöbel, Mülltonnenboxen & mehr. Direkthersteller AT.">
<meta property="og:url" content="https://alubram.at/produkte/zubehoer/">
<meta property="og:image" content="https://alubram.at/wp-content/themes/alubramat-child/assets/images/og-zubehoer.jpg">
<meta property="og:locale" content="de_AT">
```

#### Schema.org JSON-LD
```json
{
  "@context": "https://schema.org",
  "@type": "CollectionPage",
  "url": "https://alubram.at/produkte/zubehoer/",
  "name": "Zubehör & Sonstiges — ALUBRAM GMBH",
  "description": "Ergänzende Produkte und Zubehör: Gartenhütten, Garagentore, Gartenmöbel, Mülltonnenboxen, Schiebetür-Sets.",
  "breadcrumb": {
    "@type": "BreadcrumbList",
    "itemListElement": [
      {"@type": "ListItem", "position": 1, "name": "Startseite", "item": "https://alubram.at/"},
      {"@type": "ListItem", "position": 2, "name": "Produkte", "item": "https://alubram.at/produkte/"},
      {"@type": "ListItem", "position": 3, "name": "Zubehör & Sonstiges", "item": "https://alubram.at/produkte/zubehoer/"}
    ]
  }
}
```

---

### 4.23 LEISTUNGEN
**URL:** `/leistungen/`  
**WordPress-Template:** `page-leistungen.php`  
**Priorität:** ⭐⭐⭐⭐

#### Meta-Tags SEO
```html
<title>Leistungen — Beratung, Planung, Lieferung & Montage | ALUBRAM GMBH Österreich</title>
<meta name="description" content="ALUBRAM Rundum-Service: Kostenlose Beratung → Individuelle Planung → Direktlieferung vom Hersteller → Fachgerechte Montage. Alles aus einer Hand. ✔ Fertigstellung in 6 Wochen ✔ Wien & NÖ.">
<meta name="robots" content="index, follow">
<link rel="canonical" href="https://alubram.at/leistungen/">
```

#### Open Graph
```html
<meta property="og:type" content="website">
<meta property="og:title" content="Unsere Leistungen — Komplett-Service von ALUBRAM GMBH">
<meta property="og:description" content="Von der Beratung bis zur Montage: ALUBRAM begleitet Sie durch den gesamten Prozess. Direkthersteller. Wien & NÖ.">
<meta property="og:url" content="https://alubram.at/leistungen/">
<meta property="og:image" content="https://alubram.at/wp-content/themes/alubramat-child/assets/images/og-leistungen.jpg">
<meta property="og:locale" content="de_AT">
```

#### Schema.org JSON-LD
```json
{
  "@context": "https://schema.org",
  "@type": "Service",
  "serviceType": "Aluminiumzaun Montage & Lieferung",
  "name": "ALUBRAM Komplett-Service",
  "description": "Umfassender Service von der kostenlosen Erstberatung über Planung und Direktlieferung bis zur fachgerechten Montage — alles aus einer Hand.",
  "provider": {"@id": "https://alubram.at/#organization"},
  "areaServed": [
    {"@type": "State", "name": "Wien"},
    {"@type": "State", "name": "Niederösterreich"},
    {"@type": "State", "name": "Burgenland"}
  ],
  "hasOfferCatalog": {
    "@type": "OfferCatalog",
    "name": "Leistungskatalog",
    "itemListElement": [
      {"@type": "Offer", "itemOffered": {"@type": "Service", "name": "Kostenlose Beratung"}},
      {"@type": "Offer", "itemOffered": {"@type": "Service", "name": "Individuelle Planung"}},
      {"@type": "Offer", "itemOffered": {"@type": "Service", "name": "Direktlieferung vom Hersteller"}},
      {"@type": "Offer", "itemOffered": {"@type": "Service", "name": "Fachgerechte Montage"}}
    ]
  },
  "breadcrumb": {
    "@type": "BreadcrumbList",
    "itemListElement": [
      {"@type": "ListItem", "position": 1, "name": "Startseite", "item": "https://alubram.at/"},
      {"@type": "ListItem", "position": 2, "name": "Leistungen", "item": "https://alubram.at/leistungen/"}
    ]
  }
}
```

---

### 4.24 REFERENZEN & BILDERGALERIE
**URL:** `/referenzen/`  
**WordPress-Template:** `page-referenzen.php`  
**Priorität:** ⭐⭐⭐⭐

#### Meta-Tags SEO
```html
<title>Referenzen & Bildergalerie — Realisierte Projekte | ALUBRAM GMBH Österreich</title>
<meta name="description" content="Sehen Sie unsere realisierten Projekte: Aluminiumzäune, Einfahrtstoren, Carports und Überdachungen für zufriedene Kunden in Wien, Niederösterreich & der DACH-Region. ✔ Über 1.000 Projekte.">
<meta name="robots" content="index, follow">
<link rel="canonical" href="https://alubram.at/referenzen/">
```

#### Open Graph
```html
<meta property="og:type" content="website">
<meta property="og:title" content="Referenzen & Galerie — Realisierte ALUBRAM Projekte in Österreich">
<meta property="og:description" content="Galerie realisierter Projekte: Zäune, Tore, Carports & Überdachungen. Inspirierende Beispiele aus Wien & NÖ.">
<meta property="og:url" content="https://alubram.at/referenzen/">
<meta property="og:image" content="https://alubram.at/wp-content/themes/alubramat-child/assets/images/og-referenzen.jpg">
<meta property="og:locale" content="de_AT">
```

#### Schema.org JSON-LD
```json
[
  {
    "@context": "https://schema.org",
    "@type": "CollectionPage",
    "url": "https://alubram.at/referenzen/",
    "name": "Referenzen & Bildergalerie — ALUBRAM GMBH",
    "description": "Galerie realisierter Kundenprojekte: Aluminiumzäune, Einfahrtstoren, Carports und Überdachungen.",
    "breadcrumb": {
      "@type": "BreadcrumbList",
      "itemListElement": [
        {"@type": "ListItem", "position": 1, "name": "Startseite", "item": "https://alubram.at/"},
        {"@type": "ListItem", "position": 2, "name": "Referenzen & Galerie", "item": "https://alubram.at/referenzen/"}
      ]
    }
  },
  {
    "@context": "https://schema.org",
    "@type": "AggregateRating",
    "itemReviewed": {"@id": "https://alubram.at/#organization"},
    "ratingValue": "4.9",
    "reviewCount": "120",
    "bestRating": "5",
    "worstRating": "1"
  }
]
```

---

### 4.25 AKTIONEN & ANGEBOTE
**URL:** `/aktionen/`  
**WordPress-Template:** `page-aktionen.php`  
**Priorität:** ⭐⭐⭐

#### Meta-Tags SEO
```html
<title>Aktionen & Angebote — Sonderpreise auf Aluminium-Produkte | ALUBRAM GMBH</title>
<meta name="description" content="Aktuelle ALUBRAM Aktionen: Sonderpreise auf Aluminiumzäune, Tore, Carports & Überdachungen. ✔ Lagerabverkauf ✔ Saisonangebote ✔ Direkthersteller Österreich. Jetzt informieren!">
<meta name="robots" content="index, follow">
<link rel="canonical" href="https://alubram.at/aktionen/">
```

#### Open Graph
```html
<meta property="og:type" content="website">
<meta property="og:title" content="Aktuelle Aktionen & Angebote — ALUBRAM GMBH Österreich">
<meta property="og:description" content="Sonderangebote auf Aluminiumprodukte: Zäune, Tore, Carports. Lagerabverkauf und saisonale Aktionen.">
<meta property="og:url" content="https://alubram.at/aktionen/">
<meta property="og:image" content="https://alubram.at/wp-content/themes/alubramat-child/assets/images/og-aktionen.jpg">
<meta property="og:locale" content="de_AT">
```

#### Schema.org JSON-LD
```json
{
  "@context": "https://schema.org",
  "@type": "OfferCatalog",
  "name": "ALUBRAM Aktionen & Sonderangebote",
  "description": "Aktuelle Sonderpreise und Aktionsangebote auf Aluminium-Außenprodukte von ALUBRAM GMBH.",
  "url": "https://alubram.at/aktionen/",
  "provider": {"@id": "https://alubram.at/#organization"},
  "breadcrumb": {
    "@type": "BreadcrumbList",
    "itemListElement": [
      {"@type": "ListItem", "position": 1, "name": "Startseite", "item": "https://alubram.at/"},
      {"@type": "ListItem", "position": 2, "name": "Aktionen & Angebote", "item": "https://alubram.at/aktionen/"}
    ]
  }
}
```

---

### 4.26 RATGEBER (BLOG)
**URL:** `/ratgeber/`  
**WordPress-Template:** `archive.php`  
**Priorität:** ⭐⭐⭐⭐

> **Wichtiger Hinweis:** Diese Sektion ist **NEU** — auf der aktuellen Website nicht vorhanden. Content-Marketing ist entscheidend für SEO-Sichtbarkeit!

#### Meta-Tags SEO
```html
<title>Ratgeber — Tipps rund um Aluminiumzaun, Tor & Carport | ALUBRAM GMBH Blog</title>
<meta name="description" content="ALUBRAM Ratgeber: Expertentipps zu Aluminiumzäunen, Toren, Carports & Überdachungen. ✔ Pflegehinweise ✔ Planung ✔ Montageratgeber ✔ Kaufberatung. Jetzt informieren!">
<meta name="robots" content="index, follow">
<link rel="canonical" href="https://alubram.at/ratgeber/">
```

#### Open Graph
```html
<meta property="og:type" content="website">
<meta property="og:title" content="ALUBRAM Ratgeber — Blog & Expertentipps für Aluminium-Produkte">
<meta property="og:description" content="Wissenswertes rund um Aluminiumzäune, Tore & Carports: Planung, Pflege, Montage, Kaufratgeber.">
<meta property="og:url" content="https://alubram.at/ratgeber/">
<meta property="og:image" content="https://alubram.at/wp-content/themes/alubramat-child/assets/images/og-ratgeber.jpg">
<meta property="og:locale" content="de_AT">
```

#### Schema.org JSON-LD
```json
{
  "@context": "https://schema.org",
  "@type": "Blog",
  "url": "https://alubram.at/ratgeber/",
  "name": "ALUBRAM Ratgeber",
  "description": "Expertenwissen rund um Aluminiumzäune, Tore, Carports und Überdachungen.",
  "publisher": {"@id": "https://alubram.at/#organization"},
  "inLanguage": "de-AT",
  "breadcrumb": {
    "@type": "BreadcrumbList",
    "itemListElement": [
      {"@type": "ListItem", "position": 1, "name": "Startseite", "item": "https://alubram.at/"},
      {"@type": "ListItem", "position": 2, "name": "Ratgeber", "item": "https://alubram.at/ratgeber/"}
    ]
  }
}
```

**Empfohlene Artikel-Themen für den Blog:**

| Artikel-Titel (DE) | Fokus-Keyword | Priorität |
|---|---|---|
| Aluminiumzaun kaufen: Der komplette Ratgeber 2025 | Aluminiumzaun kaufen | ⭐⭐⭐⭐⭐ |
| Aluminiumzaun vs. Stahlzaun: Was ist besser? | Aluminiumzaun oder Stahlzaun | ⭐⭐⭐⭐ |
| Carport planen: So geht's richtig | Carport planen Österreich | ⭐⭐⭐⭐ |
| Aluminiumzaun pflegen: Tipps & Tricks | Aluminiumzaun pflegen | ⭐⭐⭐ |
| Elektrisches Schiebetor einbauen: Anleitung | Schiebetor elektrisch kaufen | ⭐⭐⭐ |
| Terrassenüberdachung: Glas vs. Polycarbonat | Terrassenüberdachung Material | ⭐⭐⭐⭐ |
| Baugenehmigung für Carport in Österreich | Carport Genehmigung AT | ⭐⭐⭐ |

---

### 4.27 BLOG-EINZELARTIKEL (TEMPLATE)
**URL:** `/ratgeber/{slug}/`  
**WordPress-Template:** `single.php`  
**Priorität:** variabel (je nach Thema)

#### Meta-Tags SEO (Template — dynamisch befüllt)
```html
<!-- Dynamisch per WordPress/Yoast SEO generiert -->
<title>{Artikeltitel} | ALUBRAM GMBH Ratgeber</title>
<meta name="description" content="{Artikel-Excerpt, max. 155 Zeichen}">
<meta name="robots" content="index, follow">
<link rel="canonical" href="https://alubram.at/ratgeber/{slug}/">
<meta name="author" content="ALUBRAM GMBH Redaktion">
<meta name="article:published_time" content="{ISO 8601 Datum}">
<meta name="article:modified_time" content="{ISO 8601 Datum}">
```

#### Open Graph (Template)
```html
<meta property="og:type" content="article">
<meta property="og:title" content="{Artikeltitel}">
<meta property="og:description" content="{Artikel-Excerpt}">
<meta property="og:url" content="https://alubram.at/ratgeber/{slug}/">
<meta property="og:image" content="{Featured Image URL}">
<meta property="article:publisher" content="https://alubram.at">
<meta property="article:published_time" content="{Datum}">
<meta property="og:locale" content="de_AT">
```

#### Schema.org JSON-LD (Template)
```json
{
  "@context": "https://schema.org",
  "@type": "Article",
  "headline": "{Artikeltitel}",
  "description": "{Artikel-Excerpt}",
  "image": "{Featured Image URL}",
  "datePublished": "{ISO-Datum}",
  "dateModified": "{ISO-Datum}",
  "author": {
    "@type": "Organization",
    "name": "ALUBRAM GMBH",
    "@id": "https://alubram.at/#organization"
  },
  "publisher": {
    "@type": "Organization",
    "name": "ALUBRAM GMBH",
    "logo": {
      "@type": "ImageObject",
      "url": "https://alubram.at/wp-content/themes/alubramat-child/assets/images/logo.svg"
    }
  },
  "mainEntityOfPage": {
    "@type": "WebPage",
    "@id": "https://alubram.at/ratgeber/{slug}/"
  },
  "breadcrumb": {
    "@type": "BreadcrumbList",
    "itemListElement": [
      {"@type": "ListItem", "position": 1, "name": "Startseite", "item": "https://alubram.at/"},
      {"@type": "ListItem", "position": 2, "name": "Ratgeber", "item": "https://alubram.at/ratgeber/"},
      {"@type": "ListItem", "position": 3, "name": "{Artikeltitel}", "item": "https://alubram.at/ratgeber/{slug}/"}
    ]
  }
}
```

---

### 4.28 KONTAKT
**URL:** `/kontakt/`  
**WordPress-Template:** `page-kontakt.php`  
**Priorität:** ⭐⭐⭐⭐⭐

#### Meta-Tags SEO
```html
<title>Kontakt — Kostenlose Beratung & Angebot | ALUBRAM GMBH Himberg bei Wien</title>
<meta name="description" content="Kontaktieren Sie ALUBRAM GMBH: Kostenlose Beratung für Aluminiumzäune, Tore, Carports & Überdachungen. ☎ +43 (0) 223 584 793 | Mustergarten 24/7 | Himberg bei Wien. Jetzt Angebot anfordern!">
<meta name="robots" content="index, follow">
<link rel="canonical" href="https://alubram.at/kontakt/">
```

#### Open Graph
```html
<meta property="og:type" content="website">
<meta property="og:title" content="Kontakt — ALUBRAM GMBH | Kostenlose Beratung für Aluminium-Produkte">
<meta property="og:description" content="Jetzt kostenlos beraten lassen! ALUBRAM GMBH, Himberg bei Wien. ☎ +43 223 584 793. Mustergarten 24/7.">
<meta property="og:url" content="https://alubram.at/kontakt/">
<meta property="og:image" content="https://alubram.at/wp-content/themes/alubramat-child/assets/images/og-kontakt.jpg">
<meta property="og:locale" content="de_AT">
```

#### Schema.org JSON-LD
```json
[
  {
    "@context": "https://schema.org",
    "@type": "ContactPage",
    "url": "https://alubram.at/kontakt/",
    "name": "Kontakt — ALUBRAM GMBH",
    "description": "Kontaktseite für ALUBRAM GMBH: kostenlose Beratung, Angebote, Standortinformationen.",
    "breadcrumb": {
      "@type": "BreadcrumbList",
      "itemListElement": [
        {"@type": "ListItem", "position": 1, "name": "Startseite", "item": "https://alubram.at/"},
        {"@type": "ListItem", "position": 2, "name": "Kontakt", "item": "https://alubram.at/kontakt/"}
      ]
    }
  },
  {
    "@context": "https://schema.org",
    "@type": "LocalBusiness",
    "@id": "https://alubram.at/#organization",
    "name": "ALUBRAM GMBH",
    "address": {
      "@type": "PostalAddress",
      "streetAddress": "Hintere Ortsstraße 31",
      "addressLocality": "Himberg bei Wien",
      "addressRegion": "Niederösterreich",
      "postalCode": "2325",
      "addressCountry": "AT"
    },
    "telephone": "+43223584793",
    "email": "himberg@alubram.at",
    "openingHoursSpecification": [
      {
        "@type": "OpeningHoursSpecification",
        "dayOfWeek": ["Monday", "Tuesday", "Thursday", "Friday"],
        "opens": "07:00",
        "closes": "17:00"
      },
      {
        "@type": "OpeningHoursSpecification",
        "dayOfWeek": "Wednesday",
        "opens": "07:00",
        "closes": "19:00"
      },
      {
        "@type": "OpeningHoursSpecification",
        "dayOfWeek": "Saturday",
        "opens": "08:00",
        "closes": "13:00"
      }
    ],
    "geo": {
      "@type": "GeoCoordinates",
      "latitude": 48.0833,
      "longitude": 16.4500
    }
  },
  {
    "@context": "https://schema.org",
    "@type": "FAQPage",
    "mainEntity": [
      {
        "@type": "Question",
        "name": "Wie lange dauert die Lieferung eines Aluminiumzauns?",
        "acceptedAnswer": {
          "@type": "Answer",
          "text": "ALUBRAM GMBH garantiert die Lieferung aller Produkte in 3–6 Wochen ab Auftragsbestätigung."
        }
      },
      {
        "@type": "Question",
        "name": "Bieten Sie auch Montage an?",
        "acceptedAnswer": {
          "@type": "Answer",
          "text": "Ja, ALUBRAM bietet einen vollständigen Montageservice an. Die Fertigstellung erfolgt innerhalb von 6 Wochen."
        }
      },
      {
        "@type": "Question",
        "name": "Kann ich die Produkte vor dem Kauf besichtigen?",
        "acceptedAnswer": {
          "@type": "Answer",
          "text": "Ja! Unser Mustergarten in Himberg bei Wien ist 24 Stunden, 7 Tage die Woche geöffnet."
        }
      },
      {
        "@type": "Question",
        "name": "In welchen Farben sind Ihre Aluminium-Produkte erhältlich?",
        "acceptedAnswer": {
          "@type": "Answer",
          "text": "Alle ALUBRAM Produkte sind in beliebigen RAL-Farben erhältlich. Zusätzlich bieten wir Holzoptik-Designs (Thermoprint) an."
        }
      },
      {
        "@type": "Question",
        "name": "Wohin liefern Sie Ihre Produkte?",
        "acceptedAnswer": {
          "@type": "Answer",
          "text": "ALUBRAM liefert in ganz Österreich (Schwerpunkt Wien, Niederösterreich, Burgenland) sowie auf Anfrage nach Deutschland und in die Schweiz."
        }
      }
    ]
  }
]
```

---

### 4.29 STANDORTE
**URL:** `/kontakt/standorte/`  
**WordPress-Template:** `page-standorte.php`  
**Priorität:** ⭐⭐⭐

#### Meta-Tags SEO
```html
<title>Standorte — ALUBRAM GMBH | Wien, Deutsch-Wagram & Gloggnitz</title>
<meta name="description" content="ALUBRAM GMBH mit 3 Standorten: Himberg bei Wien (Zentrale + Mustergarten 24/7), Deutsch-Wagram (Showroom) und Gloggnitz (Showroom). Besuchen Sie uns — Beratung vor Ort!">
<meta name="robots" content="index, follow">
<link rel="canonical" href="https://alubram.at/kontakt/standorte/">
```

#### Open Graph
```html
<meta property="og:type" content="website">
<meta property="og:title" content="ALUBRAM Standorte — Himberg, Deutsch-Wagram & Gloggnitz">
<meta property="og:description" content="3 Standorte in Niederösterreich: Zentrale Himberg, Showrooms in Deutsch-Wagram & Gloggnitz. Persönliche Beratung vor Ort.">
<meta property="og:url" content="https://alubram.at/kontakt/standorte/">
<meta property="og:image" content="https://alubram.at/wp-content/themes/alubramat-child/assets/images/og-standorte.jpg">
<meta property="og:locale" content="de_AT">
```

#### Schema.org JSON-LD
```json
{
  "@context": "https://schema.org",
  "@type": "ItemList",
  "name": "ALUBRAM GMBH Standorte",
  "itemListElement": [
    {
      "@type": "ListItem",
      "position": 1,
      "item": {
        "@type": "LocalBusiness",
        "name": "ALUBRAM GMBH — Zentrale & Mustergarten",
        "address": {
          "@type": "PostalAddress",
          "streetAddress": "Hintere Ortsstraße 31",
          "addressLocality": "Himberg bei Wien",
          "postalCode": "2325",
          "addressCountry": "AT"
        },
        "telephone": "+43223584793",
        "email": "himberg@alubram.at",
        "description": "Hauptstandort mit Produktion, Lager und 24/7 Mustergarten"
      }
    },
    {
      "@type": "ListItem",
      "position": 2,
      "item": {
        "@type": "LocalBusiness",
        "name": "ALUBRAM GMBH — Showroom Deutsch-Wagram",
        "address": {
          "@type": "PostalAddress",
          "streetAddress": "Bockfließerstraße 3",
          "addressLocality": "Deutsch-Wagram",
          "postalCode": "2232",
          "addressCountry": "AT"
        },
        "telephone": "+436644373965",
        "email": "deutsch-wagram@alubram.at"
      }
    },
    {
      "@type": "ListItem",
      "position": 3,
      "item": {
        "@type": "LocalBusiness",
        "name": "ALUBRAM GMBH — Showroom Gloggnitz",
        "address": {
          "@type": "PostalAddress",
          "streetAddress": "Wienerstraße 15A",
          "addressLocality": "Gloggnitz",
          "postalCode": "2640",
          "addressCountry": "AT"
        },
        "telephone": "+436644373975",
        "email": "gloggnitz@alubram.at"
      }
    }
  ]
}
```

---

### 4.30 KARRIERE / WIR SUCHEN
**URL:** `/karriere/`  
**WordPress-Template:** `page-karriere.php`  
**Priorität:** ⭐⭐ (Footer-Navigation)

> **Hinweis:** Dieser Punkt wird von der Hauptnavigation in die **Footer-Navigation** verschoben — Conversions haben Vorrang.

#### Meta-Tags SEO
```html
<title>Karriere bei ALUBRAM GMBH — Jetzt bewerben | Himberg bei Wien</title>
<meta name="description" content="Werden Sie Teil des ALUBRAM Teams! Wir suchen engagierte Mitarbeiter für Montage, Vertrieb & Beratung in Himberg bei Wien & Niederösterreich. Jetzt Bewerbung einsenden!">
<meta name="robots" content="index, follow">
<link rel="canonical" href="https://alubram.at/karriere/">
```

#### Open Graph
```html
<meta property="og:type" content="website">
<meta property="og:title" content="Karriere bei ALUBRAM GMBH — Jobs in Himberg bei Wien">
<meta property="og:description" content="ALUBRAM wächst! Offene Stellen im Bereich Montage, Vertrieb & Beratung. Jetzt bewerben.">
<meta property="og:url" content="https://alubram.at/karriere/">
<meta property="og:image" content="https://alubram.at/wp-content/themes/alubramat-child/assets/images/og-karriere.jpg">
<meta property="og:locale" content="de_AT">
```

#### Schema.org JSON-LD
```json
{
  "@context": "https://schema.org",
  "@type": "JobPosting",
  "hiringOrganization": {"@id": "https://alubram.at/#organization"},
  "jobLocation": {
    "@type": "Place",
    "address": {
      "@type": "PostalAddress",
      "addressLocality": "Himberg bei Wien",
      "addressCountry": "AT"
    }
  },
  "employmentType": "FULL_TIME",
  "breadcrumb": {
    "@type": "BreadcrumbList",
    "itemListElement": [
      {"@type": "ListItem", "position": 1, "name": "Startseite", "item": "https://alubram.at/"},
      {"@type": "ListItem", "position": 2, "name": "Karriere", "item": "https://alubram.at/karriere/"}
    ]
  }
}
```

---

### 4.31 KATALOG & DOWNLOADS
**URL:** `/katalog/`  
**WordPress-Template:** `page-katalog.php`  
**Priorität:** ⭐⭐⭐

#### Meta-Tags SEO
```html
<title>Katalog & Downloads — ALUBRAM GMBH Produktkatalog PDF</title>
<meta name="description" content="Laden Sie den aktuellen ALUBRAM Produktkatalog als PDF herunter: Aluminiumzäune, Tore, Carports & Überdachungen mit technischen Daten, Maßzeichnungen und Farbkarten.">
<meta name="robots" content="index, follow">
<link rel="canonical" href="https://alubram.at/katalog/">
```

#### Open Graph
```html
<meta property="og:type" content="website">
<meta property="og:title" content="ALUBRAM Produktkatalog — Kostenloser PDF-Download">
<meta property="og:description" content="Alle ALUBRAM Produkte im Katalog: technische Daten, Maßzeichnungen, Farbkarten. PDF-Download kostenlos.">
<meta property="og:url" content="https://alubram.at/katalog/">
<meta property="og:image" content="https://alubram.at/wp-content/themes/alubramat-child/assets/images/og-katalog.jpg">
<meta property="og:locale" content="de_AT">
```

#### Schema.org JSON-LD
```json
{
  "@context": "https://schema.org",
  "@type": "WebPage",
  "url": "https://alubram.at/katalog/",
  "name": "Katalog & Downloads — ALUBRAM GMBH",
  "description": "ALUBRAM Produktkatalog als PDF-Download: vollständige technische Dokumentation.",
  "breadcrumb": {
    "@type": "BreadcrumbList",
    "itemListElement": [
      {"@type": "ListItem", "position": 1, "name": "Startseite", "item": "https://alubram.at/"},
      {"@type": "ListItem", "position": 2, "name": "Katalog & Downloads", "item": "https://alubram.at/katalog/"}
    ]
  }
}
```

---

### 4.32 IMPRESSUM
**URL:** `/impressum/`  
**WordPress-Template:** `page.php`  
**Priorität:** ⭐ (Pflichtseite)

#### Meta-Tags SEO
```html
<title>Impressum — ALUBRAM GMBH | Angaben gemäß ECG & UGB Österreich</title>
<meta name="description" content="Impressum der ALUBRAM GMBH: Firmenbuchnummer FN 535870 w, UID ATU75724307, Himberg bei Wien, Österreich. Angaben gemäß österreichischem E-Commerce-Gesetz (ECG).">
<meta name="robots" content="noindex, follow">
<link rel="canonical" href="https://alubram.at/impressum/">
```

#### Open Graph
```html
<meta property="og:type" content="website">
<meta property="og:title" content="Impressum — ALUBRAM GMBH">
<meta property="og:url" content="https://alubram.at/impressum/">
<meta property="og:locale" content="de_AT">
```

> **Hinweis:** Impressum wird von Suchmaschinen mit `noindex` ausgezeichnet — kein JSON-LD erforderlich.

---

### 4.33 DATENSCHUTZERKLÄRUNG
**URL:** `/datenschutzerklaerung/`  
**WordPress-Template:** `page.php`  
**Priorität:** ⭐ (DSGVO-Pflichtseite)

#### Meta-Tags SEO
```html
<title>Datenschutzerklärung — ALUBRAM GMBH | DSGVO-konform</title>
<meta name="description" content="Datenschutzerklärung der ALUBRAM GMBH gemäß DSGVO und österreichischem Datenschutzgesetz (DSG). Informationen zur Verarbeitung personenbezogener Daten.">
<meta name="robots" content="noindex, follow">
<link rel="canonical" href="https://alubram.at/datenschutzerklaerung/">
```

#### Open Graph
```html
<meta property="og:type" content="website">
<meta property="og:title" content="Datenschutzerklärung — ALUBRAM GMBH">
<meta property="og:url" content="https://alubram.at/datenschutzerklaerung/">
<meta property="og:locale" content="de_AT">
```

> **Hinweis:** `noindex` — kein Schema.org JSON-LD erforderlich.

---

### 4.34 AGB (ALLGEMEINE GESCHÄFTSBEDINGUNGEN)
**URL:** `/agb/`  
**WordPress-Template:** `page.php`  
**Priorität:** ⭐ (Pflichtseite)

#### Meta-Tags SEO
```html
<title>AGB — Allgemeine Geschäftsbedingungen | ALUBRAM GMBH Österreich</title>
<meta name="description" content="Allgemeine Geschäftsbedingungen (AGB) der ALUBRAM GMBH für den Kauf und die Montage von Aluminium-Außenprodukten in Österreich.">
<meta name="robots" content="noindex, follow">
<link rel="canonical" href="https://alubram.at/agb/">
```

#### Open Graph
```html
<meta property="og:type" content="website">
<meta property="og:title" content="AGB — ALUBRAM GMBH">
<meta property="og:url" content="https://alubram.at/agb/">
<meta property="og:locale" content="de_AT">
```

---

### 4.35 LOKALE LANDINGPAGES (SEO)

> **Strategische Seiten für lokale Suchbegriffe** — hohe Conversion-Relevanz!

---

#### 4.35.1 ALUMINIUMZAUN WIEN
**URL:** `/aluminiumzaun-wien/`  
**WordPress-Template:** `page.php` (custom landing page)  
**Priorität:** ⭐⭐⭐⭐⭐

##### Meta-Tags SEO
```html
<title>Aluminiumzaun Wien — Zaunanlage direkt vom Hersteller | ALUBRAM GMBH</title>
<meta name="description" content="Aluminiumzaun Wien: ALUBRAM GMBH — Ihr lokaler Hersteller & Monteur in Wien und Umgebung. ✔ Lieferung 3–6 Wochen ✔ Montage inkl. ✔ Alle RAL-Farben ✔ Mustergarten 24/7. Jetzt beraten lassen!">
<meta name="robots" content="index, follow">
<link rel="canonical" href="https://alubram.at/aluminiumzaun-wien/">
```

##### Open Graph
```html
<meta property="og:type" content="website">
<meta property="og:title" content="Aluminiumzaun Wien — ALUBRAM GMBH Direkthersteller">
<meta property="og:description" content="Aluminiumzaun für Wien: Lieferung & Montage 3–6 Wochen. Direkthersteller. Mustergarten 24/7.">
<meta property="og:url" content="https://alubram.at/aluminiumzaun-wien/">
<meta property="og:image" content="https://alubram.at/wp-content/themes/alubramat-child/assets/images/og-wien.jpg">
<meta property="og:locale" content="de_AT">
```

##### Schema.org JSON-LD
```json
{
  "@context": "https://schema.org",
  "@type": "Service",
  "name": "Aluminiumzaun Wien — Lieferung & Montage",
  "description": "ALUBRAM GMBH liefert und montiert hochwertige Aluminiumzäune in Wien und Umgebung. Direkthersteller mit Mustergarten in Himberg bei Wien.",
  "provider": {"@id": "https://alubram.at/#organization"},
  "areaServed": {"@type": "City", "name": "Wien"},
  "serviceType": "Aluminiumzaun Lieferung und Montage",
  "breadcrumb": {
    "@type": "BreadcrumbList",
    "itemListElement": [
      {"@type": "ListItem", "position": 1, "name": "Startseite", "item": "https://alubram.at/"},
      {"@type": "ListItem", "position": 2, "name": "Aluminiumzaun Wien", "item": "https://alubram.at/aluminiumzaun-wien/"}
    ]
  }
}
```

---

#### 4.35.2 ALUMINIUMZAUN NIEDERÖSTERREICH
**URL:** `/aluminiumzaun-niederoesterreich/`  
**Priorität:** ⭐⭐⭐⭐

##### Meta-Tags SEO
```html
<title>Aluminiumzaun Niederösterreich — Hersteller & Monteur | ALUBRAM GMBH</title>
<meta name="description" content="Aluminiumzaun Niederösterreich: ALUBRAM mit 3 Standorten in NÖ — Ihr regionaler Hersteller. ✔ Himberg, Deutsch-Wagram, Gloggnitz ✔ Montage NÖ ✔ Lieferzeit 3–6 Wochen. Angebot anfordern!">
<meta name="robots" content="index, follow">
<link rel="canonical" href="https://alubram.at/aluminiumzaun-niederoesterreich/">
```

##### Open Graph
```html
<meta property="og:type" content="website">
<meta property="og:title" content="Aluminiumzaun Niederösterreich — ALUBRAM GMBH Regionale Präsenz">
<meta property="og:description" content="ALUBRAM: Aluminiumzaun-Hersteller mit 3 Standorten in NÖ. Lieferung & Montage in ganz Niederösterreich.">
<meta property="og:url" content="https://alubram.at/aluminiumzaun-niederoesterreich/">
<meta property="og:image" content="https://alubram.at/wp-content/themes/alubramat-child/assets/images/og-niederoesterreich.jpg">
<meta property="og:locale" content="de_AT">
```

##### Schema.org JSON-LD
```json
{
  "@context": "https://schema.org",
  "@type": "Service",
  "name": "Aluminiumzaun Niederösterreich",
  "description": "ALUBRAM GMBH — Ihr Hersteller für Aluminiumzäune in ganz Niederösterreich. Drei Showroom-Standorte: Himberg, Deutsch-Wagram, Gloggnitz.",
  "provider": {"@id": "https://alubram.at/#organization"},
  "areaServed": {"@type": "State", "name": "Niederösterreich"},
  "breadcrumb": {
    "@type": "BreadcrumbList",
    "itemListElement": [
      {"@type": "ListItem", "position": 1, "name": "Startseite", "item": "https://alubram.at/"},
      {"@type": "ListItem", "position": 2, "name": "Aluminiumzaun Niederösterreich", "item": "https://alubram.at/aluminiumzaun-niederoesterreich/"}
    ]
  }
}
```

---

#### 4.35.3 CARPORT WIEN KAUFEN
**URL:** `/carport-wien/`  
**Priorität:** ⭐⭐⭐⭐

##### Meta-Tags SEO
```html
<title>Carport Wien kaufen — Aluminium-Carport Hersteller | ALUBRAM GMBH</title>
<meta name="description" content="Carport Wien: Aluminium-Carport direkt vom Hersteller kaufen. ✔ Freistehend ✔ Maßanfertigung ✔ Lieferzeit 3–6 Wochen ✔ Montage inkl. ✔ Alle RAL-Farben. Jetzt Angebot anfordern!">
<meta name="robots" content="index, follow">
<link rel="canonical" href="https://alubram.at/carport-wien/">
```

##### Open Graph
```html
<meta property="og:type" content="website">
<meta property="og:title" content="Carport Wien kaufen — Aluminium Direkthersteller | ALUBRAM GMBH">
<meta property="og:description" content="Carport für Wien: Aluminium-Carport vom Hersteller. Maßanfertigung, schnelle Lieferung, Montage inklusive.">
<meta property="og:url" content="https://alubram.at/carport-wien/">
<meta property="og:image" content="https://alubram.at/wp-content/themes/alubramat-child/assets/images/og-carport-wien.jpg">
<meta property="og:locale" content="de_AT">
```

##### Schema.org JSON-LD
```json
{
  "@context": "https://schema.org",
  "@type": "Service",
  "name": "Carport Wien — Aluminium Carport kaufen",
  "description": "ALUBRAM GMBH liefert und montiert Aluminium-Carports in Wien. Direkthersteller, Lieferung 3–6 Wochen.",
  "provider": {"@id": "https://alubram.at/#organization"},
  "areaServed": {"@type": "City", "name": "Wien"},
  "serviceType": "Carport Lieferung und Montage",
  "breadcrumb": {
    "@type": "BreadcrumbList",
    "itemListElement": [
      {"@type": "ListItem", "position": 1, "name": "Startseite", "item": "https://alubram.at/"},
      {"@type": "ListItem", "position": 2, "name": "Carport Wien kaufen", "item": "https://alubram.at/carport-wien/"}
    ]
  }
}
```

---

## 5. ZUSAMMENFASSUNG DER SEO-STRATEGIE

### 5.1 Vollständige Seitenübersicht

| # | Seitenname | URL | Template | SEO-Priorität | robots |
|---|---|---|---|---|---|
| 1 | Startseite | `/` | `front-page.php` | ⭐⭐⭐⭐⭐ | index |
| 2 | Über uns | `/uber-uns/` | `page-uber-uns.php` | ⭐⭐⭐⭐ | index |
| 3 | Produkte — Übersicht | `/produkte/` | `page-produkte.php` | ⭐⭐⭐⭐⭐ | index |
| 4 | Zäune — Kategorie | `/produkte/zaune/` | `page-zaune.php` | ⭐⭐⭐⭐⭐ | index |
| 5 | Horizontal Zaun | `/produkte/zaune/horizontal-zaun/` | `single-alubram_product.php` | ⭐⭐⭐⭐⭐ | index |
| 6 | Vertikal Zaun | `/produkte/zaune/vertikal-zaun/` | `single-alubram_product.php` | ⭐⭐⭐⭐ | index |
| 7 | Klassischer Zaun | `/produkte/zaune/klassischer-zaun/` | `single-alubram_product.php` | ⭐⭐⭐ | index |
| 8 | Blickdichter Zaun | `/produkte/zaune/blickdichter-zaun/` | `single-alubram_product.php` | ⭐⭐⭐⭐ | index |
| 9 | Industrie Zaun | `/produkte/zaune/industrie-zaun/` | `single-alubram_product.php` | ⭐⭐⭐ | index |
| 10 | Sondermodell Zaun | `/produkte/zaune/sondermodell/` | `single-alubram_product.php` | ⭐⭐⭐ | index |
| 11 | Tore — Kategorie | `/produkte/tore/` | `page-tore.php` | ⭐⭐⭐⭐⭐ | index |
| 12 | Schiebetor | `/produkte/tore/schiebetor/` | `single-alubram_product.php` | ⭐⭐⭐⭐⭐ | index |
| 13 | Flügeltor & Einfahrtstor | `/produkte/tore/fluegeltor/` | `single-alubram_product.php` | ⭐⭐⭐⭐ | index |
| 14 | Eingangstor / Gehtor | `/produkte/tore/eingangstor/` | `single-alubram_product.php` | ⭐⭐⭐⭐ | index |
| 15 | Carports | `/produkte/carports/` | `single-alubram_product.php` | ⭐⭐⭐⭐⭐ | index |
| 16 | Überdachungen — Kategorie | `/produkte/ueberdachungen/` | `page-ueberdachungen.php` | ⭐⭐⭐⭐⭐ | index |
| 17 | Pergola | `/produkte/ueberdachungen/pergola/` | `single-alubram_product.php` | ⭐⭐⭐⭐ | index |
| 18 | Vordach | `/produkte/ueberdachungen/vordach/` | `single-alubram_product.php` | ⭐⭐⭐ | index |
| 19 | Terrassenüberdeckung Premium | `/produkte/ueberdachungen/terrassenueberdachung-premium/` | `single-alubram_product.php` | ⭐⭐⭐⭐⭐ | index |
| 20 | Terrassenüberdachung Standard | `/produkte/ueberdachungen/terrassenueberdachung-standard/` | `single-alubram_product.php` | ⭐⭐⭐⭐ | index |
| 21 | Balkone & Geländer | `/produkte/balkone-gelaender/` | `single-alubram_product.php` | ⭐⭐⭐⭐ | index |
| 22 | Zubehör & Sonstiges | `/produkte/zubehoer/` | `page-zubehoer.php` | ⭐⭐ | index |
| 23 | Leistungen | `/leistungen/` | `page-leistungen.php` | ⭐⭐⭐⭐ | index |
| 24 | Referenzen & Galerie | `/referenzen/` | `page-referenzen.php` | ⭐⭐⭐⭐ | index |
| 25 | Aktionen & Angebote | `/aktionen/` | `page-aktionen.php` | ⭐⭐⭐ | index |
| 26 | Ratgeber (Blog) | `/ratgeber/` | `archive.php` | ⭐⭐⭐⭐ | index |
| 27 | Blog-Artikel (Template) | `/ratgeber/{slug}/` | `single.php` | variabel | index |
| 28 | Kontakt | `/kontakt/` | `page-kontakt.php` | ⭐⭐⭐⭐⭐ | index |
| 29 | Standorte | `/kontakt/standorte/` | `page-standorte.php` | ⭐⭐⭐ | index |
| 30 | Karriere | `/karriere/` | `page-karriere.php` | ⭐⭐ | index |
| 31 | Katalog & Downloads | `/katalog/` | `page-katalog.php` | ⭐⭐⭐ | index |
| 32 | Impressum | `/impressum/` | `page.php` | — | **noindex** |
| 33 | Datenschutzerklärung | `/datenschutzerklaerung/` | `page.php` | — | **noindex** |
| 34 | AGB | `/agb/` | `page.php` | — | **noindex** |
| 35 | Aluminiumzaun Wien (LP) | `/aluminiumzaun-wien/` | `page.php` | ⭐⭐⭐⭐⭐ | index |
| 36 | Aluminiumzaun NÖ (LP) | `/aluminiumzaun-niederoesterreich/` | `page.php` | ⭐⭐⭐⭐ | index |
| 37 | Carport Wien (LP) | `/carport-wien/` | `page.php` | ⭐⭐⭐⭐ | index |

**Gesamt: 37 Seiten** (inkl. 3 lokale SEO-Landingpages)

---

### 5.2 Fokus-Keywords pro Seite (Übersicht)

| Seite | Primäres Keyword | Suchvolumen (AT+DE) |
|---|---|---|
| Startseite | Aluminiumzaun Hersteller Österreich | hoch |
| Zäune Kategorie | Aluminiumzaun kaufen | sehr hoch |
| Horizontal Zaun | Horizontaler Aluminiumzaun | mittel |
| Blickdichter Zaun | Sichtschutzzaun Aluminium | mittel-hoch |
| Tore Kategorie | Einfahrtstor Aluminium | hoch |
| Schiebetor | Schiebetor kaufen Aluminium | hoch |
| Carports | Carport Aluminium kaufen Wien | mittel-hoch |
| Überdachungen | Terrassenüberdachung Aluminium | sehr hoch |
| Pergola | Pergola Aluminium kaufen | hoch |
| Kontakt | Aluminiumzaun Beratung Wien | mittel |
| Wien-LP | Aluminiumzaun Wien | hoch |

---

### 5.3 Technische SEO-Checkliste

```
✅ Alle Seiten: <title> max. 60 Zeichen
✅ Alle Seiten: <meta description> max. 155 Zeichen
✅ Alle Seiten: Canonical URL gesetzt
✅ Alle Seiten: Open Graph vollständig (og:title, og:description, og:image, og:url)
✅ Alle Seiten: Breadcrumb-Navigation (außer Homepage)
✅ Alle Seiten: BreadcrumbList JSON-LD
✅ Produktseiten: Product Schema.org JSON-LD
✅ Startseite: LocalBusiness + Organization JSON-LD
✅ Kontakt: FAQPage JSON-LD
✅ Blog: Article JSON-LD Template
✅ Leistungen: Service JSON-LD
✅ Lokale LPs: Service + areaServed JSON-LD
✅ Impressum/DSE/AGB: noindex
✅ Alle Seiten: og:locale = de_AT
✅ Alle Seiten: hreflang de-AT gesetzt
✅ Alle Bilder: descriptive alt-text auf Deutsch
✅ Alle Bilder: loading="lazy" + decoding="async"
✅ Alle Links: keine broken links
✅ Alle Seiten: HTTPS / Canonical korrekt
```

---

### 5.4 Empfohlene WordPress-Plugins für SEO

| Plugin | Funktion | Priorität |
|---|---|---|
| **Yoast SEO Premium** oder **RankMath Pro** | Meta-Tags, XML-Sitemap, Schema.org | ⭐⭐⭐⭐⭐ |
| **WP Rocket** | Caching, Performance, Core Web Vitals | ⭐⭐⭐⭐⭐ |
| **Imagify** oder **ShortPixel** | Bild-Komprimierung + .avif/.webp Konvertierung | ⭐⭐⭐⭐⭐ |
| **Borlabs Cookie** | DSGVO Cookie Consent Banner | ⭐⭐⭐⭐⭐ |
| **ACF Pro** | Custom Fields für Produktseiten | ⭐⭐⭐⭐⭐ |
| **Contact Form 7** | Kontaktformular + AJAX | ⭐⭐⭐⭐ |
| **Google Site Kit** | Analytics, Search Console Integration | ⭐⭐⭐⭐ |
| **Redirection** | URL-Weiterleitungen (301) für alte URLs | ⭐⭐⭐⭐ |

---

### 5.5 URL-Weiterleitungen (301 Redirects) — Alte → Neue URLs

> **Wichtig:** Nach dem Launch der neuen Website müssen folgende Redirects eingerichtet werden, um bestehende Backlinks und PageRank zu erhalten:

```
301: /horizontal-zaun/        → /produkte/zaune/horizontal-zaun/
301: /vertikal-zaun/          → /produkte/zaune/vertikal-zaun/
301: /klassischer-zaun/       → /produkte/zaune/klassischer-zaun/
301: /blickdichter-zaun/      → /produkte/zaune/blickdichter-zaun/
301: /industrie-zaun/         → /produkte/zaune/industrie-zaun/
301: /industrie-zaun          → /produkte/zaune/industrie-zaun/
301: /sonder-modell/          → /produkte/zaune/sondermodell/
301: /pergola/                → /produkte/ueberdachungen/pergola/
301: /vordach/                → /produkte/ueberdachungen/vordach/
301: /carport/                → /produkte/carports/
301: /terrassenueberdachung-premiumklasse/  → /produkte/ueberdachungen/terrassenueberdachung-premium/
301: /terrassenuberdachung-mittelklasse/    → /produkte/ueberdachungen/terrassenueberdachung-standard/
301: /balkone/                → /produkte/balkone-gelaender/
301: /gelaender/              → /produkte/balkone-gelaender/
301: /gartenhutte/            → /produkte/zubehoer/
301: /gartenmobel/            → /produkte/zubehoer/
301: /garagentor/             → /produkte/zubehoer/
301: /bildergalerie/          → /referenzen/
301: /warum-wir/              → /leistungen/
301: /angebot/                → /kontakt/
301: /wir-suchen/             → /karriere/
301: /sonder/                 → /produkte/ueberdachungen/
301: /sonder-zubehor/         → /produkte/zubehoer/
```

---

*Dokument erstellt von: Senior WordPress Developer & SEO-Stratege*  
*Projekt: ALUBRAM GMBH — Neue Premium-Website 2025/2026*  
*Alle SEO-Spezifikationen basieren auf aktuellen Google-Richtlinien, Schema.org v26, Open Graph Protocol v1.1*  
*DSGVO-konform: Alle Metadaten entsprechen der österreichischen und EU-Datenschutzgesetzgebung*

---

**© 2026 ALUBRAM GMBH — Vertrauliches Strategiedokument**
