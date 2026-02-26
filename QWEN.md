# QWEN.md — Qwen AI Configuration & Instructions

> **Dokument:** Konfiguracja i instrukcje dla Qwen AI w projekcie ALUBRAM GMBH
> **Projekt:** `piotroq/alubram-gmbh-wordpress`
> **Model:** Qwen 2.5 Coder / Qwen Max
> **Wersja:** 1.0.0 | 2026-02-26

---

## 📋 Spis Treści

1. [Wprowadzenie](#1-wprowadzenie)
2. [Konfiguracja Qwen AI](#2-konfiguracja-qwen-ai)
3. [Kontekst Projektu](#3-kontekst-projektu)
4. [Zasady Generowania Kodu](#4-zasady-generowania-kodu)
5. [Workflow Pracy](#5-workflow-pracy)
6. [Przykładowe Prompty](#6-przykładowe-prompty)
7. [Best Practices](#7-best-practices)
8. [Rozwiązywanie Problemów](#8-rozwiązywanie-problemów)

---

## 1. Wprowadzenie

### 1.1 O Qwen AI

**Qwen** to zaawansowany model AI opracowany przez Alibaba Cloud, specjalizujący się w:
- ✅ Generowaniu kodu (PHP, TypeScript, CSS, JavaScript)
- ✅ Analizie i refaktoryzacji kodu
- ✅ Dokumentacji technicznej
- ✅ Rozwiązywaniu problemów programistycznych
- ✅ Wielojęzycznej komunikacji (PL/DE/EN)

### 1.2 Zastosowanie w Projekcie ALUBRAM GMBH

Qwen AI jest używany do:
- Generowania kompletnych plików PHP (templates, functions, includes)
- Tworzenia komponentów TypeScript/JavaScript
- Pisania stylów CSS z brand variables
- Generowania dokumentacji technicznej
- Code review i debugging
- Optymalizacji performance

### 1.3 Model Selection

| Zadanie | Model | Powód |
|---------|-------|-------|
| Generowanie kodu PHP | Qwen 2.5 Coder 32B | Najlepszy do code generation |
| Code review | Qwen 2.5 Coder 32B | Detailed analysis |
| Dokumentacja | Qwen Max | Długi context, dobre wyjaśnienia |
| Debugowanie | Qwen 2.5 Coder 32B | Precise error detection |
| Tłumaczenia DE/PL | Qwen Max | Multilingual support |

---

## 2. Konfiguracja Qwen AI

### 2.1 Dostęp przez Alibaba Cloud

```bash
# Konfiguracja API key
export DASHSCOPE_API_KEY="your-api-key-here"

# Instalacja SDK (Python)
pip install dashscope

# Przykład użycia
python -c "import dashscope; print(dashscope.Generation.call('qwen-max', 'Hello'))"
```

### 2.2 Dostęp przez Ollama (Local)

```bash
# Pull modelu Qwen
ollama pull qwen2.5-coder:32b

# Uruchomienie
ollama run qwen2.5-coder:32b

# API endpoint
# http://localhost:11434/api/generate
```

### 2.3 Konfiguracja w VS Code (Continue.dev)

```json
// .continue/config.json
{
  "models": [
    {
      "title": "Qwen 2.5 Coder",
      "provider": "ollama",
      "model": "qwen2.5-coder:32b"
    },
    {
      "title": "Qwen Max",
      "provider": "dashscope",
      "model": "qwen-max"
    }
  ]
}
```

### 2.4 Environment Variables

```bash
# .env (nie commitować do repozytorium)
DASHSCOPE_API_KEY=sk-xxxxxxxxxxxxxxxx
OLLAMA_HOST=http://localhost:11434
QWEN_MODEL=qwen2.5-coder:32b
QWEN_MAX_TOKENS=4096
QWEN_TEMPERATURE=0.2
```

---

## 3. Kontekst Projektu

### 3.1 Informacje o Firmie

**ZAWSZE wczytaj ten kontekst przed generowaniem kodu:**

```
FIRMA: ALUBRAM GMBH
BRANŻA: Producent aluminiowych ogrodzeń, bram, Carport, zadaszeń
RYNEK: DACH (Austria, Niemcy, Szwajcaria)
JĘZYK: Deutsch (de_AT)
SIEDZIBA: Hintere Ortsstraße 31, 2325 Himberg bei Wien, Austria
KONTAKT: +43 (0) 223 584 793 | himberg@alubram.at

USP:
✓ Direkt vom Hersteller (bez pośredników)
✓ Lieferung in 3–6 Wochen garantiert
✓ 24 Stunden · 7 Tage erreichbar
✓ Komplettservice: Beratung → Planung → Lieferung → Montage
✓ Aluminium: rostfrei, wartungsfrei, witterungsbeständig
```

### 3.2 Stack Technologiczny

```
CMS: WordPress 6.9
PHP: 8.2+ (strict_types=1, PSR-12)
TypeScript: ES6+, async/await
CSS: Tailwind CSS + Custom Properties (:root variables)
Biblioteki: AOS (animations), Swiper (sliders), Material Icons
```

### 3.3 Brand Colors

```css
Primary: #1A1A2E (Dark Navy)
Accent: #C8A96E (Gold/Champagne)
Secondary: #0F3460 (Deep Blue)
Light: #F8F6F1 (Warm White)
Dark: #0D0D0D (Almost Black)
```

### 3.4 Struktura Plików

```
alubramat-child/
├── style.css                 # Brand variables + CSS
├── functions.php             # Bootstrap
├── front-page.php            # Homepage
├── page.php                  # Generic page
├── header.php                # Header
├── footer.php                # Footer
│
├── page-templates/
│   ├── page-uber-uns.php
│   ├── page-produkte.php
│   ├── page-kontakt.php
│   └── ...
│
├── template-parts/
│   ├── sections/             # Sekcje
│   ├── components/           # Komponenty
│   └── global/               # Globalne
│
├── inc/                      # PHP includes
│   ├── custom-post-types.php
│   ├── schema-markup.php
│   └── ...
│
└── assets/
    ├── css/
    ├── js/
    └── images/
```

---

## 4. Zasady Generowania Kodu

### 4.1 PHP — Obowiązkowe Elementy

**Każdy plik PHP musi zawierać:**

```php
<?php
/**
 * Template Name: [Nazwa]
 * Template Post Type: page
 * @package alubramat-child
 * @version 1.0.0
 */

// Security check
if (!defined('ABSPATH')) {
    exit;
}

// Strict types
declare(strict_types=1);

// Reszta kodu...
```

### 4.2 Escape Functions

```php
// ZAWSZE używaj:
echo esc_html($text);           // Tekst
echo esc_url($url);             // URL
echo esc_attr($attribute);      // Atrybuty HTML
echo wp_kses_post($html);       // HTML z dozwolonymi tagami

// NIGDY nie rób:
echo $text;                     // ❌ XSS vulnerability!
```

### 4.3 Sanitize Functions

```php
// Formularze - ZAWSZE sanitizuj input:
$input = sanitize_text_field($_POST['field']);
$email = sanitize_email($_POST['email']);
$int = absint($_POST['number']);
$url = esc_url_raw($_POST['website']);

// Nonce verification:
if (!wp_verify_nonce($_POST['nonce'], 'alubram_form_action')) {
    wp_die('Security check failed', 'Error', ['response' => 403]);
}
```

### 4.4 TypeScript — Best Practices

```typescript
// ZAWSZE używaj typów:
interface Product {
    id: number;
    title: string;
    price: number;
    category: 'zaune' | 'tore' | 'carports';
}

// Async/await zamiast .then():
async function fetchProducts(): Promise<Product[]> {
    const response = await fetch('/wp-json/alubram/v1/products');
    return await response.json();
}

// Optional chaining:
const price = product?.offers?.price ?? 0;
```

### 4.5 CSS — Brand Variables

```css
/* ZAWSZE używaj brand variables z :root */
.alubram-btn {
    background: var(--color-primary);
    color: var(--color-white);
    padding: var(--spacing-4) var(--spacing-8);
    border-radius: var(--border-radius);
    transition: var(--transition-base);
}

/* NIGDY nie hardcode kolorów */
.alubram-btn {
    background: #1A1A2E;  /* ❌ ŹLE */
}
```

### 4.6 SEO & Schema.org

```php
// JSON-LD dla LocalBusiness (Homepage):
<script type="application/ld+json">
{
    "@context": "https://schema.org",
    "@type": ["LocalBusiness", "Manufacturer"],
    "name": "ALUBRAM GMBH",
    "url": "<?php echo esc_url(home_url('/')); ?>",
    "address": {
        "@type": "PostalAddress",
        "streetAddress": "Hintere Ortsstraße 31",
        "addressLocality": "Himberg bei Wien",
        "postalCode": "2325",
        "addressCountry": "AT"
    },
    "telephone": "+43223584793",
    "openingHours": "Mo-Su 00:00-24:00"
}
</script>
```

### 4.7 AOS Animations

```html
<!-- ZAWSZE dodawaj AOS attributes do sekcji -->
<section data-aos="fade-up" data-aos-delay="100" data-aos-duration="800">
    <h2>Unsere Produkte</h2>
</section>

<!-- Karty produktów -->
<article data-aos="zoom-in-up" data-aos-delay="200">
    <!-- content -->
</article>
```

### 4.8 Image Optimization

```html
<!-- ZAWSZE optymalizuj obrazy -->
<picture>
    <source type="image/avif"
            srcset="image-600.avif 600w, image-1200.avif 1200w"
            sizes="(max-width: 768px) 100vw, 50vw">
    <source type="image/webp"
            srcset="image-600.webp 600w, image-1200.webp 1200w"
            sizes="(max-width: 768px) 100vw, 50vw">
    <img src="image-1200.jpg"
         alt="Beschreibender Alt-Text auf Deutsch"
         loading="lazy"
         decoding="async"
         width="1200"
         height="800">
</picture>

<!-- Hero/LCP image: fetchpriority="high" -->
<img src="hero.jpg" fetchpriority="high" alt="Hero Image">
```

---

## 5. Workflow Pracy

### 5.1 Standardowy Proces

```
┌─────────────────────────────────────────────────────────────────┐
│                    QWEN AI WORKFLOW                             │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  1. LOAD CONTEXT                                                │
│     ├─ TECHNICAL-SHEETS.md                                     │
│     ├─ BRAND-SETTINGS.md                                       │
│     └─ ARCHITECTURE.md                                         │
│                                                                 │
│  2. UNDERSTAND TASK                                             │
│     ├─ Co jest wymagane?                                       │
│     ├─ Jaki typ pliku?                                         │
│     └─ Jakie są wymagania?                                     │
│                                                                 │
│  3. PLAN STRUCTURE                                              │
│     ├─ Struktura pliku                                         │
│     ├─ Dependencies                                            │
│     └─ Edge cases                                              │
│                                                                 │
│  4. GENERATE CODE                                               │
│     ├─ Kompletny kod                                           │
│     ├─ Z komentarzami                                          │
│     └─ Z PHPDoc/TypeScript types                               │
│                                                                 │
│  5. SELF-REVIEW                                                 │
│     ├─ PHP syntax check                                        │
│     ├─ Security check                                          │
│     ├─ Performance check                                       │
│     └─ Accessibility check                                     │
│                                                                 │
│  6. OUTPUT                                                      │
│     └─ Finalny kod + wyjaśnienie                               │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

### 5.2 Checklista Przed Outputem

```markdown
## Code Quality Checklist

### Security
- [ ] `if (!defined('ABSPATH')) { exit; }` — każdy plik template
- [ ] Wszystkie `echo` z `esc_html()`, `esc_url()`, `esc_attr()`
- [ ] Wszystkie `$_POST/$_GET` z `sanitize_*()`
- [ ] Nonce verification na formularzach
- [ ] Capability checks (`current_user_can()`)

### WordPress Standards
- [ ] `enqueue_scripts` hook dla CSS/JS
- [ ] `get_template_part()` dla include'ów
- [ ] CPT przez `register_post_type()`
- [ ] Tłumaczenia: `__()`, `_e()`, `esc_html__()`

### Performance
- [ ] `loading="lazy"` na obrazach
- [ ] `fetchpriority="high"` na LCP image
- [ ] `defer`/`async` na skryptach
- [ ] Minified CSS/JS

### Accessibility
- [ ] `alt` teksty na obrazach
- [ ] ARIA roles gdzie potrzebne
- [ ] Kontrast kolorów ≥ 4.5:1
- [ ] Keyboard navigation
```

---

## 6. Przykładowe Prompty

### 6.1 Generowanie Template PHP

```markdown
[TASK]: Wygeneruj kompletny plik `page-templates/page-kontakt.php`

[CONTEXT]:
- ALUBRAM GMBH — austriacki producent aluminiowych ogrodzeń
- Strona w języku niemieckim (de_AT)
- Dokumentacja: TECHNICAL-SHEETS.md, BRAND-SETTINGS.md

[REQUIREMENTS]:
- PSR-12, strict_types=1
- DSGVO compliant (Google Maps za cookie consent)
- AOS animations
- Mobile-first CSS
- AJAX contact form z walidacją

[SECTIONS]:
1. Hero z breadcrumbs
2. Dane kontaktowe (3 kolumny)
3. Formularz kontaktowy
4. Google Maps (placeholder przed consent)
5. CTA banner

[EXPECTED OUTPUT]:
- Kompletny plik PHP (700+ linii)
- Inline komentarze
- PHPDoc dla funkcji
- JSON-LD: LocalBusiness
```

### 6.2 Generowanie CPT

```markdown
[TASK]: Wygeneruj rejestrację CPT `alubram_product`

[CONTEXT]:
- Custom Post Type dla produktów ALUBRAM
- Pola ACF: category, material, delivery_time, warranty, price, gallery, specs, colors

[REQUIREMENTS]:
- register_post_type() z pełnym konfigurem
- Labels po niemiecku
- Taxonomie: product_category, product_material, product_color
- show_in_rest: true (Gutenberg support)
- Rewrite slug: 'produkte'

[EXPECTED OUTPUT]:
- Funkcja register_alubram_product_cpt()
- Hook: add_action('init', ...)
- Pełna tablica labels
- PHPDoc
```

### 6.3 Code Review

```markdown
[TASK]: Przeprowadź code review pliku front-page.php

[CHECKLIST]:
### Security
- [ ] if (!defined('ABSPATH')) { exit; }
- [ ] Wszystkie echo z esc_html()/esc_url()
- [ ] Nonce verification

### WordPress Standards
- [ ] get_template_part() usage
- [ ] Proper enqueue_scripts
- [ ] CPT queries optimized

### Performance
- [ ] Image lazy loading
- [ ] AOS attributes
- [ ] No render-blocking resources

[EXPECTED OUTPUT]:
- Lista issues (critical/high/medium/low)
- Konkretne linie kodu
- Sugerowane fixy
```

### 6.4 Debugowanie

```markdown
[TASK]: Zdebuguj błąd z formularzem kontaktowym

[ERROR]:
- Formularz nie wysyła danych
- Console: 500 Internal Server Error
- File: inc/ajax-handlers.php, line 45

[CODE SNIPPET]:
```php
add_action('wp_ajax_alubram_contact', 'handle_contact_form');
function handle_contact_form() {
    $email = $_POST['email'];  // Line 45
    // ...
}
```

[EXPECTED OUTPUT]:
- Root cause analysis
- Fix z kodem
- Jak zapobiec w przyszłości
```

---

## 7. Best Practices

### 7.1 Komunikacja z Qwen

✅ **DO:**
- Bądź konkretny i precyzyjny
- Podawaj kontekst projektu
- Określaj wymagania jakościowe
- Definiuj format outputu
- Podawaj przykłady

❌ **DON'T:**
- "Napisz kod dla strony" — zbyt ogólny
- "Zrób jak na tamtej stronie" — bez konkretów
- Pisanie bez kontekstu

### 7.2 Zarządzanie Kontekstem

Przy dużych zadaniach:

```markdown
[CONTEXT LOADING]:
Najpierw przeanalizuj:
1. TECHNICAL-SHEETS.md — główna instrukcja
2. BRAND-SETTINGS.md — kolory, fonty
3. ARCHITECTURE.md — struktura

Dopiero potem generuj kod.
```

### 7.3 Iteracja

Jeśli output nie jest idealny:

```markdown
[FOLLOW-UP]:
Dzięki! Mam kilka uwag:

1. Zmień [X] na [Y] ponieważ [powód]
2. Dodaj [feature] z [wymagania]
3. Popraw [issue] — obecne rozwiązanie nie działa

Proszę o zaktualizowaną wersję.
```

---

## 8. Rozwiązywanie Problemów

### 8.1 Częste Problemy

| Problem | Przyczyna | Rozwiązanie |
|---------|-----------|-------------|
| Kod nie działa | Brak context | Wczytaj TECHNICAL-SHEETS.md |
| Błędy składni | Zbyt ogólne prompt | Bądź bardziej precyzyjny |
| Zły styl | Brak brand info | Podaj BRAND-SETTINGS.md |
| Za krótki output | Limit tokenów | Zwiększ max_tokens |
| Halucynacje | Zbyt ogólne | Podaj konkretne wymagania |

### 8.2 Troubleshooting

```bash
# Problem: Qwen nie odpowiada
# Rozwiązanie: Sprawdź API status
curl -X POST http://localhost:11434/api/generate \
  -d '{"model": "qwen2.5-coder:32b", "prompt": "test"}'

# Problem: Zła jakość kodu
# Rozwiązanie: Dodaj więcej contextu
# Wczytaj: TECHNICAL-SHEETS.md + BRAND-SETTINGS.md

# Problem: Za krótkie odpowiedzi
# Rozwiązanie: Zwiększ max_tokens
export QWEN_MAX_TOKENS=8192
```

---

## 9. Qwen vs Claude — Kiedy Używać

| Zadanie | Qwen | Claude | Powód |
|---------|------|--------|-------|
| Code generation | ✅ | ✅ | Oba dobre |
| Code review | ✅ | ✅ | Qwen bardziej szczegółowy |
| Documentation | ✅ | ✅ | Claude lepszy styl |
| Debugging | ✅ | ✅ | Qwen szybszy |
| Long context | ❌ | ✅ | Claude 200k tokens |
| Polish language | ✅ | ✅ | Oba dobre |
| German language | ✅ | ✅ | Oba dobre |

---

*QWEN.md — ALUBRAM GMBH WordPress Project | v1.0.0 | 2026-02-26*
