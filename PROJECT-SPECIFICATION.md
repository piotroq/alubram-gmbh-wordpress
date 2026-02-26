# PROJECT-SPECIFICATION.md — Complete Project Specification

> **Dokument:** Kompletna specyfikacja projektu ALUBRAM GMBH WordPress
> **Projekt:** `piotroq/alubram-gmbh-wordpress`
> **Wersja:** 1.0.0 | 2026-02-26

---

## 📋 Spis Treści

1. [Executive Summary](#1-executive-summary)
2. [Company Information](#2-company-information)
3. [Project Goals](#3-project-goals)
4. [Target Audience](#4-target-audience)
5. [Technical Specifications](#5-technical-specifications)
6. [Design Specifications](#6-design-specifications)
7. [Content Specifications](#7-content-specifications)
8. [Functional Requirements](#8-functional-requirements)
9. [SEO Requirements](#9-seo-requirements)
10. [Performance Requirements](#10-performance-requirements)
11. [Security Requirements](#11-security-requirements)
12. [Legal Requirements](#12-legal-requirements)
13. [Deliverables](#13-deliverables)
14. [Timeline](#14-timeline)
15. [Success Metrics](#15-success-metrics)

---

## 1. Executive Summary

### 1.1 Project Overview

**Project Name:** ALUBRAM GMBH WordPress Website  
**Client:** ALUBRAM GMBH  
**Industry:** Aluminum fences, gates, carports, and canopies manufacturer  
**Market:** DACH region (Austria, Germany, Switzerland)  
**Language:** German (de_AT)  
**Timeline:** 12-16 weeks  
**Budget:** [To be determined]

### 1.2 Project Summary

ALUBRAM GMBH requires a premium WordPress website to showcase their aluminum products (fences, gates, carports, canopies) to the DACH market. The website must reflect the company's position as a premium manufacturer, generate leads through contact forms, and provide comprehensive product information in German.

### 1.3 Key Objectives

1. **Brand Positioning:** Establish ALUBRAM as premium manufacturer in DACH region
2. **Lead Generation:** Generate 50+ qualified leads per month
3. **Product Showcase:** Display full product range with specifications
4. **SEO Visibility:** Achieve top 3 rankings for 20+ keywords
5. **Performance:** PageSpeed scores ≥ 90 mobile, ≥ 95 desktop

---

## 2. Company Information

### 2.1 Business Details

| Field | Value |
|-------|-------|
| **Company Name** | ALUBRAM GMBH |
| **Legal Form** | GmbH (Gesellschaft mit beschränkter Haftung) |
| **Industry** | Aluminum fences, gates, carports, canopies manufacturer |
| **Founded** | [Year] |
| **Employees** | [Number] |
| **Location** | Hintere Ortsstraße 31, 2325 Himberg bei Wien, Austria |

### 2.2 Contact Information

| Type | Details |
|------|---------|
| **Phone 1** | +43 (0) 223 584 793 |
| **Phone 2** | +43 664 437 3954 |
| **Email 1** | himberg@alubram.at |
| **Email 2** | wien@alubram.at |
| **Website** | https://alubram.at |
| **Contact Person** | Herr Szpak Irek |

### 2.3 Unique Selling Propositions (USPs)

1. **Direkt vom Hersteller** — No middleman, direct from manufacturer
2. **Lieferung in 3–6 Wochen garantiert** — Guaranteed delivery in 3-6 weeks
3. **24 Stunden · 7 Tage erreichbar** — Available 24/7
4. **Alles aus einer Hand** — Complete service: Consultation → Planning → Delivery → Installation
5. **Aluminium: rostfrei, wartungsfrei** — Rust-free, maintenance-free aluminum
6. **Pulverbeschichtet** — Powder-coated for decades of durability

### 2.4 Product Range

| Category | Products |
|----------|----------|
| **Zäune & Zaunfelder** | Aluminum fence panels, complete fence systems |
| **Tore** | Driveway gates, sliding gates, garden gates |
| **Carports** | Aluminum carports, double carports |
| **Überdachungen** | Terrace canopies, pergolas, entrance canopies |

---

## 3. Project Goals

### 3.1 Business Goals

| Goal | KPI | Target | Timeline |
|------|-----|--------|----------|
| **Brand Awareness** | Organic traffic | 5,000 visits/month | 12 months |
| **Lead Generation** | Contact forms | 50 leads/month | 6 months |
| **SEO Visibility** | Top 3 keywords | 20 keywords | 12 months |
| **User Engagement** | Bounce rate | < 40% | Ongoing |
| **Conversion Rate** | Form submissions | 3-5% | Ongoing |

### 3.2 Technical Goals

| Goal | Metric | Target |
|------|--------|--------|
| **PageSpeed Mobile** | Score | ≥ 90/100 |
| **PageSpeed Desktop** | Score | ≥ 95/100 |
| **LCP** | Time | < 2.5s |
| **FID/INP** | Time | < 100ms |
| **CLS** | Score | < 0.1 |
| **Accessibility** | WCAG 2.1 | Level AA |
| **SEO** | Lighthouse | 100/100 |

### 3.3 Design Goals

1. **Premium Look & Feel:** Modern, metallic, industrial-elegant design
2. **Brand Consistency:** Consistent use of brand colors, typography, and imagery
3. **Mobile-First:** Fully responsive design with mobile priority
4. **Accessibility:** WCAG 2.1 Level AA compliance
5. **User Experience:** Intuitive navigation, clear CTAs, smooth interactions

---

## 4. Target Audience

### 4.1 Primary Audience

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

### 4.2 Secondary Audience

- **Architects** — Specifying products for projects
- **Builders/Contractors** — Sourcing materials for clients
- **Real Estate Developers** — Bulk purchases for developments

### 4.3 User Personas

**Persona 1: Max Mustermann (Homeowner)**
- Age: 45-55
- Location: Wien Umgebung
- Need: New fence for property
- Behavior: Researches online, requests multiple quotes
- Decision factors: Quality, price, delivery time, warranty

**Persona 2: Architekt Bauer (Architect)**
- Age: 35-50
- Location: Österreich
- Need: Premium products for client projects
- Behavior: Specifies products, recommends to clients
- Decision factors: Quality, design, technical specs, reliability

---

## 5. Technical Specifications

### 5.1 Technology Stack

| Component | Technology | Version |
|-----------|------------|---------|
| **CMS** | WordPress | 6.9+ |
| **PHP** | PHP | 8.2+ |
| **Database** | MySQL / MariaDB | 8.0 / 10.6+ |
| **Frontend** | TypeScript, JavaScript | ES6+ |
| **CSS** | Tailwind CSS | 3.4+ |
| **Animations** | AOS | 2.3.4 |
| **Sliders** | Swiper.js | 11.x |
| **Icons** | Material Design Icons | Latest |

### 5.2 Theme Architecture

**Parent Theme:** `alubramat` (blank theme)  
**Child Theme:** `alubramat-child` (active, all customizations)

**Theme Structure:**
```
alubramat-child/
├── style.css                 # Brand variables + CSS
├── functions.php             # Bootstrap
├── front-page.php            # Homepage template
├── page.php                  # Generic page
├── single.php                # Blog post
├── archive.php               # Blog archive
├── header.php                # Site header
├── footer.php                # Site footer
│
├── page-templates/           # Custom page templates
│   ├── page-uber-uns.php
│   ├── page-produkte.php
│   ├── page-referenzen.php
│   ├── page-leistungen.php
│   └── page-kontakt.php
│
├── template-parts/           # Reusable parts
│   ├── sections/             # Sections
│   ├── components/           # Components
│   └── global/               # Global parts
│
├── inc/                      # PHP includes
│   ├── custom-post-types.php
│   ├── taxonomies.php
│   ├── schema-markup.php
│   ├── enqueue.php
│   └── ...
│
└── assets/
    ├── css/
    ├── js/
    └── images/
```

### 5.3 Custom Post Types

| CPT | Name | Slug | Public |
|-----|------|------|--------|
| **alubram_product** | Produkte | /produkte/ | Yes |
| **alubram_reference** | Referenzen | /referenzen/ | Yes |
| **alubram_testimonial** | Kundenmeinungen | (internal) | No |

### 5.4 Required Plugins

| Plugin | Purpose | Required |
|--------|---------|----------|
| **Yoast SEO** | SEO optimization | Yes |
| **Contact Form 7** | Contact forms | Yes |
| **WP Rocket** | Caching, performance | Yes |
| **Imagify** | Image optimization | Yes |
| **Borlabs Cookie** | DSGVO compliance | Yes |
| **Advanced Custom Fields Pro** | Custom fields | Yes |
| **Classic Editor** | Classic editor support | Yes |

---

## 6. Design Specifications

### 6.1 Brand Colors

```css
/* Primary Brand Colors */
--color-primary: #1A1A2E;         /* Dark Navy */
--color-primary-light: #16213E;   /* Dark Blue */
--color-accent: #C8A96E;          /* Gold/Champagne */
--color-accent-light: #E8D5A3;    /* Light Gold */
--color-accent-dark: #A07840;     /* Dark Gold */

/* Secondary Colors */
--color-secondary: #0F3460;       /* Deep Blue */
--color-dark: #0D0D0D;            /* Almost Black */
--color-light: #F8F6F1;           /* Warm White */
--color-white: #FFFFFF;

/* Aluminum Tones */
--color-aluminum: #8D9DB6;
--color-aluminum-light: #B8C5D6;
--color-aluminum-dark: #5A6A7E;
```

### 6.2 Typography

| Element | Font | Weights | Usage |
|---------|------|---------|-------|
| **Headings** | Montserrat | 400, 500, 600, 700, 800, 900 | H1-H6 |
| **Body** | Inter | 300, 400, 500, 600, 700 | Paragraphs, UI |
| **Accent** | Playfair Display | 400, 700 | Quotes, special text |

### 6.3 Visual Style

**Keywords:** Modern, Premium, Metallic, Industrial-Elegant

**Design Principles:**
1. Clean, uncluttered layouts
2. Generous whitespace
3. High-quality imagery
4. Subtle animations
5. Consistent spacing and alignment

**Inspiration Sites:**
- https://arrea.at/ — Video autoplay, section dynamics
- https://www.selt.com/home-de — Menu design, premium fonts
- https://mbveranda.de/ — Overall visual appearance

### 6.4 Component Library

| Component | Variants | States |
|-----------|----------|--------|
| **Buttons** | Primary, Secondary, Outline, Ghost | Default, Hover, Active, Disabled |
| **Cards** | Product, USP, Team, Feature | Default, Hover |
| **Forms** | Contact, Quote, Newsletter | Default, Focus, Error, Success |
| **Navigation** | Desktop, Mobile (Hamburger) | Default, Active, Open |

---

## 7. Content Specifications

### 7.1 Page Structure

| Page | Template | Word Count | Language |
|------|----------|------------|----------|
| **Homepage** | front-page.php | 1,200+ | German (de_AT) |
| **Über uns** | page-uber-uns.php | 600+ | German (de_AT) |
| **Produkte** | page-produkte.php | 800+ | German (de_AT) |
| **Single Produkt** | single-alubram_product.php | 1,000+ | German (de_AT) |
| **Referenzen** | page-referenzen.php | 400+ | German (de_AT) |
| **Kontakt** | page-kontakt.php | 250+ | German (de_AT) |
| **Blog** | archive.php / single.php | 1,500+ | German (de_AT) |
| **Impressum** | page.php | Legal text | German (de_AT) |
| **Datenschutz** | page.php | Legal text | German (de_AT) |

### 7.2 Content Guidelines

**Tone of Voice:**
- Professional, trustworthy, expert
- Sie-Form (formal address)
- Active voice
- Concrete benefits
- Numbers and facts

**SEO Guidelines:**
- Keyword density: 1.5-2.5%
- H1: One per page, includes primary keyword
- H2-H3: Hierarchical structure
- Meta title: 50-60 characters
- Meta description: 150-160 characters

### 7.3 Image Requirements

| Type | Format | Size | Notes |
|------|--------|------|-------|
| **Hero Images** | AVIF/WebP | 1920x1080 | Fullscreen, high quality |
| **Product Images** | AVIF/WebP | 1200x900 | Multiple angles |
| **Thumbnails** | WebP | 600x450 | Optimized |
| **Icons** | SVG | Vector | Material Icons |
| **Logo** | SVG | Vector | Multiple variants |

---

## 8. Functional Requirements

### 8.1 Core Features

| Feature | Description | Priority |
|---------|-------------|----------|
| **Responsive Design** | Mobile-first, all devices | Critical |
| **Contact Forms** | AJAX submission, validation | Critical |
| **Product Catalog** | CPT with categories, filters | Critical |
| **Image Gallery** | Lightbox, slider | High |
| **Testimonials** | Slider with ratings | High |
| **Google Maps** | With cookie consent | High |
| **Blog** | News, articles | Medium |
| **Search** | Site-wide search | Medium |
| **Social Sharing** | Share buttons | Low |

### 8.2 Form Requirements

**Contact Form Fields:**
- Name (required)
- Email (required)
- Phone (optional)
- PLZ/Postcode (required)
- Message (required)
- Product interest (dropdown)
- DSGVO consent checkbox (required)

**Form Features:**
- Client-side validation
- Server-side validation
- AJAX submission (no page reload)
- Success/error messages
- Email notifications
- Spam protection (honeypot)
- Nonce verification

### 8.3 Interactive Features

| Feature | Description |
|---------|-------------|
| **Sticky Header** | Transparent → solid on scroll |
| **Smooth Scroll** | Anchor links, navigation |
| **Parallax** | Hero sections, backgrounds |
| **AOS Animations** | Fade, zoom on scroll |
| **Counters** | Animated number count-up |
| **Hover Effects** | Cards, buttons, images |
| **Mobile Menu** | Hamburger, full-screen |

---

## 9. SEO Requirements

### 9.1 Technical SEO

| Requirement | Implementation |
|-------------|----------------|
| **XML Sitemap** | Yoast SEO auto-generation |
| **Robots.txt** | Custom configuration |
| **Canonical URLs** | Auto-generated |
| **Schema.org** | JSON-LD markup |
| **Breadcrumbs** | Schema.org BreadcrumbList |
| **Open Graph** | Meta tags for social |
| **Twitter Cards** | Summary large image |

### 9.2 On-Page SEO

| Element | Requirement |
|---------|-------------|
| **Title Tags** | 50-60 chars, keyword at start |
| **Meta Descriptions** | 150-160 chars, compelling |
| **H1 Tags** | One per page, includes keyword |
| **H2-H6 Tags** | Hierarchical structure |
| **Image Alt Text** | Descriptive, German |
| **Internal Linking** | 3-5 links per page |
| **URL Structure** | Short, descriptive, keyword-rich |

### 9.3 Target Keywords

**Primary Keywords:**
- Aluminiumzaun Hersteller Österreich
- Aluzaun direkt vom Hersteller
- Zaunanlage Wien
- Carport Aluminium kaufen
- Einfahrtstor Aluminium
- Überdachung Terrasse

**Long-Tail Keywords:**
- Aluminiumzaun direkt vom Hersteller Österreich
- Carport aus Aluminium kaufen Wien
- wartungsfreier Aluzaun Austria
- Aluminiumtor Schiebetor kaufen
- Terrassenüberdachung Aluminium Österreich

---

## 10. Performance Requirements

### 10.1 Core Web Vitals

| Metric | Target | Strategy |
|--------|--------|----------|
| **LCP** | < 2.5s | Hero preload, critical CSS, fast server |
| **FID/INP** | < 100ms | Defer JS, Web Worker for heavy tasks |
| **CLS** | < 0.1 | Explicit dimensions, font-display: swap |

### 10.2 Performance Budget

| Resource | Budget | Strategy |
|----------|--------|----------|
| **Page Size** | < 2MB | Image optimization, minification |
| **Images** | < 1MB | AVIF/WebP, lazy loading |
| **CSS** | < 200KB | Critical CSS inline, rest deferred |
| **JavaScript** | < 300KB | Defer, async, code splitting |
| **Fonts** | < 100KB | Local hosting, subset, swap |

### 10.3 Optimization Techniques

- **Image Optimization:** AVIF/WebP format, lazy loading, srcset
- **Caching:** WP Rocket, browser caching, object cache
- **CDN:** Cloudflare for static assets
- **Minification:** CSS, JS, HTML minified
- **Critical CSS:** Inline for above-the-fold
- **Preloading:** LCP image, fonts, critical resources
- **Compression:** Gzip/Brotli enabled

---

## 11. Security Requirements

### 11.1 WordPress Security

| Measure | Implementation |
|---------|----------------|
| **SSL/HTTPS** | Mandatory, HSTS enabled |
| **Security Headers** | CSP, X-Frame-Options, etc. |
| **File Permissions** | 644 files, 755 directories |
| **WP Config** | Secured, salts rotated |
| **Login Security** | Limited attempts, 2FA recommended |
| **Regular Updates** | WordPress, plugins, theme |

### 11.2 Code Security

| Practice | Implementation |
|----------|----------------|
| **Input Sanitization** | sanitize_text_field(), sanitize_email() |
| **Output Escaping** | esc_html(), esc_url(), esc_attr() |
| **Nonce Verification** | wp_nonce_field(), wp_verify_nonce() |
| **Capability Checks** | current_user_can() |
| **SQL Injection** | $wpdb->prepare() for queries |
| **XSS Prevention** | All output escaped |

### 11.3 Data Protection

| Requirement | Implementation |
|-------------|----------------|
| **DSGVO Compliance** | Borlabs Cookie, consent management |
| **Privacy Policy** | Complete Datenschutzerklärung |
| **Form Data** | Encrypted transmission, secure storage |
| **Google Fonts** | Locally hosted (DSGVO) |
| **Google Maps** | Behind cookie consent |
| **Analytics** | Only with opt-in |

---

## 12. Legal Requirements

### 12.1 Required Pages

| Page | German | Required |
|------|--------|----------|
| **Imprint** | Impressum | Yes (Austrian law) |
| **Privacy Policy** | Datenschutzerklärung | Yes (DSGVO) |
| **Terms & Conditions** | AGB | Recommended |
| **Cookie Policy** | Cookie-Richtlinie | Yes (DSGVO) |

### 12.2 Impressum Requirements

**Mandatory Information (Austrian ECG):**
- Company name (ALUBRAM GMBH)
- Address (Hintere Ortsstraße 31, 2325 Himberg bei Wien)
- Contact (phone, email)
- UID-Nummer (VAT ID)
- Firmenbuchnummer (Company registration number)
- Firmenbuchgericht (Registry court)
- Berufsbezeichnung und Verleihungsstaat

### 12.3 DSGVO Requirements

- Cookie consent before tracking
- Privacy policy with all processing activities
- Right to access, erasure, rectification
- Data processing agreements with processors
- SSL encryption for data transmission
- Local hosting of Google Fonts
- Google Maps only with consent

---

## 13. Deliverables

### 13.1 Design Deliverables

| Deliverable | Format | Due Date |
|-------------|--------|----------|
| **Moodboard** | PDF/Figma | Week 3 |
| **Wireframes** | Figma | Week 3 |
| **Design System** | Figma | Week 4 |
| **Homepage Mockup** | Figma | Week 4 |
| **Inner Page Mockups** | Figma | Week 5 |
| **Interactive Prototype** | Figma | Week 5 |

### 13.2 Development Deliverables

| Deliverable | Description | Due Date |
|-------------|-------------|----------|
| **WordPress Setup** | Local + staging environments | Week 6 |
| **Theme Development** | Parent + child theme | Week 6-7 |
| **Homepage** | front-page.php with all sections | Week 7 |
| **CPT Registration** | Products, references, testimonials | Week 8 |
| **Product Templates** | Single, archive, taxonomy | Week 8 |
| **Inner Pages** | 5 custom templates | Week 9 |
| **Contact Form** | AJAX with validation | Week 10 |
| **Animations** | AOS + custom | Week 10 |
| **Performance Optimization** | Images, caching, minification | Week 11 |
| **SEO Implementation** | Meta tags, schema, sitemap | Week 11 |
| **Content Population** | All pages with German content | Week 11 |

### 13.3 Testing Deliverables

| Deliverable | Description | Due Date |
|-------------|-------------|----------|
| **Functional Testing** | All features tested | Week 12 |
| **Cross-Browser Testing** | Chrome, Firefox, Safari, Edge | Week 12 |
| **Performance Audit** | Lighthouse, PageSpeed | Week 13 |
| **Accessibility Audit** | WCAG 2.1 AA | Week 13 |
| **Security Audit** | Code review, vulnerability scan | Week 13 |

### 13.4 Deployment Deliverables

| Deliverable | Description | Due Date |
|-------------|-------------|----------|
| **Production Setup** | Server configuration | Week 14 |
| **Database Migration** | Staging → production | Week 14 |
| **DNS Configuration** | Domain pointing | Week 14 |
| **SSL Certificate** | HTTPS enabled | Week 14 |
| **Go-Live** | Site publicly accessible | Week 14 |

### 13.5 Post-Launch Deliverables

| Deliverable | Description | Due Date |
|-------------|-------------|----------|
| **Training** | Client training session | Week 15 |
| **Documentation** | User manual, technical docs | Week 15 |
| **Monitoring Report** | 2-week performance report | Week 16 |
| **SEO Report** | 1-month ranking report | Week 18 |

---

## 14. Timeline

### 14.1 Project Phases

```
Week 1-2:   Discovery & Planning
Week 3-5:   Design
Week 6-11:  Development
Week 12-13: Testing & QA
Week 14:    Deployment
Week 15-16: Post-Launch
```

### 14.2 Key Milestones

| Milestone | Due Date | Status |
|-----------|----------|--------|
| **Project Kickoff** | Week 1, Day 2 | ⬜ Pending |
| **Discovery Complete** | Week 2, Day 5 | ⬜ Pending |
| **Wireframes Approved** | Week 3, Day 5 | ⬜ Pending |
| **Design Approved** | Week 5, Day 4 | ⬜ Pending |
| **Homepage Complete** | Week 7, Day 5 | ⬜ Pending |
| **All Templates Complete** | Week 9, Day 5 | ⬜ Pending |
| **Development Complete** | Week 11, Day 5 | ⬜ Pending |
| **QA Complete** | Week 13, Day 5 | ⬜ Pending |
| **Go-Live** | Week 14, Day 5 | ⬜ Pending |

---

## 15. Success Metrics

### 15.1 Technical KPIs

| KPI | Target | Measurement Tool |
|-----|--------|-----------------|
| **PageSpeed Mobile** | ≥ 90/100 | PageSpeed Insights |
| **PageSpeed Desktop** | ≥ 95/100 | PageSpeed Insights |
| **LCP** | < 2.5s | Chrome UX Report |
| **FID/INP** | < 100ms | Chrome UX Report |
| **CLS** | < 0.1 | Chrome UX Report |
| **Accessibility** | ≥ 90/100 | Lighthouse |
| **SEO** | 100/100 | Lighthouse |

### 15.2 Business KPIs

| KPI | Baseline | Target (12M) | Measurement |
|-----|----------|--------------|-------------|
| **Organic Traffic** | 0 | 5,000/month | Google Analytics |
| **Keyword Rankings (Top 3)** | 0 | 20 keywords | SEMrush/Ahrefs |
| **Lead Forms/Month** | 0 | 50 | Form submissions |
| **Bounce Rate** | N/A | < 40% | Google Analytics |
| **Avg. Session Duration** | N/A | > 2:30 | Google Analytics |
| **Domain Rating** | 0 | 25 | Ahrefs |

### 15.3 Reporting Schedule

| Report | Frequency | Audience |
|--------|-----------|----------|
| **Performance Report** | Weekly | Development team |
| **SEO Report** | Monthly | Client, marketing |
| **Traffic Report** | Monthly | Client |
| **Lead Report** | Weekly | Sales team |
| **Security Report** | Monthly | Development team |

---

*PROJECT-SPECIFICATION.md — ALUBRAM GMBH WordPress Project | v1.0.0 | 2026-02-26*
