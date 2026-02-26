# README.agents.md — AI Agents Documentation

> **Dokument:** Konfiguracja, role i workflow agentów AI w projekcie  
> **Projekt:** `piotroq/alubram-gmbh-wordpress`  
> **Modele:** Claude Sonnet 4.6 / Claude Opus 4.6  
> **Środowisko:** `.claude/agents/` · `.cursorrules/` · `.copilot/`  
> **Wersja:** 1.0.0 | 2026-02-26  

---

## 1. Przegląd Architektury Agentów

Projekt ALUBRAM GMBH WordPress używa wielowarstwowej konfiguracji agentów AI do wspomagania developmentu. Każdy agent ma ściśle zdefiniowaną rolę, priorytety i zakres działania.

```
┌─────────────────────────────────────────────────────────────────┐
│                    AI AGENT ECOSYSTEM                           │
│                                                                 │
│  ┌──────────────────┐  ┌──────────────────┐  ┌──────────────┐  │
│  │  Claude Sonnet   │  │  Claude Opus     │  │  Copilot     │  │
│  │  (primary)       │  │  (complex tasks) │  │  (autocomplete│  │
│  │                  │  │                  │  │  + PR review) │  │
│  │ • Code gen       │  │ • Architecture   │  │              │  │
│  │ • Reviews        │  │ • SEO strategy   │  │              │  │
│  │ • Docs           │  │ • Complex PHP    │  │              │  │
│  └──────────────────┘  └──────────────────┘  └──────────────┘  │
│           │                     │                              │
│           └─────────┬───────────┘                              │
│                     │                                          │
│          ┌──────────▼──────────┐                               │
│          │  Project Knowledge  │                               │
│          │  TECHNICAL-SHEETS   │                               │
│          │  ARCHITECTURE.md    │                               │
│          │  BRAND-SETTINGS.md  │                               │
│          │  DESIGN-SYSTEM.md   │                               │
│          └─────────────────────┘                               │
└─────────────────────────────────────────────────────────────────┘
```

---

## 2. Katalog `.claude/agents/`

### 2.1 Struktura katalogów

```
.claude/
├── agents/
│   ├── business-product/
│   │   └── wordpress-master.md       ← WordPress expert agent config
│   ├── code-review/
│   │   └── php-reviewer.md           ← PHP PSR-12 code review
│   ├── seo/
│   │   └── seo-de-specialist.md      ← SEO DE/AT specialist
│   ├── design/
│   │   └── ui-ux-designer.md         ← UI/UX design assistant
│   └── security/
│       └── wp-security-auditor.md    ← Security audit agent
├── settings.json                     ← Global Claude settings
└── CLAUDE.md                         ← Master instructions (symlink → TECHNICAL-SHEETS.md)
```

### 2.2 Agent: `wordpress-master` (Primary)

**Plik:** `.claude/agents/business-product/wordpress-master.md`

**Rola:** Senior Full-Stack WordPress Developer — główny agent projektowy.

**Zakres odpowiedzialności:**
- Generowanie plików PHP (templates, functions.php, includes)
- Code review pod kątem PSR-12, WordPress Coding Standards
- Implementacja Custom Post Types i taxonomii
- Schema.org JSON-LD markup
- AJAX handlers i REST API endpoints
- Performance optimization (enqueue, lazy load, cache)
- DSGVO compliance (formularz zgody, cookie handling)

**Triggery wywołania:**
```
- "Wygeneruj template..."
- "Stwórz sekcję..."
- "Zaimplementuj CPT..."
- "Napisz shortcode..."
- "Zoptymalizuj..."
- "Napraw błąd PHP..."
```

**Kontekst wymagany (zawsze wczytaj):**
1. `TECHNICAL-SHEETS.md` — główna instrukcja projektu
2. `ARCHITECTURE.md` — architektura techniczna
3. `BRAND-SETTINGS.md` — kolory, fonty, brand variables
4. `DESIGN-SYSTEM.md` — komponenty, klasy CSS

