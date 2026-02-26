# README.skills.md — Skills & Capabilities Documentation

> **Dokument:** Katalog umiejętności, kompetencji i capabilities projektu
> **Projekt:** `piotroq/alubram-gmbh-wordpress`
> **Wersja:** 1.0.0 | 2026-02-26

---

## 📋 Spis Treści

1. [Wprowadzenie](#1-wprowadzenie)
2. [Technical Skills](#2-technical-skills)
3. [WordPress Skills](#3-wordpress-skills)
4. [Frontend Skills](#4-frontend-skills)
5. [Backend Skills](#5-backend-skills)
6. [SEO & Marketing Skills](#6-seo--marketing-skills)
7. [Security Skills](#7-security-skills)
8. [Soft Skills](#8-soft-skills)
9. [Tools & Software](#9-tools--software)
10. [Skills Matrix](#10-skills-matrix)

---

## 1. Wprowadzenie

### 1.1 Cel Dokumentu

Ten dokument definiuje wszystkie umiejętności, kompetencje i capabilities wymagane do skutecznego wykonania projektu ALUBRAM GMBH WordPress. Służy jako:

- **Checklist kompetencji** dla zespołu projektowego
- **Baza wiedzy** do onboardingu nowych developerów
- **Framework** do oceny jakości kodu
- **Guide** do identyfikacji gaps i potrzeb trainingowych

### 1.2 Poziomy Biegłości

| Poziom | Nazwa | Opis | Przykład |
|--------|-------|------|---------|
| **L1** | Fundamental | Podstawowa znajomość, wymaga nadzoru | HTML tags, CSS selectors |
| **L2** | Intermediate | Samodzielna praca w zakresie | WordPress themes, PHP functions |
| **L3** | Advanced | Pełna autonomia, mentoring | Architecture decisions, optimization |
| **L4** | Expert | Tworzenie best practices, innovation | System design, performance tuning |
| **L5** | Master | Industry recognition, thought leadership | Open-source contributions, speaking |

---

## 2. Technical Skills

### 2.1 Programming Languages

#### PHP 8.2+
**Poziom wymagany:** L4 (Expert)

**Kompetencje:**
- ✅ Strict types (`declare(strict_types=1)`)
- ✅ Type declarations (string, int, bool, array, nullable)
- ✅ Return type declarations
- ✅ Named arguments
- ✅ Match expressions
- ✅ Readonly properties
- ✅ Constructor property promotion
- ✅ Attributes (PHP 8.0+)
- ✅ JIT compilation awareness
- ✅ Error handling (try/catch, throw)
- ✅ Exception handling custom classes

**Przykłady użycia w projekcie:**
```php
<?php
declare(strict_types=1);

namespace Alubram\Theme;

class ProductQuery {
    public function __construct(
        private readonly string $category,
        private readonly int $limit = 10,
    ) {}

    public function getProducts(): array {
        return match ($this->category) {
            'zaune' => $this->getFences(),
            'tore' => $this->getGates(),
            default => [],
        };
    }
}
```

#### TypeScript 5.4+
**Poziom wymagany:** L3 (Advanced)

**Kompetencje:**
- ✅ Static typing (interfaces, types)
- ✅ Generics
- ✅ Utility types (Partial, Pick, Omit, Readonly)
- ✅ Type guards (typeof, instanceof, in)
- ✅ Conditional types
- ✅ Mapped types
- ✅ Decorators
- ✅ ES6+ features (async/await, destructuring, spread)
- ✅ Module resolution
- ✅ tsconfig.json configuration

**Przykłady użycia w projekcie:**
```typescript
interface Product {
  id: number;
  title: string;
  category: 'zaune' | 'tore' | 'carports' | 'ueberdachungen';
  price: number;
  deliveryTime: string;
}

type ProductCardProps = {
  product: Product;
  variant?: 'small' | 'medium' | 'large';
  onClick?: (id: number) => void;
};

export const ProductCard: React.FC<ProductCardProps> = ({
  product,
  variant = 'medium',
  onClick,
}) => {
  // Implementation
};
```

#### JavaScript ES6+
**Poziom wymagany:** L3 (Advanced)

**Kompetencje:**
- ✅ Arrow functions
- ✅ Template literals
- ✅ Destructuring assignment
- ✅ Spread/rest operators
- ✅ Promises, async/await
- ✅ Modules (import/export)
- ✅ Classes (ES6 classes)
- ✅ Map, Set, WeakMap, WeakSet
- ✅ Proxy, Reflect
- ✅ Iterators, generators

#### CSS3 / Tailwind CSS
**Poziom wymagany:** L4 (Expert)

**Kompetencje:**
- ✅ CSS Custom Properties (--var-name)
- ✅ Flexbox layout
- ✅ Grid layout
- ✅ Media queries (mobile-first)
- ✅ Animations (@keyframes)
- ✅ Transitions
- ✅ Transform (translate, scale, rotate)
- ✅ Pseudo-classes, pseudo-elements
- ✅ BEM naming convention
- ✅ Tailwind utility classes
- ✅ Tailwind config customization
- ✅ Responsive design patterns

### 2.2 Markup Languages

#### HTML5
**Poziom wymagany:** L4 (Expert)

**Kompetencje:**
- ✅ Semantic HTML (article, section, nav, aside, header, footer)
- ✅ Accessibility (ARIA roles, labels, live regions)
- ✅ Forms (input types, validation, attributes)
- ✅ Media (picture, source, video, audio)
- ✅ Meta tags (SEO, Open Graph, Twitter Cards)
- ✅ Structured data (Schema.org, JSON-LD)
- ✅ Performance (preload, prefetch, preconnect)
- ✅ Security (CSP, integrity, crossorigin)

---

## 3. WordPress Skills

### 3.1 Core Development
**Poziom wymagany:** L4 (Expert)

**Kompetencje:**
- ✅ Theme hierarchy understanding
- ✅ Template tags
- ✅ The Loop (WP_Query)
- ✅ Hooks system (actions, filters)
- ✅ Custom Post Types (register_post_type)
- ✅ Taxonomies (register_taxonomy)
- ✅ Meta boxes (add_meta_box)
- ✅ Options API (get_option, update_option)
- ✅ Transients API (get_transient, set_transient)
- ✅ REST API (register_rest_route)
- ✅ WP-CLI commands
- ✅ Multisite (optional)
- ✅ Gutenberg blocks (register_block_type)
- ✅ Block patterns, templates

**Przykłady użycia w projekcie:**
```php
// Custom Post Type Registration
add_action('init', function(): void {
    register_post_type('alubram_product', [
        'labels' => [
            'name' => 'Produkte',
            'singular_name' => 'Produkt',
            'add_new' => 'Neues Produkt',
            'add_new_item' => 'Neues Produkt hinzufügen',
            'edit_item' => 'Produkt bearbeiten',
        ],
        'public' => true,
        'has_archive' => true,
        'rewrite' => ['slug' => 'produkte'],
        'supports' => ['title', 'editor', 'thumbnail', 'excerpt', 'custom-fields'],
        'menu_icon' => 'dashicons-admin-generic',
        'show_in_rest' => true,
    ]);
});

// Custom Query with WP_Query
$args = [
    'post_type' => 'alubram_product',
    'posts_per_page' => 4,
    'tax_query' => [
        [
            'taxonomy' => 'product_category',
            'field' => 'slug',
            'terms' => ['zaune', 'tore'],
        ],
    ],
    'meta_query' => [
        [
            'key' => '_featured',
            'value' => '1',
            'compare' => '=',
        ],
    ],
];

$products = new WP_Query($args);
```

### 3.2 Theme Development
**Poziom wymagany:** L4 (Expert)

**Kompetencje:**
- ✅ Parent/child theme architecture
- ✅ functions.php bootstrap
- ✅ Template hierarchy
- ✅ get_template_part()
- ✅ load_template()
- ✅ Theme support (add_theme_support)
- ✅ Custom logo, header, background
- ✅ Navigation menus (register_nav_menus)
- ✅ Widgets, sidebars (register_sidebar)
- ✅ Customizer API
- ✅ Theme.json (block themes)

**Struktura motywu alubramat-child:**
```
alubramat-child/
├── style.css                 # Theme declaration + brand CSS
├── functions.php             # Bootstrap, includes
├── front-page.php            # Homepage template
├── page.php                  # Generic page
├── single.php                # Single post
├── archive.php               # Archive
├── header.php                # Site header
├── footer.php                # Site footer
├── 404.php                   # Error page
│
├── page-templates/           # Custom page templates
│   ├── page-uber-uns.php
│   ├── page-produkte.php
│   ├── page-referenzen.php
│   ├── page-leistungen.php
│   └── page-kontakt.php
│
├── template-parts/           # Reusable parts
│   ├── sections/             # Section components
│   │   ├── hero-homepage.php
│   │   ├── section-usps.php
│   │   └── ...
│   ├── components/           # UI components
│   │   ├── breadcrumbs.php
│   │   ├── product-card.php
│   │   └── ...
│   └── global/               # Global parts
│       ├── header-nav.php
│       └── footer-widgets.php
│
├── inc/                      # PHP includes
│   ├── custom-post-types.php
│   ├── taxonomies.php
│   ├── meta-boxes.php
│   ├── schema-markup.php
│   ├── enqueue.php
│   ├── nav-menus.php
│   ├── widgets.php
│   ├── shortcodes.php
│   └── ajax-handlers.php
│
└── assets/                   # Static assets
    ├── css/
    ├── js/
    └── images/
```

### 3.3 Plugin Development
**Poziom wymagany:** L3 (Advanced)

**Kompetencje:**
- ✅ Plugin header, bootstrap
- ✅ Activation/deactivation hooks
- ✅ Uninstall methods
- ✅ Plugin settings API
- ✅ Admin menus, pages
- ✅ Nonce verification
- ✅ Capability checks
- ✅ AJAX handlers (wp_ajax_, wp_ajax_nopriv_)
- ✅ REST API endpoints
- ✅ Background processing (wp_cron)
- ✅ Database tables (dbDelta)
- ✅ Internationalization (__(), _e(), _n())

### 3.4 Advanced Custom Fields (ACF)
**Poziom wymagany:** L3 (Advanced)

**Kompetencje:**
- ✅ Field groups (UI + PHP registration)
- ✅ Field types (text, textarea, image, gallery, repeater, flexible content)
- ✅ get_field(), the_field()
- ✅ have_rows(), the_sub_field() (repeaters)
- ✅ Conditional logic
- ✅ Options pages
- ✅ JSON save points
- ✅ Field validation
- ✅ Custom field types (optional)

**Przykład użycia w projekcie:**
```php
// Get single field
$delivery_time = get_field('delivery_time');

// Get image field
$image = get_field('hero_image');
if ($image) {
    echo wp_get_attachment_image($image['ID'], 'full');
}

// Repeater field
if (have_rows('technical_specs')):
    echo '<table class="specs-table">';
    while (have_rows('technical_specs')): the_row();
        $spec_name = get_sub_field('name');
        $spec_value = get_sub_field('value');
        echo "<tr><th>{$spec_name}</th><td>{$spec_value}</td></tr>";
    endwhile;
    echo '</table>';
endif;

// Gallery field
$images = get_field('gallery_images');
if ($images):
    foreach ($images as $image):
        echo wp_get_attachment_image($image['ID'], 'large');
    endforeach;
endif;
```

### 3.5 WooCommerce (Optional)
**Poziom wymagany:** L2 (Intermediate)

**Kompetencje:**
- ✅ Product types (simple, variable, grouped, external)
- ✅ Cart, checkout flow
- ✅ Payment gateways
- ✅ Shipping zones, methods
- ✅ Tax settings
- ✅ Order management
- ✅ Customer accounts
- ✅ Hooks (woocommerce_before_shop_loop, etc.)
- ✅ Template overrides

---

## 4. Frontend Skills

### 4.1 Responsive Design
**Poziom wymagany:** L4 (Expert)

**Kompetencje:**
- ✅ Mobile-first methodology
- ✅ Breakpoints strategy (640px, 768px, 1024px, 1280px, 1536px)
- ✅ Fluid typography (clamp())
- ✅ Fluid spacing (calc(), vw/vh)
- ✅ Container queries (modern browsers)
- ✅ Responsive images (srcset, sizes, picture)
- ✅ Touch-friendly UI (44px min tap target)
- ✅ Responsive tables
- ✅ Responsive videos (aspect-ratio)

**Przykład mobile-first CSS:**
```css
/* Mobile first (default) */
.alubram-section {
    padding: 40px 0;
    font-size: 16px;
}

.alubram-grid {
    grid-template-columns: 1fr;
    gap: 1.5rem;
}

/* Tablet ≥ 768px */
@media (min-width: 768px) {
    .alubram-section {
        padding: 60px 0;
        font-size: 18px;
    }

    .alubram-grid {
        grid-template-columns: repeat(2, 1fr);
        gap: 2rem;
    }
}

/* Desktop ≥ 1024px */
@media (min-width: 1024px) {
    .alubram-section {
        padding: 80px 0;
    }

    .alubram-grid {
        grid-template-columns: repeat(4, 1fr);
    }
}

/* Large Desktop ≥ 1280px */
@media (min-width: 1280px) {
    .alubram-section {
        padding: 100px 0;
    }
}
```

### 4.2 Animation
**Poziom wymagany:** L3 (Advanced)

**Kompetencje:**
- ✅ CSS transitions
- ✅ CSS animations (@keyframes)
- ✅ AOS (Animate On Scroll) library
- ✅ Intersection Observer API
- ✅ RequestAnimationFrame
- ✅ Transform (translate, scale, rotate, skew)
- ✅ Opacity animations
- ✅ Stagger animations
- ✅ Scroll-triggered animations
- ✅ Parallax effects
- ✅ Performance (will-change, transform/opacity only)

**AOS Configuration:**
```typescript
// assets/ts/main.ts
import AOS from 'aos';

AOS.init({
    duration: 800,
    easing: 'ease-in-out-cubic',
    once: true,
    offset: 80,
    delay: 0,
    anchorPlacement: 'top-bottom',
});

// Custom animation on scroll
const observer = new IntersectionObserver(
    (entries) => {
        entries.forEach((entry) => {
            if (entry.isIntersecting) {
                entry.target.classList.add('animate-count-up');
                observer.unobserve(entry.target);
            }
        });
    },
    { threshold: 0.5 }
);

document.querySelectorAll('[data-count]').forEach((el) => {
    observer.observe(el);
});
```

### 4.3 Accessibility (WCAG 2.1)
**Poziom wymagany:** L3 (Advanced)

**Kompetencje:**
- ✅ WCAG 2.1 Level AA compliance
- ✅ Semantic HTML
- ✅ ARIA roles, states, properties
- ✅ Keyboard navigation
- ✅ Focus management
- ✅ Skip links
- ✅ Alt text for images
- ✅ Form labels, error messages
- ✅ Color contrast (4.5:1 for text, 3:1 for large)
- ✅ Screen reader testing (NVDA, VoiceOver)
- ✅ prefers-reduced-motion
- ✅ prefers-color-scheme (dark mode prep)

**Accessibility Checklist:**
```markdown
### Perceivable
- [ ] Alt text for all images
- [ ] Captions for videos
- [ ] Color contrast ≥ 4.5:1
- [ ] Text resizable to 200%
- [ ] Content reflowable (no horizontal scroll)

### Operable
- [ ] All functionality keyboard accessible
- [ ] No keyboard traps
- [ ] Skip to main content link
- [ ] Focus visible on all elements
- [ ] No seizures (no flashing > 3x/sec)
- [ ] Enough time to read content

### Understandable
- [ ] Language declared (lang="de")
- [ ] Consistent navigation
- [ ] Consistent identification
- [ ] Error prevention (forms)
- [ ] Error suggestions
- [ ] Labels for form fields

### Robust
- [ ] Valid HTML
- [ ] Valid CSS
- [ ] ARIA used correctly
- [ ] Name, role, value for custom UI
- [ ] Status messages announced
```

### 4.4 Performance Optimization
**Poziom wymagany:** L4 (Expert)

**Kompetencje:**
- ✅ Core Web Vitals (LCP, FID/INP, CLS)
- ✅ Critical CSS
- ✅ Lazy loading (images, iframes, JS)
- ✅ Image optimization (AVIF, WebP, srcset)
- ✅ Font optimization (font-display: swap, preload)
- ✅ Script optimization (defer, async, module)
- ✅ Resource hints (preload, prefetch, preconnect)
- ✅ Code splitting
- ✅ Tree shaking
- ✅ Minification (CSS, JS, HTML)
- ✅ Gzip/Brotli compression
- ✅ Browser caching (Cache-Control headers)
- ✅ CDN usage

**Performance Targets:**
| Metryka | Target | Strategia |
|---------|--------|-----------|
| **LCP** | < 2.5s | Hero image preload, critical CSS inline, server response < 200ms |
| **FID/INP** | < 100ms | Defer non-critical JS, Web Worker dla heavy tasks |
| **CLS** | < 0.1 | Explicit width/height na img, font-display: swap, reserve space |
| **TTFB** | < 200ms | Server-side caching (WP Rocket), OPcache, CDN |
| **PageSpeed Mobile** | ≥ 90/100 | Wszystkie powyższe + image compression |
| **PageSpeed Desktop** | ≥ 95/100 | Wszystkie powyższe |

---

## 5. Backend Skills

### 5.1 Database (MySQL/MariaDB)
**Poziom wymagany:** L3 (Advanced)

**Kompetencje:**
- ✅ WordPress database schema
- ✅ WP_Query optimization
- ✅ $wpdb class (prepare, insert, update, delete)
- ✅ Indexes, query optimization
- ✅ EXPLAIN analysis
- ✅ Query caching
- ✅ Database transactions
- ✅ Backup, restore
- ✅ Migration scripts
- ✅ Custom tables (dbDelta)

**Przykład optymalizacji zapytania:**
```php
// ❌ ŹLE - N+1 query problem
$products = get_posts(['post_type' => 'alubram_product']);
foreach ($products as $product) {
    $price = get_post_meta($product->ID, '_price', true); // Query per product!
}

// ✅ DOBRZE - Single query z meta_query
$args = [
    'post_type' => 'alubram_product',
    'posts_per_page' => -1,
    'meta_query' => [
        [
            'key' => '_price',
            'value' => 0,
            'compare' => '>',
            'type' => 'NUMERIC',
        ],
    ],
    'fields' => 'ids', // Tylko ID, nie pełne obiekty
];
$products = get_posts($args);
```

### 5.2 API Development
**Poziom wymagany:** L3 (Advanced)

**Kompetencje:**
- ✅ WordPress REST API
- ✅ Custom endpoints (register_rest_route)
- ✅ Authentication (cookie, nonce, application passwords)
- ✅ Authorization (permissions_callback)
- ✅ Request validation
- ✅ Response formatting
- ✅ Error handling
- ✅ CORS configuration
- ✅ Rate limiting
- ✅ API documentation (Swagger/OpenAPI optional)

**Przykład custom REST endpoint:**
```php
add_action('rest_api_init', function(): void {
    register_rest_route('alubram/v1', '/products', [
        'methods' => 'GET',
        'callback' => function(WP_REST_Request $request): WP_REST_Response {
            $category = $request->get_param('category');
            $limit = $request->get_param('limit') ?? 10;

            $args = [
                'post_type' => 'alubram_product',
                'posts_per_page' => (int) $limit,
            ];

            if ($category) {
                $args['tax_query'] = [
                    [
                        'taxonomy' => 'product_category',
                        'field' => 'slug',
                        'terms' => $category,
                    ],
                ];
            }

            $products = get_posts($args);

            return new WP_REST_Response([
                'success' => true,
                'data' => $products,
            ], 200);
        },
        'permission_callback' => '__return_true', // Public endpoint
    ]);
});
```

### 5.3 Caching Strategies
**Poziom wymagany:** L4 (Expert)

**Kompetencje:**
- ✅ Object cache (wp_cache_get, wp_cache_set)
- ✅ Transients API (get_transient, set_transient)
- ✅ Site transients (network-wide)
- ✅ Fragment caching
- ✅ Query caching
- ✅ Browser caching (headers)
- ✅ Page caching (WP Rocket)
- ✅ CDN caching
- ✅ Cache invalidation strategies
- ✅ Redis/Memcached integration

**Przykład cache'owania:**
```php
// Transient cache dla featured products
function alubram_get_featured_products(): array {
    $cache_key = 'alubram_featured_products';
    $products = get_transient($cache_key);

    if (false === $products) {
        $args = [
            'post_type' => 'alubram_product',
            'posts_per_page' => 4,
            'meta_query' => [
                [
                    'key' => '_featured',
                    'value' => '1',
                    'compare' => '=',
                ],
            ],
        ];

        $products = get_posts($args);

        // Cache for 6 hours
        set_transient($cache_key, $products, 6 * HOUR_IN_SECONDS);
    }

    return $products;
}

// Invalidate cache on product update
add_action('save_post_alubram_product', function($post_id): void {
    delete_transient('alubram_featured_products');
});
```

---

## 6. SEO & Marketing Skills

### 6.1 Technical SEO
**Poziom wymagany:** L4 (Expert)

**Kompetencje:**
- ✅ Site architecture, URL structure
- ✅ XML sitemaps
- ✅ Robots.txt
- ✅ Canonical URLs
- ✅ Redirects (301, 302, 307)
- ✅ Schema.org structured data
- ✅ Open Graph, Twitter Cards
- ✅ Hreflang (multi-language)
- ✅ Pagination (rel="next", rel="prev")
- ✅ Breadcrumbs
- ✅ 404 handling
- ✅ Site speed optimization
- ✅ Mobile-first indexing
- ✅ Core Web Vitals

**Schema.org Implementation:**
```php
// inc/schema-markup.php
add_action('wp_head', function(): void {
    if (is_front_page()) {
        $schema = [
            '@context' => 'https://schema.org',
            '@type' => ['LocalBusiness', 'Manufacturer'],
            'name' => 'ALUBRAM GMBH',
            'url' => home_url('/'),
            'logo' => get_stylesheet_directory_uri() . '/assets/images/logo.svg',
            'image' => get_stylesheet_directory_uri() . '/assets/images/og-image.jpg',
            'description' => 'Hersteller von hochwertigen Aluminiumzäunen, Toren, Carports und Überdachungen.',
            'address' => [
                '@type' => 'PostalAddress',
                'streetAddress' => 'Hintere Ortsstraße 31',
                'addressLocality' => 'Himberg bei Wien',
                'postalCode' => '2325',
                'addressCountry' => 'AT',
            ],
            'telephone' => '+43223584793',
            'email' => 'himberg@alubram.at',
            'openingHours' => 'Mo-Su 00:00-24:00',
            'priceRange' => '€€€',
        ];

        echo '<script type="application/ld+json">' . wp_json_encode($schema, JSON_UNESCAPED_UNICODE | JSON_PRETTY_PRINT) . '</script>';
    }
}, 10);
```

### 6.2 On-Page SEO
**Poziom wymagany:** L4 (Expert)

**Kompetencje:**
- ✅ Keyword research (DE/AT market)
- ✅ Keyword density (1.5-2.5%)
- ✅ Title tags (50-60 chars)
- ✅ Meta descriptions (150-160 chars)
- ✅ Heading hierarchy (H1, H2, H3)
- ✅ Content optimization (800+ words per product page)
- ✅ Internal linking strategy
- ✅ Image optimization (alt text, file names)
- ✅ URL optimization (short, descriptive, keyword-rich)
- ✅ Readability (Flesch score for German)

### 6.3 Local SEO (Austria)
**Poziom wymagany:** L3 (Advanced)

**Kompetencje:**
- ✅ Google Business Profile optimization
- ✅ Local citations (Austrian directories)
- ✅ NAP consistency (Name, Address, Phone)
- ✅ Local keywords (Wien, Österreich, Himberg)
- ✅ German language SEO (de_AT, de_DE)
- ✅ Review management
- ✅ Local backlinks

---

## 7. Security Skills

### 7.1 WordPress Security
**Poziom wymagany:** L4 (Expert)

**Kompetencje:**
- ✅ Nonce verification (wp_nonce_field, wp_verify_nonce)
- ✅ Capability checks (current_user_can)
- ✅ Input sanitization (sanitize_text_field, sanitize_email)
- ✅ Output escaping (esc_html, esc_url, esc_attr)
- ✅ SQL injection prevention ($wpdb->prepare)
- ✅ XSS prevention
- ✅ CSRF protection
- ✅ File upload security
- ✅ Security headers (CSP, X-Frame-Options, etc.)
- ✅ .htaccess hardening
- ✅ wp-config.php security
- ✅ Database security (unique prefixes, salts)

**Security Checklist:**
```markdown
### Authentication
- [ ] Strong passwords enforced
- [ ] Two-factor authentication available
- [ ] Login attempt limiting
- [ ] Password reset secure

### Authorization
- [ ] Proper user roles
- [ ] Capability checks on all actions
- [ ] Nonce verification on all forms
- [ ] AJAX nonces

### Input Validation
- [ ] All $_GET sanitized
- [ ] All $_POST sanitized
- [ ] File uploads validated (type, size)
- [ ] URL validation

### Output Escaping
- [ ] esc_html() for text
- [ ] esc_url() for URLs
- [ ] esc_attr() for attributes
- [ ] wp_kses_post() for HTML

### Database
- [ ] $wpdb->prepare() for all queries
- [ ] No raw SQL
- [ ] Unique table prefixes
- [ ] Secure salts/keys

### File Security
- [ ] File permissions (644 files, 755 dirs)
- [ ] Disable file editing in wp-admin
- [ ] Protect sensitive files (.htaccess)
- [ ] No sensitive data in repo
```

### 7.2 DSGVO (GDPR) Compliance
**Poziom wymagany:** L4 (Expert)

**Kompetencje:**
- ✅ Cookie consent (Borlabs Cookie)
- ✅ Privacy policy (Datenschutzerklärung)
- ✅ Data processing agreements
- ✅ Right to access
- ✅ Right to erasure
- ✅ Right to rectification
- ✅ Data portability
- ✅ Consent management
- ✅ Google Fonts local hosting
- ✅ Google Maps consent
- ✅ Analytics opt-in
- ✅ Form data encryption
- ✅ Data retention policies

---

## 8. Soft Skills

### 8.1 Communication
**Poziom wymagany:** L3 (Advanced)

**Kompetencje:**
- ✅ Clear technical writing (documentation)
- ✅ German language (de_AT, de_DE) — written
- ✅ English language — technical communication
- ✅ Client communication (non-technical explanations)
- ✅ Team collaboration (Git, code reviews)
- ✅ Active listening
- ✅ Feedback giving/receiving

### 8.2 Problem Solving
**Poziom wymagany:** L4 (Expert)

**Kompetencje:**
- ✅ Root cause analysis
- ✅ Systematic debugging
- ✅ Critical thinking
- ✅ Creative solutions
- ✅ Trade-off analysis
- ✅ Decision making under uncertainty

### 8.3 Time Management
**Poziom wymagany:** L3 (Advanced)

**Kompetencje:**
- ✅ Task prioritization (Eisenhower Matrix)
- ✅ Estimation accuracy
- ✅ Deadline management
- ✅ Context switching
- ✅ Deep work sessions
- ✅ Pomodoro technique

---

## 9. Tools & Software

### 9.1 Development Tools

| Kategoria | Narzędzie | Poziom |
|-----------|-----------|--------|
| **Code Editor** | VS Code, Cursor | L5 |
| **Version Control** | Git, GitHub | L5 |
| **Local Dev** | wp-env, XAMPP, Docker | L4 |
| **Database** | MySQL Workbench, phpMyAdmin, TablePlus | L4 |
| **FTP/SFTP** | FileZilla, Transmit | L4 |
| **Terminal** | iTerm2, Windows Terminal | L4 |

### 9.2 Design Tools

| Kategoria | Narzędzie | Poziom |
|-----------|-----------|--------|
| **UI Design** | Figma, Adobe XD | L3 |
| **Image Editing** | Photoshop, Affinity Photo | L3 |
| **Image Optimization** | Squoosh, ImageOptim | L4 |
| **Color Tools** | Coolors, Adobe Color | L3 |

### 9.3 Testing Tools

| Kategoria | Narzędzie | Poziom |
|-----------|-----------|--------|
| **Performance** | PageSpeed Insights, Lighthouse, WebPageTest | L5 |
| **Accessibility** | axe DevTools, WAVE, NVDA | L4 |
| **SEO** | SEMrush, Ahrefs, Screaming Frog | L3 |
| **Browser Testing** | BrowserStack | L3 |

### 9.4 Project Management

| Kategoria | Narzędzie | Poziom |
|-----------|-----------|--------|
| **Task Management** | Jira, Trello, Asana | L4 |
| **Documentation** | Notion, Confluence | L4 |
| **Communication** | Slack, Microsoft Teams | L4 |
| **Time Tracking** | Toggl, Clockify | L3 |

---

## 10. Skills Matrix

### 10.1 Required Skills per Role

| Skill | WordPress Dev | Frontend Dev | Backend Dev | Full-Stack |
|-------|--------------|-------------|-------------|------------|
| PHP 8.2+ | L4 | L2 | L5 | L4 |
| TypeScript | L2 | L4 | L3 | L4 |
| WordPress Core | L5 | L3 | L4 | L5 |
| Tailwind CSS | L3 | L5 | L2 | L4 |
| MySQL | L3 | L1 | L4 | L3 |
| SEO | L4 | L3 | L3 | L4 |
| Security | L4 | L3 | L4 | L4 |
| Accessibility | L4 | L5 | L2 | L4 |
| Performance | L4 | L4 | L4 | L5 |

### 10.2 Skills Assessment

**Self-Assessment Template:**

```markdown
## Skill: [Nazwa Umiejętności]

### Current Level: L1 / L2 / L3 / L4 / L5

### Evidence:
- [Project/Task 1]: [Description of what you did]
- [Project/Task 2]: [Description of what you did]

### Gaps:
- [What you need to learn/improve]

### Action Plan:
1. [Action item 1] - [Deadline]
2. [Action item 2] - [Deadline]

### Resources:
- [Book/Course/Article 1]
- [Book/Course/Article 2]
```

### 10.3 Learning Path

**For Junior Developer (L1 → L2):**
```
Month 1-2: PHP Basics + WordPress Fundamentals
Month 3-4: Theme Development + ACF
Month 5-6: Frontend (Tailwind, AOS) + Basic SEO
```

**For Mid Developer (L2 → L3):**
```
Month 1-2: Advanced WordPress (CPT, REST API)
Month 3-4: TypeScript + Performance Optimization
Month 5-6: Security + Accessibility
```

**For Senior Developer (L3 → L4):**
```
Month 1-2: System Architecture + Caching Strategies
Month 3-4: Advanced SEO + DSGVO Compliance
Month 5-6: Mentoring + Code Review Leadership
```

---

*README.skills.md — ALUBRAM GMBH WordPress Project | v1.0.0 | 2026-02-26*
