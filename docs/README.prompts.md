# README.prompts.md — AI Prompt Library

> **Dokument:** Biblioteka promptów dla AI agents
> **Projekt:** `piotroq/alubram-gmbh-wordpress`
> **Modele:** Claude Sonnet 4.6 / Claude Opus 4.6
> **Wersja:** 1.0.0 | 2026-02-26

---

## 📋 Spis Treści

1. [Wprowadzenie](#1-wprowadzenie)
2. [Struktura Promptu](#2-struktura-promptu)
3. [Prompty do Generowania Kodu](#3-prompty-do-generowania-kodu)
4. [Prompty do Code Review](#4-prompty-do-code-review)
5. [Prompty do SEO](#5-prompty-do-seo)
6. [Prompty do UI/UX](#6-prompty-do-uiux)
7. [Prompty do Security](#7-prompty-do-security)
8. [Prompty do Debugowania](#8-prompty-do-debugowania)
9. [Prompty do Dokumentacji](#9-prompty-do-dokumentacji)
10. [Best Practices](#10-best-practices)

---

## 1. Wprowadzenie

### 1.1 Jak Używać Tej Biblioteki

Ta biblioteka zawiera gotowe szablony promptów do różnych zadań w projekcie ALUBRAM GMBH WordPress. Każdy prompt jest zoptymalizowany pod kątem:

- **Kontekstu** — zawsze zawiera odniesienia do dokumentacji projektu
- **Konkretu** — precyzyjnie określa oczekiwany output
- **Quality gates** — definiuje wymagania jakościowe
- **Formatu** — określa strukturę odpowiedzi

### 1.2 Dostępni Agenci

| Agent | Specjalizacja | Plik |
|-------|--------------|------|
| `wordpress-master` | WordPress development | `.claude/agents/business-product/wordpress-master.md` |
| `php-reviewer` | PHP code review | `.claude/agents/code-review/php-reviewer.md` |
| `seo-de-specialist` | SEO DE/AT | `.claude/agents/seo/seo-de-specialist.md` |
| `ui-ux-designer` | UI/UX design | `.claude/agents/design/ui-ux-designer.md` |
| `wp-security-auditor` | Security audit | `.claude/agents/security/wp-security-auditor.md` |

---

## 2. Struktura Promptu

### 2.1 Template — Uniwersalny

```markdown
[TASK]: [Krótki opis zadania — 1 zdanie]

[CONTEXT]:
- [Kontekst projektu / firmy]
- [Powiązane pliki / dokumentacja]
- [Istniejące rozwiązania]

[REQUIREMENTS]:
- [Wymaganie 1]
- [Wymaganie 2]
- [Wymaganie 3]

[TECHNICAL SPECS]:
- [Specyfikacja techniczna 1]
- [Specyfikacja techniczna 2]

[EXPECTED OUTPUT]:
- [Konkretny format outputu]
- [Struktura pliku / kodu]
- [Dodatkowe elementy]

[CONSTRAINTS]:
- [Ograniczenie 1]
- [Ograniczenie 2]

[EXAMPLES]:
- [Przykład inspiracji / referencji]
```

### 2.2 Przykład — Wypełniony Template

```markdown
[TASK]: Wygeneruj kompletny plik PHP `page-templates/page-kontakt.php`

[CONTEXT]:
- ALUBRAM GMBH — austriacki producent aluminiowych ogrodzeń
- Strona w języku niemieckim (de_AT)
- Dokumentacja: TECHNICAL-SHEETS.md, BRAND-SETTINGS.md, DESIGN-SYSTEM.md

[REQUIREMENTS]:
- PSR-12 compliance, strict_types=1
- DSGVO compliant (Google Maps za cookie consent)
- AOS animations na wszystkich sekcjach
- Mobile-first CSS (Tailwind + custom vars)
- AJAX submit formularza (bez reload) + nonce WordPress
- Pełna walidacja client-side + server-side

[TECHNICAL SPECS]:
- Formularz: Name, Email, Telefon, PLZ, Nachricht, Produktinteresse (dropdown), DSGVO checkbox
- Schema.org JSON-LD: LocalBusiness
- Google Maps: iframe z lazy loading + placeholder przed akceptacją cookies
- Sekcje: Hero z breadcrumbs, dane kontaktowe z ikonami MDI, formularz, mapa

[EXPECTED OUTPUT]:
- Kompletny plik PHP (700+ linii)
- Inline komentarze przy logice AJAX
- PHPDoc dla wszystkich funkcji pomocniczych
- Przykładowe dane kontaktowe w języku niemieckim

[CONSTRAINTS]:
- Nie używaj jQuery — tylko vanilla JS
- Google Fonts hostowane lokalnie (DSGVO)
- Brak inline CSS — wszystko przez klasy Tailwind/custom

[EXAMPLES]:
- Inspiracja: https://arrea.at/kontakt/ — układ sekcji
- Design: DESIGN-SYSTEM.md → Form Elements
```

---

## 3. Prompty do Generowania Kodu

### 3.1 Homepage Template

```markdown
[TASK]: Wygeneruj kompletny plik `front-page.php` — Homepage

[CONTEXT]:
- ALUBRAM GMBH — producent premium aluminiowych ogrodzeń, bram, Carport
- Strona główna bez breadcrumbs, z Hero Section fullscreen
- Język: niemiecki (de_AT)
- Inspiracje: arrea.at, selt.com/home-de, mbveranda.de

[REQUIREMENTS]:
- 11 sekcji w określonej kolejności (poniżej)
- AOS animations: fade-up, fade-down, zoom-in-up
- Parallax effect na hero i sekcji Über uns
- Counter animation (stats section)
- Swiper slider dla testimonials
- Mobile-first: mobile → tablet (768px) → desktop (1024px) → large (1280px)

[SECTIONS ORDER]:
1. Hero Section — fullscreen video/parallax, H1, CTA buttons, USP badges
2. USP Bar — 4 ikony z kluczowymi zaletami (local_shipping, schedule, handyman, verified)
3. Produkte Übersicht — grid 4 kategorie produktów z hover effects
4. Warum ALUBRAM — why us section z licznikami (counter animation)
5. Unser Prozess — 4-krokowy proces (Beratung → Planung → Lieferung → Montage)
6. Referenzen Galerie — masonry gallery z lightbox (Swiper)
7. Über uns Teaser — company story z parallax image
8. Kundenmeinungen — testimonials slider (Swiper)
9. CTA Banner — fullwidth z gradient overlay + formularz kontaktowy inline
10. Aktuelles Blog — 3 najnowsze wpisy
11. Kontakt Teaser — mapa + dane kontaktowe

[TECHNICAL SPECS]:
- Hero: fetchpriority="high" na LCP image
- Wszystkie img: loading="lazy" decoding="async" + srcset + sizes
- Tailwind utility classes + custom CSS z BRAND-SETTINGS.md
- Schema.org JSON-LD: LocalBusiness + Manufacturer
- Sticky header z scroll effect (transparent → solid)

[EXPECTED OUTPUT]:
- Kompletny plik PHP (1000+ linii)
- Wszystkie sekcje z inline komentarzami
- PHPDoc dla helper functions
- Przykładowe treści w języku niemieckim

[BRAND COLORS]:
- Primary: #1A1A2E (Dark Navy)
- Accent: #C8A96E (Gold/Champagne)
- Secondary: #0F3460 (Deep Blue)
```

### 3.2 Single Product Template

```markdown
[TASK]: Wygeneruj plik `single-alubram_product.php` — Single Product Template

[CONTEXT]:
- Custom Post Type: alubram_product
- Pola ACF: _product_category, _product_material, _delivery_time, _warranty_years, _price_from, _gallery_images, _technical_specs, _colors_available
- Taxonomie: product_category, product_material, product_color

[REQUIREMENTS]:
- Breadcrumbs na górze (Schema.org BreadcrumbList)
- Galeria produktu (Swiper slider z thumbs)
- Tabela specyfikacji technicznych
- Dostępne kolory (color swatches z nazwami RAL)
- FAQ sekcja (Schema FAQPage)
- Powiązane produkty (related products query)
- CTA z formularzem zapytania

[SECTIONS]:
1. Hero z breadcrumbs + tytuł produktu
2. Main content: opis produktu + galeria + specyfikacje
3. Zalety techniczne (lista z ikonami MDI)
4. Konfiguracja kolorów/wariantów
5. FAQ sekcja (accordion)
6. Powiązane produkty (grid 4)
7. CTA z formularzem zapytania

[TECHNICAL SPECS]:
- ACF functions: get_field(), have_rows(), the_sub_field()
- Swiper: main slider + thumbs slider
- Schema.org: Product + Offer + AggregateRating (jeśli opinie)
- Related products: WP_Query z tax_query
- Formularz: AJAX submit z walidacją

[EXPECTED OUTPUT]:
- Kompletny plik PHP (800+ linii)
- Wszystkie ACF fields poprawnie zaimplementowane
- Swiper initialization w TypeScript
- JSON-LD markup dla Product
```

### 3.3 Kontakt Template

```markdown
[TASK]: Wygeneruj plik `page-templates/page-kontakt.php` — Kontakt

[CONTEXT]:
- Strona kontaktowa z formularzem + Google Maps
- Dane firmy: ALUBRAM GMBH, Hintere Ortsstraße 31, 2325 Himberg bei Wien
- Kontakt: +43 (0) 223 584 793, himberg@alubram.at
- DSGVO: Google Maps tylko po akceptacji cookies

[REQUIREMENTS]:
- Formularz AJAX: Name, Email, Telefon, PLZ, Nachricht, Produktinteresse, DSGVO checkbox
- Walidacja: client-side (HTML5 + JS) + server-side (PHP sanitize)
- Google Maps: placeholder przed akceptacją + iframe po
- Schema.org: LocalBusiness JSON-LD
- AOS animations

[SECTIONS]:
1. Hero z breadcrumbs
2. Dane kontaktowe (3 kolumny: adres, telefon/email, godziny otwarcia)
3. Formularz kontaktowy
4. Google Maps
5. CTA banner

[TECHNICAL SPECS]:
- AJAX handler: wp_ajax_nopriv_alubram_contact_form
- Nonce: wp_create_nonce('alubram_contact_nonce')
- Sanitize: sanitize_text_field(), sanitize_email(), absint()
- Google Maps: API key z .env, lazy load iframe
- Honeypot anti-spam field

[EXPECTED OUTPUT]:
- Kompletny plik PHP (700+ linii)
- AJAX handler w pliku lub inc/ajax-handlers.php
- TypeScript: forms.ts z walidacją
- JSON-LD: LocalBusiness z contact info
```

### 3.4 Custom Post Type Registration

```markdown
[TASK]: Wygeneruj plik `inc/custom-post-types.php` — CPT Registration

[CONTEXT]:
- 3 Custom Post Types: alubram_product, alubram_reference, alubram_testimonial
- Rejestracja przez register_post_type() z pełnym konfigurem
- Support dla Gutenberg (show_in_rest: true)

[CPT: alubram_product]:
- Labels: Produkte, Produkt, Kategorie
- Rewrite slug: 'produkte'
- Supports: title, editor, thumbnail, excerpt, custom-fields
- Menu icon: dashicons-admin-generic
- Taxonomie: product_category (hierarchical), product_material, product_color

[CPT: alubram_reference]:
- Labels: Referenzen, Referenz
- Rewrite slug: 'referenzen'
- Supports: title, editor, thumbnail, excerpt
- Menu icon: dashicons-images-alt2

[CPT: alubram_testimonial]:
- Labels: Kundenmeinungen, Kundenmeinung
- Rewrite slug: nie (niepubliczne)
- Supports: title, editor
- Menu icon: dashicons-format-quote
- show_ui: true, show_in_menu: false (tylko admin)

[TECHNICAL SPECS]:
- Hook: init (priority 10)
- Labels: pełna tablica z niemieckimi nazwami
- Capabilities: edit_post, edit_posts, edit_others_posts, publish_posts
- Has_archive: true dla product i reference
- Public: true (except testimonial: public => false)

[EXPECTED OUTPUT]:
- Kompletny plik PHP z 3 funkcjami register_post_type()
- Wszystkie labels po niemiecku
- PHPDoc dla każdej funkcji
- Hook add_action('init', ...)
```

### 3.5 Shortcodes

```markdown
[TASK]: Wygeneruj plik `inc/shortcodes.php` — Shortcodes Registration

[CONTEXT]:
- Shortcodes do użycia w Gutenberg/Classic Editor
- Wszystkie shortcodes z prefiksem `alubram_`

[SHORTCODES TO IMPLEMENT]:
1. [alubram_cta text="..." url="..." style="primary|outline|ghost"]
2. [alubram_usps style="horizontal|vertical|cards"]
3. [alubram_products count="4" category="zaune|tore|carports" layout="grid|list"]
4. [alubram_counter label="..." value="15" icon="star"]
5. [alubram_contact_form type="quote|general|callback"]
6. [alubram_gallery ref_id="123" columns="3"]
7. [alubram_process steps="4"]
8. [alubram_faq category="produkte|all"]
9. [alubram_testimonials count="3" autoplay="true"]
10. [alubram_delivery_badge weeks="3-6"]

[TECHNICAL SPECS]:
- Funkcje: add_shortcode('alubram_name', 'callback_function')
- Output buffering: ob_start() ... return ob_get_clean()
- Atrybuty: shortcode_atts() z defaults
- Content: $content parameter dla shortcodes z content
- Escape output: esc_html(), esc_url(), wp_kses_post()

[EXPECTED OUTPUT]:
- Kompletny plik PHP z 10 shortcodes
- Przykłady użycia w komentarzach
- PHPDoc dla każdej funkcji
- Hook: add_action('init', 'register_alubram_shortcodes')
```

---

## 4. Prompty do Code Review

### 4.1 PHP Security Review

```markdown
[TASK]: Przeprowadź security review pliku [nazwa_pliku.php]

[CONTEXT]:
- Plik PHP z motywu alubramat-child
- Production environment (DSGVO compliance required)

[REVIEW CHECKLIST]:
### Input Security
- [ ] Wszystkie $_POST/$_GET sanitized (sanitize_text_field, sanitize_email, absint)
- [ ] Nonce verification (wp_verify_nonce)
- [ ] Capability checks (current_user_can)

### Output Security
- [ ] Wszystkie echo escaped (esc_html, esc_url, esc_attr, wp_kses_post)
- [ ] Brak inline JavaScript
- [ ] Brak eval() lub base64_decode()

### WordPress Best Practices
- [ ] if (!defined('ABSPATH')) { exit; } na początku
- [ ] declare(strict_types=1);
- [ ] Właściwe użycie WP_Query (nie raw SQL)
- [ ] Prepared statements dla $wpdb->prepare()

### Performance
- [ ] Transient cache dla ciężkich queries
- [ ] WP_Query z 'fields' => 'ids' gdy tylko ID potrzebne
- [ ] Brak N+1 queries

[EXPECTED OUTPUT]:
- Lista wszystkich security issues (critical, high, medium, low)
- Konkretne linie kodu z problemami
- Sugerowane fixy z kodem
- Overall security score (0-100)
```

### 4.2 PSR-12 Compliance Check

```markdown
[TASK]: Sprawdź zgodność pliku [nazwa_pliku.php] z PSR-12

[CONTEXT]:
- PHP 8.2+ codebase
- WordPress Coding Standards

[CHECKLIST]:
### Naming Conventions
- [ ] lowercase_with_underscore dla plików
- [ ] PascalCase dla klas
- [ ] camelCase dla metod i funkcji
- [ ] UPPERCASE dla stałych

### Code Structure
- [ ] 4-space indentation (nie tabs)
- [ ] Max line length: 120 znaków
- [ ] Blank lines między funkcjami
- [ ] Opening brace na tej samej linii

### Type Declarations
- [ ] declare(strict_types=1);
- [ ] Type hints dla argumentów (string, int, bool, array, ?nullable)
- [ ] Return type declarations (void, string, int, bool, array, ?nullable)

### Documentation
- [ ] PHPDoc dla klas i funkcji
- [ ] @package, @version tags
- [ ] Opis parametrów @param
- [ ] Opis return @return

[EXPECTED OUTPUT]:
- Lista wszystkich PSR-12 violations
- Numery linii z problemami
- Sugerowane poprawki
- Overall compliance score (0-100)
```

### 4.3 Performance Review

```markdown
[TASK]: Przeprowadź performance review całego motywu

[CONTEXT]:
- Motyw alubramat-child
- Cel: PageSpeed Mobile ≥ 90, Desktop ≥ 95

[REVIEW AREAS]:
### Images
- [ ] loading="lazy" na wszystkich img poniżej fold
- [ ] fetchpriority="high" na LCP image (hero)
- [ ] srcset + sizes atrybuty
- [ ] AVIF/WebP format z fallback
- [ ] Explicit width/height (CLS prevention)

### Scripts
- [ ] defer/async na external scripts
- [ ] Brak render-blocking JS
- [ ] Minified CSS/JS
- [ ] Critical CSS inline

### Database Queries
- [ ] WP_Query z proper indexing
- [ ] Transient cache dla powtarzających się queries
- [ ] Brak N+1 queries
- [ ] Pre_get_posts hooks dla optymalizacji

### Caching
- [ ] Object cache (wp_cache_get/set)
- [ ] Transient cache (get_transient/set_transient)
- [ ] Fragment cache dla sekcji

[EXPECTED OUTPUT]:
- Performance audit report
- Lista bottlenecków z priorytetami
- Konkretne sugestie optymalizacji
- Estimated impact na PageSpeed
```

---

## 5. Prompty do SEO

### 5.1 Meta Tags Generation

```markdown
[TASK]: Wygeneruj meta tags dla strony [nazwa_strony]

[CONTEXT]:
- ALUBRAM GMBH — producent aluminiowych ogrodzeń
- Rynek: Austria (de_AT), Niemcy (de_DE)
- Język: niemiecki

[PAGE INFO]:
- URL: /produkte/zaune-zaunfelder/
- H1: Aluminium Zaunfelder — Direkt vom Hersteller
- Main content: Opis produktu Zaunfelder (800 słów)
- Target keyword: Aluminium Zaunfelder kaufen

[REQUIREMENTS]:
- Title: 50-60 znaków, keyword na początku
- Meta description: 150-160 znaków, keyword + USP + CTA
- Meta keywords: 5-8 long-tail keywords
- OG tags: og:title, og:description, og:image, og:url, og:type
- Twitter Card: summary_large_image

[KEYWORDS]:
- Primary: Aluminium Zaunfelder
- Secondary: Aluzaun kaufen, Zaunfeld Aluminium, wartungsfreier Zaun
- Long-tail: Aluminiumzaun direkt vom Hersteller Österreich

[EXPECTED OUTPUT]:
- Kompletny HTML block z meta tags
- JSON-LD Schema.org markup
- Alternatywne warianty title/description (A/B test)
```

### 5.2 Schema.org JSON-LD

```markdown
[TASK]: Wygeneruj Schema.org JSON-LD markup dla [typ_strony]

[CONTEXT]:
- ALUBRAM GMBH — LocalBusiness + Manufacturer
- Strona: [URL]
- Język: de_AT

[SCHEMA TYPES NEEDED]:
1. LocalBusiness + Manufacturer (Homepage)
2. Product (single-alubram_product.php)
3. BreadcrumbList (wszystkie strony poza Homepage)
4. FAQPage (strony produktów z FAQ)
5. Organization (footer)

[DATA FOR LOCALBUSINESS]:
- Name: ALUBRAM GMBH
- Address: Hintere Ortsstraße 31, 2325 Himberg bei Wien, Austria
- Phone: +43 223 584 793
- Email: himberg@alubram.at
- OpeningHours: Mo-Su 00:00-24:00
- PriceRange: €€€
- AreaServed: AT, DE, CH

[EXPECTED OUTPUT]:
- Valid JSON-LD code dla każdego typu
- Przykłady implementacji w PHP (functions.php)
- Test link do Schema.org Validator
```

### 5.3 Content SEO Optimization

```markdown
[TASK]: Zoptymalizuj treść strony [URL] pod SEO

[CONTEXT]:
- Obecna treść: [wklej obecny content]
- Target keyword: [główne słowo kluczowe]
- Konkurencja: [URL konkurencji]

[REQUIREMENTS]:
- Keyword density: 1.5-2.5%
- Nagłówki: H1 (1x), H2 (główne sekcje), H3 (podsekcje)
- Długość: min. 800 słów dla strony produktu
- Internal linking: 3-5 linków do powiązanych stron
- External linking: 1-2 autorytatywne źródła

[OPTIMIZATION AREAS]:
- Title tag z keyword na początku
- Meta description z CTA
- H1 z primary keyword
- H2/H3 z secondary keywords
- First 100 words: keyword występuje
- Image alt tags z keywords
- Internal links z anchor text

[EXPECTED OUTPUT]:
- Zoptymalizowana treść z highlighted keywords
- Sugestie nagłówków H2/H3
- Propozycje internal links
- Meta tags (title, description)
```

---

## 6. Prompty do UI/UX

### 6.1 Component Design

```markdown
[TASK]: Zaprojektuj komponent UI — [nazwa_komponentu]

[CONTEXT]:
- Design System: DESIGN-SYSTEM.md
- Brand colors: BRAND-SETTINGS.md
- Styl: nowoczesny, premium, metaliczny, industrialno-elegancki

[COMPONENT]:
- Name: Product Card
- States: default, hover, active, disabled
- Variants: small, medium, large
- Content: image, category, title, excerpt, price, CTA

[REQUIREMENTS]:
- Mobile-first CSS
- AOS animation: zoom-in-up
- Hover effect: translateY(-8px) + shadow
- Image overlay z CTA na hover
- Badge (Bestseller/Neu) w rogu
- Accessibility: focus states, keyboard navigation

[BRAND COLORS]:
- Background: #FFFFFF
- Text: #1A1A2E (primary), #9E9E9E (secondary)
- Accent: #C8A96E (gold)
- Shadow: rgba(0,0,0,0.12)

[EXPECTED OUTPUT]:
- HTML structure (BEM naming)
- CSS (custom properties + Tailwind)
- Hover/focus states
- Responsive breakpoints (mobile, tablet, desktop)
- Usage examples
```

### 6.2 Section Design

```markdown
[TASK]: Zaprojektuj sekcję — [nazwa_sekcji]

[CONTEXT]:
- Strona: Homepage
- Pozycja: po hero section
- Cel: prezentacja 4 kluczowych USPs

[SECTION]:
- Name: USP Bar
- Layout: 4 kolumny (mobile: stack, desktop: row)
- Content per USP: icon, title, short description

[REQUIREMENTS]:
- AOS: fade-up z delay (0, 100, 200, 300)
- Ikony Material Design: local_shipping, schedule, handyman, verified
- Tło: var(--color-light) lub gradient
- Responsive: 1 col mobile → 2 cols tablet → 4 cols desktop
- Hover effect na każdej karcie

[BRAND GUIDELINES]:
- Font heading: Montserrat 700
- Font body: Inter 400
- Spacing: var(--spacing-6) mobile, var(--spacing-10) desktop
- Border radius: var(--border-radius-lg)

[EXPECTED OUTPUT]:
- HTML structure
- CSS z custom properties
- Responsive breakpoints
- AOS attributes
- Ikony MD z proper font-variation-settings
```

### 6.3 Animation Design

```markdown
[TASK]: Zaprojektuj animacje dla [element/section]

[CONTEXT]:
- Biblioteka: AOS v2.3.4 + custom @keyframes
- Performance: 60fps, GPU-accelerated

[ANIMATIONS NEEDED]:
1. Hero section entrance (fade-up + stagger)
2. Counter animation (count-up numbers)
3. Card hover (shimmer effect)
4. Parallax scroll (background images)
5. CTA button pulse (gold glow)

[REQUIREMENTS]:
- Duration: 600-1200ms
- Easing: ease-in-out-cubic lub cubic-bezier(0.4, 0, 0.2, 1)
- Once: true (animuj tylko raz)
- Offset: 80-120px
- Accessibility: respect prefers-reduced-motion

[CUSTOM @KEYFRAMES]:
- alubram-shimmer: background-position animation
- alubram-float: translateY loop
- alubram-pulse-gold: box-shadow pulse
- alubram-count-up: opacity + translateY

[EXPECTED OUTPUT]:
- AOS initialization code (TypeScript)
- Custom @keyframes CSS
- Intersection Observer dla counter
- Parallax JS (vanilla, no jQuery)
- prefers-reduced-motion media query
```

---

## 7. Prompty do Security

### 7.1 Full Security Audit

```markdown
[TASK]: Przeprowadź pełny audyt bezpieczeństwa motywu

[CONTEXT]:
- Production environment (Austria, DSGVO)
- WordPress 6.9 + PHP 8.2
- Motyw: alubramat-child

[AUDIT SCOPE]:
### File Security
- [ ] All template files: if (!defined('ABSPATH')) { exit; }
- [ ] No sensitive data in repo (wp-config.php, .env)
- [ ] File permissions correct (644 files, 755 directories)

### Input Handling
- [ ] All $_POST/$_GET sanitized
- [ ] Nonce verification on all forms
- [ ] File upload validation (type, size, extension)
- [ ] Capability checks (current_user_can)

### Output Escaping
- [ ] esc_html() for text
- [ ] esc_url() for URLs
- [ ] esc_attr() for attributes
- [ ] wp_kses_post() for HTML content

### Database Security
- [ ] $wpdb->prepare() for custom queries
- [ ] No raw SQL (use WP_Query)
- [ ] Proper user input validation before DB

### XSS Prevention
- [ ] No inline JavaScript
- [ ] Nonce for AJAX requests
- [ ] Content-Security-Policy headers

### CSRF Protection
- [ ] wp_nonce_field() on all forms
- [ ] wp_verify_nonce() on submission
- [ ] AJAX nonces (wp_create_nonce)

[EXPECTED OUTPUT]:
- Security audit report (critical/high/medium/low)
- Lista wszystkich vulnerabilities z liniami kodu
- Konkretne fixy z kodem
- Overall security score (0-100)
- Hardening recommendations
```

### 7.2 DSGVO Compliance Check

```markdown
[TASK]: Sprawdź zgodność z DSGVO (RODO)

[CONTEXT]:
- Rynek: Austria (de_AT)
- Strona: alubram.at
- Plugin: Borlabs Cookie

[CHECKLIST]:
### Cookie Consent
- [ ] Cookie banner przed załadowaniem trackerów
- [ ] Google Maps tylko po akceptacji
- [ ] Google Fonts hostowane lokalnie
- [ ] Analytics tylko po opt-in

### Privacy Policy
- [ ] Datenschutzerklärung kompletna
- [ ] Lista wszystkich pluginów z danymi
- [ ] Contact form: checkbox zgody
- [ ] Prawo do usunięcia danych

### Data Handling
- [ ] Formularz: dane szyfrowane w transit
- [ ] Email z formularza: encryption
- [ ] Brak danych osobowych w analytics
- [ ] Data retention policy

### User Rights
- [ ] Right to access implemented
- [ ] Right to erasure (delete data)
- [ ] Right to rectification
- [ ] Data portability

[EXPECTED OUTPUT]:
- DSGVO compliance report
- Lista naruszeń z priorytetami
- Konkretne fixy
- Template Datenschutzerklärung
```

---

## 8. Prompty do Debugowania

### 8.1 PHP Error Debugging

```markdown
[TASK]: Zdebuguj błąd PHP — [description]

[ERROR INFO]:
- Error message: [wklej pełny błąd]
- File: [nazwa_pliku.php]
- Line: [numer_linii]
- Stack trace: [wklej jeśli dostępny]

[CONTEXT]:
- Co robiłeś przed wystąpieniem błędu?
- Jakie zmiany były wprowadzone?
- Środowisko: local/staging/production

[ATTEMPTED FIXES]:
- [ ] Włączono WP_DEBUG
- [ ] Sprawdzono error log
- [ ] Wyłączono wszystkie pluginy
- [ ] Przelączono na default theme

[EXPECTED OUTPUT]:
- Root cause analysis
- Konkretne rozwiązanie z kodem
- Jak zapobiec w przyszłości
```

### 8.2 JavaScript/TypeScript Debugging

```markdown
[TASK]: Zdebuguj błąd JavaScript — [description]

[ERROR INFO]:
- Console error: [wklej błąd]
- Browser: [Chrome/Firefox/Safari]
- URL: [gdzie występuje]
- Console log: [wklej output]

[CONTEXT]:
- Co powinno się dziać?
- Co się dzieje zamiast tego?
- Kiedy występuje (always/sometimes)?

[CODE SNIPPET]:
```typescript
// wklej relevant code
```

[EXPECTED OUTPUT]:
- Root cause analysis
- Fix z kodem
- Test case
```

### 8.3 Performance Issue Debugging

```markdown
[TASK]: Zdebuguj problem z wydajnością — [description]

[SYMPTOMS]:
- Page load time: [X]s (target: < 2.5s)
- LCP: [X]s (target: < 2.5s)
- CLS: [X] (target: < 0.1)
- INP: [X]ms (target: < 100ms)

[LIGHTHOUSE REPORT]:
- Overall score: [X]/100
- Performance: [X]/100
- Largest Contentful Paint: [X]s
- Cumulative Layout Shift: [X]
- Total Blocking Time: [X]ms

[WATERFALL ANALYSIS]:
- Slowest resources: [lista]
- Render-blocking: [CSS/JS]
- Large images: [lista]

[EXPECTED OUTPUT]:
- Bottleneck identification
- Prioritized fix list
- Estimated impact per fix
```

---

## 9. Prompty do Dokumentacji

### 9.1 Code Documentation

```markdown
[TASK]: Udokumentuj kod w pliku [nazwa_pliku.php]

[CONTEXT]:
- Plik: [ścieżka do pliku]
- Zawartość: [krótki opis funkcji]

[REQUIREMENTS]:
- PHPDoc dla każdej funkcji/klasy
- @package, @version, @author tags
- @param dla każdego argumentu (z typem)
- @return z typem i opisem
- @since dla nowych funkcji
- Inline comments dla skomplikowanej logiki
- Przykłady użycia w komentarzach

[EXPECTED OUTPUT]:
- Pełny plik z PHPDoc
- Inline comments
- Przykłady użycia
```

### 9.2 User Documentation

```markdown
[TASK]: Napisz dokumentację użytkownika dla [feature]

[AUDIENCE]:
- Client: ALUBRAM GMBH (non-technical)
- Language: German (de_AT)
- Level: Basic WordPress knowledge

[FEATURE]:
- Name: [nazwa feature]
- Purpose: [do czego służy]
- Location: [gdzie w WP-Admin]

[SECTIONS NEEDED]:
1. Overview (co to jest)
2. How to use (step-by-step)
3. Settings/options
4. Troubleshooting
5. FAQ

[FORMAT]:
- Markdown z screenshotami
- Numerowane kroki
- Wyróżnione ważne informacje (⚠️, ✅)
- Glossary terminów

[EXPECTED OUTPUT]:
- Kompletna dokumentacja w Markdown
- Miejsca na screenshoty oznaczone
- Linki do powiązanych dokumentów
```

---

## 10. Best Practices

### 10.1 Jak Pisać Efektywne Prompty

✅ **DO:**
- Bądź konkretny i precyzyjny
- Podawaj kontekst projektu
- Określaj wymagania jakościowe
- Definiuj format outputu
- Podawaj przykłady/inspiracje
- Używaj struktury (TASK, CONTEXT, REQUIREMENTS)

❌ **DON'T:**
- "Napisz kod dla strony" — zbyt ogólny
- "Zrób jak na tamtej stronie" — bez konkretów
- "Zoptymalizuj wszystko" — brak zakresu
- Pisanie promptu bez kontekstu

### 10.2 Prompt Iteration

Jeśli pierwszy output nie jest idealny:

```markdown
[FOLLOW-UP]:
Dzięki za kod! Mam kilka uwag:

1. Zmień [X] na [Y] ponieważ [powód]
2. Dodaj [feature] z [wymagania]
3. Popraw [issue] — obecne rozwiązanie nie działa bo [dlaczego]

Proszę o zaktualizowaną wersję z uwzględnieniem powyższych punktów.
```

### 10.3 Context Management

Przy dużych zadaniach:

```markdown
[CONTEXT LOADING]:
Najpierw wczytaj i przeanalizuj:
1. TECHNICAL-SHEETS.md — główna instrukcja
2. BRAND-SETTINGS.md — kolory, fonty
3. DESIGN-SYSTEM.md — komponenty
4. ARCHITECTURE.md — struktura projektu

Dopiero potem generuj kod.
```

---

*README.prompts.md — ALUBRAM GMBH WordPress Project | v1.0.0 | 2026-02-26*