### 2.3 Agent: `php-reviewer`

**Plik:** `.claude/agents/code-review/php-reviewer.md`

**Rola:** PHP Code Reviewer — sprawdza zgodność z PSR-12 i WordPress Coding Standards.

**Checklist review:**

```markdown
## PHP Review Checklist

### Security
- [ ] `if (!defined('ABSPATH')) { exit; }` — każdy plik template
- [ ] Wszystkie echo: `esc_html()`, `esc_url()`, `esc_attr()`, `wp_kses_post()`
- [ ] Wszystkie $_POST/$_GET: `sanitize_text_field()`, `sanitize_email()`
- [ ] Formularze: `wp_nonce_field()` + `wp_verify_nonce()`
- [ ] Capability checks: `current_user_can()`
- [ ] SQL: `$wpdb->prepare()` dla custom queries

### WordPress Standards
- [ ] `enqueue_scripts` hook — nie bezpośredni `<script>` w template
- [ ] `get_template_part()` — dla include sekcji
- [ ] `wp_localize_script()` — dla danych PHP → JS
- [ ] `add_action()` / `add_filter()` — nie inline w templates
- [ ] CPT przez `register_post_type()` — nie własne tabele DB
- [ ] Translatable strings: `__()`, `_e()`, `esc_html__()`

### PHP 8.2+ Quality
- [ ] `declare(strict_types=1)` — w plikach z logiką
- [ ] Typy argumentów i return types: `string`, `int`, `void`, `?nullable`
- [ ] `readonly` properties gdzie możliwe
- [ ] Named arguments dla czytelności
- [ ] Match expressions zamiast switch (gdzie sensowne)
- [ ] Brak `@` error suppression

### Performance
- [ ] WP_Query z `'fields' => 'ids'` gdy tylko ID potrzebne
- [ ] Transient cache dla ciężkich queries
- [ ] `update_post_meta()` — batch gdzie możliwe
- [ ] Lazy loading img: `loading="lazy" decoding="async"`
- [ ] LCP image: `fetchpriority="high"`
```

### 2.4 Agent: `seo-de-specialist`

**Plik:** `.claude/agents/seo/seo-de-specialist.md`

**Rola:** SEO Specialist dla rynku DE/AT — optymalizacja treści i kodu.

**Zakres:**
- Generowanie SEO-optimized content (DE)
- Schema.org JSON-LD markup (LocalBusiness, Product, FAQ, BreadcrumbList)
- Meta tags (title, description, OG)
- Keyword density check (1.5–2.5%)
- Structura URL i internal linking

**Wzorzec tytułu stron:**
```
Homepage:   ALUBRAM GMBH | Aluminiumzäune & Tore Hersteller Österreich
Produkt:    Aluminium Zaunfelder kaufen | ALUBRAM GMBH – Direkt vom Hersteller
Kontakt:    Kontakt | ALUBRAM GMBH Himberg bei Wien – Kostenlose Beratung
```

**Wzorzec meta description:**
```
Max 155 znaków, zawiera: keyword + USP + CTA
Przykład: "Hochwertige Aluminiumzäune vom Hersteller. ✓ Lieferung in 3–6 Wochen 
           ✓ 24/7 erreichbar ✓ Montage inklusive. Jetzt kostenlos beraten lassen!"
```

### 2.5 Agent: `ui-ux-designer`

**Plik:** `.claude/agents/design/ui-ux-designer.md`

**Rola:** UI/UX Designer — generowanie komponentów CSS, sekcji, animacji.

**Zakres:**
- CSS komponenty (zgodne z DESIGN-SYSTEM.md)
- Animacje AOS i custom @keyframes
- Responsive layouts (mobile-first)
- Tailwind utility compositions
- Accessibility (WCAG 2.1 AA)

