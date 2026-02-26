# README.md — ALUBRAM GMBH WordPress Project

> **Projekt:** Strona internetowa ALUBRAM GMBH na WordPress
> **Klient:** ALUBRAM GMBH — Himberg bei Wien, Austria
> **Repozytorium:** https://github.com/piotroq/alubram-gmbh-wordpress
> **Wersja:** 1.0.0 | 2026-02-26

---

## 🏢 O Projekcie

**ALUBRAM GMBH** to austriacki producent premium aluminiowych ogrodzeń, bram, wiat garażowych (Carport) oraz zadaszeń. Projekt polega na stworzeniu nowoczesnej, szybkiej strony internetowej w języku niemieckim na CMS WordPress.

### Cele Projektu

- ✅ **Brand Positioning** — Pozycjonowanie jako premium manufacturer na rynku DACH
- ✅ **Lead Generation** — Generowanie leadów poprzez formularze kontaktowe
- ✅ **Product Showcase** — Prezentacja produktów z galeriami i specyfikacjami
- ✅ **SEO Visibility** — Top 3 rankings dla 20+ keywords
- ✅ **Performance** — PageSpeed ≥ 90 mobile, ≥ 95 desktop

### Informacje o Firmie

| Pole | Wartość |
|------|---------|
| **Nazwa** | ALUBRAM GMBH |
| **Branża** | Producent aluminiowych ogrodzeń, bram, Carport, zadaszeń |
| **Rynek** | DACH (Austria, Niemcy, Szwajcaria) |
| **Język** | Deutsch (de_AT) |
| **Siedziba** | Hintere Ortsstraße 31, 2325 Himberg bei Wien, Austria |
| **Kontakt** | +43 (0) 223 584 793 \| himberg@alubram.at |
| **Strona** | https://alubram.at |

### USP (Unique Selling Propositions)

```
✓ Direkt vom Hersteller — kein Zwischenhändler
✓ Lieferung in 3–6 Wochen garantiert
✓ 24 Stunden · 7 Tage erreichbar
✓ Alles aus einer Hand: Beratung → Planung → Lieferung → Montage
✓ Aluminium: rostfrei · wartungsfrei · witterungsbeständig
✓ Pulverbeschichtet — jahrzehntelange Haltbarkeit
```

---

## 🛠️ Stack Technologiczny

| Komponent | Technologia | Wersja |
|-----------|-------------|--------|
| **CMS** | WordPress | 6.9+ |
| **PHP** | PHP | 8.2+ |
| **Database** | MySQL / MariaDB | 8.0 / 10.6+ |
| **Frontend** | TypeScript, JavaScript | ES6+ |
| **CSS** | Tailwind CSS | 3.4+ |
| **Animations** | AOS | 2.3.4 |
| **Sliders** | Swiper.js | 11.x |
| **Icons** | Material Design Icons | Latest |

### Wymagane Pluginy

- **Yoast SEO** — SEO optimization
- **Contact Form 7** — Contact forms
- **WP Rocket** — Caching, performance
- **Imagify** — Image optimization
- **Borlabs Cookie** — DSGVO compliance
- **Advanced Custom Fields Pro** — Custom fields
- **Classic Editor** — Classic editor support

---

## 📁 Struktura Repozytorium

```
alubram-gmbh-wordpress/
│
├── .claude/                          ← Claude AI configuration
├── .qwen/                            ← Qwen AI configuration
├── .github/                          ← GitHub workflows
│
├── docs/                             ← Documentation
│   ├── ARCHITECTURE.md
│   ├── BRAND-SETTINGS.md
│   ├── DESIGN-SYSTEM.md
│   └── ...
│
├── src/
│   └── wp-content/
│       └── themes/
│           ├── alubramat/            ← Parent theme
│           └── alubramat-child/      ← Child theme (ACTIVE)
│
├── CLAUDE.md                         ← Claude AI instructions
├── QWEN.md                           ← Qwen AI instructions
├── OLLAMA.md                         ← Ollama local AI config
├── CONTRIBUTING.md                   ← Contribution guidelines
├── PROJECT-SPECIFICATION.md          ← Project specs
├── PAGES-WIREFRAMES.md               ← Pages wireframes
├── ROADMAP.SCHEMA.md                 ← Roadmap schema
├── TECHNICAL-SHEETS.md               ← Master instructions
└── README.md                         ← This file
```

---

## 🚀 Quick Start

### Wymagania

```bash
PHP >= 8.2
Node.js >= 20.x LTS
npm >= 10.x
Composer >= 2.7
MySQL 8.0 / MariaDB 10.6+
Git >= 2.40
```

### Instalacja

```bash
# 1. Sklonuj repozytorium
git clone https://github.com/piotroq/alubram-gmbh-wordpress.git
cd alubram-gmbh-wordpress

# 2. Zainstaluj dependencies
npm install
composer install

# 3. Uruchom lokalne środowisko
npx @wordpress/env start

# 4. Build TypeScript
npm run build

# 5. Watch mode
npm run watch
```

### Dostęp

- **WordPress:** http://localhost:8888
- **WP-Admin:** http://localhost:8888/wp-admin
- **Staging:** https://staging.alubram.at
- **Production:** https://alubram.at