**Zasady designu:**
```
Styl: nowoczesny · premium · metaliczny · industrialno-elegancki
Inspiracje: arrea.at · selt.com/home-de · mbveranda.de
Efekty: parallax · hover cards · gradient overlays · smooth scroll
Animacje: AOS fade-up/zoom-in · CSS @keyframes shimmer/float/pulse
```

### 2.6 Agent: `wp-security-auditor`

**Plik:** `.claude/agents/security/wp-security-auditor.md`

**Rola:** Security Auditor — przegląd bezpieczeństwa kodu WordPress.

**Security Audit Checklist:**

```markdown
### Input/Output Security
- [ ] Brak SQL injection (parameterized queries)
- [ ] Brak XSS (escape wszystkich output)
- [ ] CSRF protection (nonce na wszystkich formularzach)
- [ ] File upload validation (typ, rozmiar, rozszerzenie)

### WordPress Hardening
- [ ] Wyłączony XML-RPC
- [ ] Ukryty WP version string
- [ ] Chroniony wp-admin (limit IP lub 2FA)
- [ ] Wyłączone file editing w wp-admin
- [ ] Silne hasła (enforce przez plugin)

### DSGVO / Privacy
- [ ] Cookie consent przed Google Analytics / Maps
- [ ] Google Fonts hostowane lokalnie
- [ ] Formularz: checkbox zgody DSGVO
- [ ] Dane osobowe: szyfrowane lub hash
- [ ] Prawo do usunięcia danych — implementacja

### Server Config
- [ ] HTTPS only (HSTS header)
- [ ] X-Frame-Options: SAMEORIGIN
- [ ] X-Content-Type-Options: nosniff
- [ ] Referrer-Policy: strict-origin-when-cross-origin
- [ ] Content-Security-Policy: zdefiniowana
```

---

## 3. Workflow Agenta — Standard Operating Procedure

### 3.1 Flowchart zadania

```
Otrzymanie taska
      │
      ▼
┌─────────────────────┐
│  1. Read Context    │
│  TECHNICAL-SHEETS   │ ← zawsze pierwsze
│  ARCHITECTURE.md    │
│  BRAND-SETTINGS.md  │
│  DESIGN-SYSTEM.md   │
└────────┬────────────┘
         │
         ▼
┌─────────────────────┐
│  2. Fetch URLs      │
│  GitHub repo        │ ← jeśli relevantne
│  Inspiracje         │
│  WP Docs            │
└────────┬────────────┘
         │
         ▼
┌─────────────────────┐
│  3. Plan (comment)  │
│  Struktura kodu     │
│  Dependencies       │
│  Edge cases         │
└────────┬────────────┘
         │
         ▼
┌─────────────────────┐
│  4. Generate Code   │
│  PHP · CSS · TS/JS  │
│  Kompletny plik     │
└────────┬────────────┘
         │
         ▼
┌─────────────────────┐
│  5. Mental Test     │
│  PHP syntax check   │
│  JS/TS types check  │
│  Security check     │
│  Accessibility      │
└────────┬────────────┘
         │
         ▼
┌─────────────────────┐
│  6. Self-Review     │
│  PSR-12 compliance  │
│  WP standards       │
│  Performance        │
└────────┬────────────┘
         │
         ▼
┌─────────────────────┐
│  7. Document        │
│  PHPDoc comments    │
│  Inline explanations│
│  Usage examples     │
└────────┬────────────┘
         │
         ▼
      Output:
  Finalny kod + wyjaśnienie + alternatywy
```

### 3.2 Priorytety przy konflikcie instrukcji

```
1. Bezpieczeństwo (security) — zawsze najwyższy priorytet
2. DSGVO compliance — wymóg prawny Austria
3. Accessibility WCAG 2.1 AA — standard
4. Performance (PageSpeed ≥ 90) — KPI projektu
5. SEO (Lighthouse 100) — KPI projektu
6. Brand consistency (BRAND-SETTINGS.md) — UX
7. Code quality (PSR-12) — maintainability
8. Feature completeness — developerski cel
```

---

## 4. Konfiguracja Cursor AI (`.cursorrules/`)

### 4.1 `.cursorrules` — główne reguły

```
.cursorrules/
├── php.mdc                 ← PHP rules (PSR-12, WP standards)
├── typescript.mdc          ← TypeScript rules (strict, ES6+)
├── css.mdc                 ← CSS rules (BEM, custom properties)
└── general.mdc             ← Ogólne reguły projektu
```

**Kluczowe reguły z `.cursorrules` (skrót):**

```yaml
# php.mdc
language: php
version: "8.2+"
standards:
  - PSR-12
  - WordPress-Coding-Standards
always_include:
  - "declare(strict_types=1);"
  - "if (!defined('ABSPATH')) { exit; }"
escape_functions:
  html: "esc_html()"
  url: "esc_url()"
  attr: "esc_attr()"
  html_content: "wp_kses_post()"
sanitize_functions:
  text: "sanitize_text_field()"
  email: "sanitize_email()"
  int: "absint()"

# typescript.mdc
language: typescript
strict: true
target: ES6
prefer:
  - async/await over promises.then()
  - const over let (when not reassigned)
  - arrow functions
  - optional chaining (?.)
  - nullish coalescing (??)
```

---

## 5. GitHub Copilot (`.copilot/`)

### 5.1 Konfiguracja Copilot

```
.copilot/
└── copilot-instructions.md    ← Instrukcje dla GitHub Copilot
```

**Główne instrukcje dla Copilot:**

```markdown
# GitHub Copilot Instructions — ALUBRAM GMBH WordPress

## Project Context
WordPress 6.9 theme (alubramat-child) for ALUBRAM GMBH Austria.
Language: German (DE). Premium aluminum fences/gates/carports manufacturer.

## Code Style
- PHP 8.2+, strict_types=1, PSR-12
- TypeScript (prefer over JS), ES6+, strict mode
- CSS: custom properties (--var-name), BEM naming (.alubram-component)
- Always: mobile-first CSS, WCAG 2.1 AA accessibility

## Brand Colors (use these in CSS suggestions)
--color-primary: #1A1A2E (Dark Navy)
--color-accent: #C8A96E (Gold/Champagne)
--color-secondary: #0F3460 (Deep Blue)

## Important Patterns
- Always escape output: esc_html(), esc_url(), esc_attr()
- Always sanitize input: sanitize_text_field(), sanitize_email()
- Nonces on all forms: wp_nonce_field() + wp_verify_nonce()
- AOS animations: data-aos="fade-up" data-aos-delay="100"
- Material Icons: <span class="material-symbols-outlined">icon_name</span>
- Images: loading="lazy" decoding="async" + srcset + sizes
- Hero/LCP image: fetchpriority="high"
```

---

## 6. Qwen AI Config (`.qwen/`)

```
.qwen/
└── qwen-instructions.md    ← Konfiguracja Qwen AI (alternatywny asystent)
```

Qwen używany jako backup dla zadań wymagających dużego context window (analiza całego motywu, refaktoring).

---

## 7. Schemas (`.schemas/`)

```
.schemas/
├── product-schema.json         ← JSON Schema dla CPT alubram_product
├── reference-schema.json       ← JSON Schema dla CPT alubram_reference
└── contact-form-schema.json    ← JSON Schema dla AJAX contact form payload
```

**Przykład — `product-schema.json`:**

```json
{
  "$schema": "http://json-schema.org/draft-07/schema",
  "$id": "alubram-product",
  "type": "object",
  "title": "ALUBRAM Product",
  "required": ["title", "category", "material", "delivery_time"],
  "properties": {
    "title":          { "type": "string", "minLength": 5, "maxLength": 100 },
    "category":       { "type": "string", "enum": ["zaune", "tore", "carports", "ueberdachungen"] },
    "material":       { "type": "string", "default": "Aluminium" },
    "delivery_time":  { "type": "string", "default": "3–6 Wochen" },
    "warranty_years": { "type": "integer", "minimum": 1, "maximum": 30 },
    "price_from":     { "type": "number", "minimum": 0 },
    "colors":         { "type": "array", "items": { "type": "string" } }
  }
}
```