---

## 📋 Dokumentacja

### AI Configuration

| Plik | Opis |
|------|------|
| **[CLAUDE.md](./CLAUDE.md)** | Claude AI configuration, prompts, workflow |
| **[QWEN.md](./QWEN.md)** | Qwen AI configuration, usage guide |
| **[OLLAMA.md](./OLLAMA.md)** | Ollama local AI setup, models |

### Project Documentation

| Plik | Opis |
|------|------|
| **[PROJECT-SPECIFICATION.md](./PROJECT-SPECIFICATION.md)** | Complete project specs, requirements |
| **[ROADMAP.SCHEMA.md](./ROADMAP.SCHEMA.md)** | Roadmap schema, phases, milestones |
| **[PAGES-WIREFRAMES.md](./PAGES-WIREFRAMES.md)** | All pages wireframes with diagrams |
| **[TECHNICAL-SHEETS.md](./TECHNICAL-SHEETS.md)** | Master technical instructions |

### Design Documentation

| Plik | Opis |
|------|------|
| **[docs/BRAND-SETTINGS.md](./docs/BRAND-SETTINGS.md)** | Brand colors, typography, guidelines |
| **[docs/DESIGN-SYSTEM.md](./docs/DESIGN-SYSTEM.md)** | UI components, patterns |
| **[docs/ARCHITECTURE.md](./docs/ARCHITECTURE.md)** | Technical architecture |

### Process Documentation

| Plik | Opis |
|------|------|
| **[CONTRIBUTING.md](./CONTRIBUTING.md)** | Contribution guidelines |
| **[FETCH-TEMPLATE-WEBSITE.md](./FETCH-TEMPLATE-WEBSITE.md)** | Website analysis template |

---

## 🎨 Brand Identity

### Kolory

```css
/* Primary */
--color-primary: #1A1A2E;      /* Dark Navy */
--color-accent: #C8A96E;       /* Gold/Champagne */
--color-secondary: #0F3460;    /* Deep Blue */

/* Secondary */
--color-light: #F8F6F1;        /* Warm White */
--color-dark: #0D0D0D;         /* Almost Black */
```

### Typografia

- **Headings:** Montserrat (400-900)
- **Body:** Inter (300-700)
- **Accent:** Playfair Display (400, 700)

---

## ✅ KPIs Projektu

### Technical KPIs

| Metryka | Target |
|---------|--------|
| **PageSpeed Mobile** | ≥ 90/100 |
| **PageSpeed Desktop** | ≥ 95/100 |
| **LCP** | < 2.5s |
| **FID/INP** | < 100ms |
| **CLS** | < 0.1 |
| **Accessibility** | ≥ 90/100 |
| **SEO** | 100/100 |

### Business KPIs

| Metryka | Target (12M) |
|---------|--------------|
| **Organic Traffic** | 5,000/month |
| **Keyword Rankings (Top 3)** | 20 keywords |
| **Lead Forms/Month** | 50 |
| **Bounce Rate** | < 40% |
| **Domain Rating** | 25 |

---

## 🔧 Development

### Komendy

```bash
# Build
npm run build          # Build TypeScript
npm run css:build      # Build Tailwind CSS

# Watch
npm run watch          # Watch TypeScript
npm run css:watch      # Watch Tailwind

# Lint
npm run lint           # ESLint
npm run lint:fix       # Auto-fix

# Test
npm run test           # All tests
npm run test:unit      # Unit tests
npm run test:e2e       # E2E tests
```

### Coding Standards

**PHP:**
- `declare(strict_types=1);`
- PSR-12 compliance
- WordPress Coding Standards
- Escape all output: `esc_html()`, `esc_url()`, `esc_attr()`
- Sanitize all input: `sanitize_text_field()`, `sanitize_email()`

**TypeScript:**
- ES6+ features
- Strict mode
- Async/await
- Type definitions

**CSS:**
- Mobile-first
- Brand variables from `:root`
- BEM-like naming
- Tailwind utility classes

---

## 🤝 Contributing

Zobacz **[CONTRIBUTING.md](./CONTRIBUTING.md)** dla szczegółowych wytycznych.

### Quick Guide

```bash
# 1. Fork repozytorium
# 2. Utwórz branch
git checkout -b feature/your-feature

# 3. Pracuj nad zmianami
# 4. Commit (Conventional Commits)
git commit -m "feat(contact-form): add AJAX form"

# 5. Push
git push origin feature/your-feature

# 6. Utwórz Pull Request
```

---

## 📞 Kontakty

| Kontakt | Dane |
|---------|------|
| **Klient** | ALUBRAM GMBH |
| **Email** | himberg@alubram.at |
| **Telefon** | +43 (0) 223 584 793 |
| **Adres** | Hintere Ortsstraße 31, 2325 Himberg bei Wien |

| Developer | Dane |
|-----------|------|
| **Repozytorium** | https://github.com/piotroq/alubram-gmbh-wordpress |
| **Issues** | https://github.com/piotroq/alubram-gmbh-wordpress/issues |

---

## 📄 License

Proprietary — All rights reserved to ALUBRAM GMBH.

---

*README.md — ALUBRAM GMBH WordPress Project | v1.0.0 | 2026-02-26*