---

## 8. Agent Prompting Best Practices

### 8.1 Jak konstruować prompt do agenta

```markdown
## Dobry prompt (template):

[TASK]: Wygeneruj kompletny plik PHP `page-templates/page-kontakt.php`

[CONTEXT]:
- Strona kontaktowa z formularzem AJAX + Google Maps
- Formularz: Name, Email, Tel, PLZ, Nachricht, Produktinteresse (dropdown), DSGVO checkbox
- Schema.org: LocalBusiness kontaktowy JSON-LD
- Sekcje: Hero z breadcrumbs, dane kontaktowe z ikonami MDI, formularz, mapa

[REQUIREMENTS]:
- PSR-12, strict_types=1
- DSGVO compliant (Google Maps za cookie consent)
- AOS animacje na sekcjach
- Mobile-first CSS (Tailwind + custom vars z BRAND-SETTINGS.md)
- AJAX submit (bez reload) + nonce WordPress
- Pełna walidacja client + server side

[EXPECTED OUTPUT]:
- Kompletny plik PHP (700+ linii)
- Z inline komentarzami przy logice AJAX
- PHPDoc dla funkcji pomocniczych
```

### 8.2 Czego NIE robić w promptach

```
❌ "Napisz kod dla strony kontaktowej" — zbyt ogólny
❌ "Popraw styl" — bez wskazania pliku i problemu
❌ "Zrób jak na arrea.at" — bez konkretyzacji elementu
❌ "Zoptymalizuj wszystko" — brak zakresu
```

---

## 9. Komunikacja między agentami (Multi-Agent)

W przypadku złożonych zadań wymagających koordynacji:

```
Przykład: "Stwórz stronę produktu z pełną SEO i schema"

1. seo-de-specialist:
   → Generuje meta tags, schema JSON-LD dla produktu, keywords
   → Output: SEO block PHP

2. ui-ux-designer:
   → Generuje CSS sekcji produktu, galeria Swiper, AOS
   → Output: CSS + HTML struktura sekcji

3. wordpress-master:
   → Integruje output obu agentów w kompletny single-alubram_product.php
   → Dodaje WP_Query, ACF field calls, breadcrumbs
   → Output: finalny plik PHP

4. php-reviewer:
   → Review finalnego pliku pod security + PSR-12
   → Output: lista issues (jeśli są) + approved sign-off
```

---

## 10. Model Selection Guide

| Task | Model | Powód |
|------|-------|-------|
| Generowanie krótkiego snipetu (< 100 linii) | Claude Sonnet 4.6 | Szybki, wydajny |
| Kompletny template PHP (200–600 linii) | Claude Sonnet 4.6 | Standardowe zadanie |
| Architektura, design decisions | Claude Opus 4.6 | Głębsze reasoning |
| Złożony refaktoring całego modułu | Claude Opus 4.6 | Więcej context |
| SEO copywriting (długie treści DE) | Claude Sonnet 4.6 | Wystarczający |
| Security audit całego theme | Claude Opus 4.6 | Dokładność |
| Code review snippetu | Claude Sonnet 4.6 | Quick review |
| Debugowanie trudnego bugu | Claude Opus 4.6 | Root cause analysis |

---

## 11. Changelog Agentów

| Wersja | Data | Zmiana |
|--------|------|--------|
| 1.0.0 | 2026-02-26 | Inicjalna konfiguracja wszystkich agentów |

---

*README.agents.md — ALUBRAM GMBH WordPress | v1.0.0 | 2026-02-26*  
*Modele: Claude Sonnet 4.6 / Claude Opus 4.6 | Repozytorium: piotroq/alubram-gmbh-wordpress*
