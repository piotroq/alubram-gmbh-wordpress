# DESIGN-SYSTEM.md — ALUBRAM GMBH

> **Dokument:** Design System — komponenty, wzorce, specyfikacje  
> **Projekt:** alubram-gmbh-wordpress · motyw `alubramat-child`  
> **Stack:** Tailwind CSS · Custom CSS (`:root` variables) · PHP templates  
> **Wersja:** 1.0.0 | 2026-02-26  

---

## 1. Przegląd Design System

Design System ALUBRAM GMBH definiuje wszystkie komponenty UI, wzorce layoutu, interakcje i zasady dostępności używane na stronie https://alubram.at.

System bazuje na:
- **CSS Custom Properties** (`--var-name`) — `style.css` motywu potomnego
- **Tailwind CSS utility classes** — layout, spacing, responsive
- **BEM-like naming** — `.alubram-[component]__[element]--[modifier]`
- **Mobile-first** — wszystkie style zaczynają się od mobile `<768px`

---

## 2. Layout System

### 2.1 Container

```html
<!-- PHP helper (functions.php) -->
<div class="alubram-container">
  <!-- content -->
</div>
```

```css
.alubram-container {
  width: 100%;
  max-width: var(--container-max);      /* 1280px */
  margin-inline: auto;
  padding-inline: 1.5rem;               /* 24px mobile */
}

@media (min-width: 1024px) {
  .alubram-container {
    padding-inline: 2rem;               /* 32px desktop */
  }
}

@media (min-width: 1280px) {
  .alubram-container {
    padding-inline: 2.5rem;             /* 40px large */
  }
}
```

**Tailwind equivalent:**
```html
<div class="max-w-screen-xl mx-auto px-6 lg:px-8 xl:px-10">
```

### 2.2 Section Wrapper

```html
<section class="alubram-section alubram-section--light">
  <div class="alubram-container">
    <!-- section content -->
  </div>
</section>
```

```css
.alubram-section {
  padding: var(--section-padding-mobile);      /* 40px 0 mobile */
}

@media (min-width: 768px) {
  .alubram-section { padding: 60px 0; }
}

@media (min-width: 1024px) {
  .alubram-section { padding: var(--section-padding); }  /* 80px 0 */
}

.alubram-section--light    { background: var(--color-light); }
.alubram-section--white    { background: var(--color-white); }
.alubram-section--dark     { background: var(--color-primary); }
.alubram-section--navy     { background: var(--gradient-primary); }
.alubram-section--gray     { background: var(--color-gray-100); }
.alubram-section--aluminum {
  background: linear-gradient(135deg, var(--color-gray-100) 0%, var(--color-gray-200) 100%);
}
```

### 2.3 Grid System

```html
<!-- 4-kolumnowy grid (produkty) -->
<div class="alubram-grid alubram-grid--4">
  <div class="alubram-grid__item">...</div>
  ...
</div>
```

```css
.alubram-grid {
  display: grid;
  gap: 1.5rem;
  grid-template-columns: 1fr;                    /* mobile: 1 col */
}

@media (min-width: 640px) {
  .alubram-grid--2, .alubram-grid--4 {
    grid-template-columns: repeat(2, 1fr);       /* sm: 2 cols */
  }
}

@media (min-width: 1024px) {
  .alubram-grid--3 { grid-template-columns: repeat(3, 1fr); }
  .alubram-grid--4 { grid-template-columns: repeat(4, 1fr); }
}

@media (min-width: 1024px) {
  .alubram-grid { gap: 2rem; }
}
```

---

## 3. Komponenty UI

### 3.1 Buttons

#### Primary Button (CTA główne)
```html
<a href="/kontakt/" class="alubram-btn alubram-btn--primary">
  <span>Jetzt kostenlos beraten lassen</span>
  <span class="material-symbols-outlined" aria-hidden="true">arrow_forward</span>
</a>
```

```css
.alubram-btn {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  padding: 0.875rem 2rem;
  font-family: var(--font-heading);
  font-size: var(--text-sm);
  font-weight: 600;
  letter-spacing: 0.05em;
  text-transform: uppercase;
  text-decoration: none;
  border-radius: var(--border-radius-md);
  cursor: pointer;
  border: 2px solid transparent;
  position: relative;
  overflow: hidden;
  transition: var(--transition-base);
  white-space: nowrap;
}

/* Primary — Gold fill */
.alubram-btn--primary {
  background: var(--gradient-gold);
  color: var(--color-primary);
  box-shadow: var(--shadow-gold);
}
.alubram-btn--primary:hover {
  transform: translateY(-2px);
  box-shadow: 0 8px 30px rgba(200, 169, 110, 0.45);
}

/* Shimmer effect on hover */
.alubram-btn--primary::after {
  content: '';
  position: absolute;
  inset: 0;
  background: linear-gradient(120deg, transparent 30%, rgba(255,255,255,0.2) 50%, transparent 70%);
  transform: translateX(-100%);
  transition: transform 0.6s ease;
}
.alubram-btn--primary:hover::after {
  transform: translateX(100%);
}

/* Secondary — Navy fill */
.alubram-btn--secondary {
  background: var(--color-primary);
  color: var(--color-white);
  border-color: var(--color-primary);
}
.alubram-btn--secondary:hover {
  background: var(--color-secondary);
  border-color: var(--color-secondary);
  transform: translateY(-2px);
}

/* Outline — Gold border */
.alubram-btn--outline {
  background: transparent;
  color: var(--color-accent);
  border-color: var(--color-accent);
}
.alubram-btn--outline:hover {
  background: var(--color-accent);
  color: var(--color-primary);
}

/* Ghost — White (hero) */
.alubram-btn--ghost {
  background: rgba(255, 255, 255, 0.1);
  color: var(--color-white);
  border-color: rgba(255, 255, 255, 0.5);
  backdrop-filter: blur(4px);
}
.alubram-btn--ghost:hover {
  background: rgba(255, 255, 255, 0.2);
  border-color: var(--color-white);
}

/* Size modifiers */
.alubram-btn--sm { padding: 0.625rem 1.25rem; font-size: var(--text-xs); }
.alubram-btn--lg { padding: 1.125rem 2.5rem; font-size: var(--text-base); }
```

### 3.2 Product Card

```html
<article class="alubram-card alubram-card--product"
         data-aos="zoom-in-up"
         data-aos-delay="100">

  <div class="alubram-card__image-wrap">
    <picture>
      <source type="image/avif" srcset="...">
      <img src="..." alt="Aluminium Zaunfeld Modern – ALUBRAM"
           loading="lazy" decoding="async" width="600" height="450">
    </picture>
    <div class="alubram-card__overlay">
      <a href="/produkte/zaune/" class="alubram-btn alubram-btn--ghost alubram-btn--sm">
        Mehr erfahren
      </a>
    </div>
    <span class="alubram-card__badge">Bestseller</span>
  </div>

  <div class="alubram-card__body">
    <span class="alubram-card__category">Zäune & Zaunfelder</span>
    <h3 class="alubram-card__title">Aluminium Zaunfeld Classic</h3>
    <p class="alubram-card__excerpt">Hochwertiges Aluminiumzaunfeld, wartungsfrei und rostfrei.</p>
    <div class="alubram-card__footer">
      <span class="alubram-card__price">ab € 89,–/lfm</span>
      <a href="/produkte/zaune/" class="alubram-card__link">Details →</a>
    </div>
  </div>
</article>
```

```css
.alubram-card {
  background: var(--color-white);
  border-radius: var(--border-radius-lg);
  overflow: hidden;
  box-shadow: var(--shadow-sm);
  transition: transform var(--transition-base), box-shadow var(--transition-base);
}
.alubram-card:hover {
  transform: translateY(-8px);
  box-shadow: var(--shadow-lg);
}

.alubram-card__image-wrap {
  position: relative;
  aspect-ratio: 4 / 3;
  overflow: hidden;
}
.alubram-card__image-wrap img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform var(--transition-slow);
}
.alubram-card:hover .alubram-card__image-wrap img {
  transform: scale(1.06);
}

.alubram-card__overlay {
  position: absolute;
  inset: 0;
  background: var(--gradient-card);
  display: flex;
  align-items: flex-end;
  justify-content: center;
  padding-bottom: 1.5rem;
  opacity: 0;
  transition: opacity var(--transition-base);
}
.alubram-card:hover .alubram-card__overlay { opacity: 1; }

.alubram-card__badge {
  position: absolute;
  top: 1rem;
  right: 1rem;
  background: var(--gradient-gold);
  color: var(--color-primary);
  font-size: var(--text-xs);
  font-weight: 700;
  padding: 0.25rem 0.75rem;
  border-radius: var(--border-radius-full);
  text-transform: uppercase;
  letter-spacing: 0.08em;
}

.alubram-card__body {
  padding: 1.5rem;
}

.alubram-card__category {
  font-size: var(--text-xs);
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.1em;
  color: var(--color-accent-dark);
}

.alubram-card__title {
  font-family: var(--font-heading);
  font-size: var(--text-xl);
  font-weight: 700;
  color: var(--color-primary);
  margin: 0.5rem 0;
}

.alubram-card__footer {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-top: 1rem;
  padding-top: 1rem;
  border-top: 1px solid var(--color-gray-200);
}

.alubram-card__price {
  font-weight: 700;
  color: var(--color-accent-dark);
  font-size: var(--text-lg);
}

.alubram-card__link {
  color: var(--color-primary);
  font-weight: 600;
  text-decoration: none;
  font-size: var(--text-sm);
  transition: color var(--transition-fast);
}
.alubram-card__link:hover { color: var(--color-accent-dark); }
```

### 3.3 USP Badge / Icon Item

```html
<div class="alubram-usp" data-aos="fade-up" data-aos-delay="200">
  <div class="alubram-usp__icon">
    <span class="material-symbols-outlined" aria-hidden="true">local_shipping</span>
  </div>
  <div class="alubram-usp__content">
    <h3 class="alubram-usp__title">3–6 Wochen Lieferzeit</h3>
    <p class="alubram-usp__text">Garantierte Lieferung direkt vom Hersteller</p>
  </div>
</div>
```

```css
.alubram-usp {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  padding: 2rem 1.5rem;
  gap: 1rem;
}

@media (min-width: 768px) {
  .alubram-usp--horizontal {
    flex-direction: row;
    text-align: left;
  }
}

.alubram-usp__icon {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 72px;
  height: 72px;
  border-radius: var(--border-radius-lg);
  background: linear-gradient(135deg, var(--color-primary) 0%, var(--color-secondary) 100%);
  flex-shrink: 0;
  box-shadow: var(--shadow-navy);
  transition: transform var(--transition-base), box-shadow var(--transition-base);
}

.alubram-usp:hover .alubram-usp__icon {
  transform: scale(1.1) rotate(3deg);
  box-shadow: var(--shadow-gold);
  background: var(--gradient-gold);
}

.alubram-usp__icon .material-symbols-outlined {
  font-size: 32px;
  color: var(--color-accent);
  transition: color var(--transition-base);
}

.alubram-usp:hover .alubram-usp__icon .material-symbols-outlined {
  color: var(--color-primary);
}

.alubram-usp__title {
  font-family: var(--font-heading);
  font-size: var(--text-lg);
  font-weight: 700;
  color: var(--color-primary);
  margin: 0;
}

.alubram-usp__text {
  color: var(--color-gray-500);
  font-size: var(--text-sm);
  line-height: 1.6;
  margin: 0;
}
```

### 3.4 Section Header (reusable)

```html
<header class="alubram-section-header" data-aos="fade-up">
  <span class="alubram-section-header__eyebrow">Unsere Produkte</span>
  <h2 class="alubram-section-header__title">
    Premium Aluminiumprodukte<br>
    <span class="text-gradient-gold">direkt vom Hersteller</span>
  </h2>
  <p class="alubram-section-header__subtitle">
    Entdecken Sie unser gesamtes Sortiment hochwertiger Aluminiumpprodukte.
  </p>
  <div class="alubram-section-header__divider"></div>
</header>
```

```css
.alubram-section-header {
  text-align: center;
  max-width: 720px;
  margin-inline: auto;
  margin-bottom: 3rem;
}

@media (min-width: 1024px) {
  .alubram-section-header { margin-bottom: 4rem; }
}

.alubram-section-header__eyebrow {
  display: inline-block;
  font-size: var(--text-xs);
  font-weight: 700;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  color: var(--color-accent-dark);
  margin-bottom: 0.75rem;
}

.alubram-section-header__title {
  font-family: var(--font-heading);
  font-size: var(--text-4xl);
  font-weight: 800;
  color: var(--color-primary);
  line-height: 1.15;
  margin-bottom: 1rem;
}

.alubram-section-header__subtitle {
  font-size: var(--text-lg);
  color: var(--color-gray-500);
  line-height: 1.7;
  margin-bottom: 1.5rem;
}

.alubram-section-header__divider {
  width: 80px;
  height: 3px;
  background: var(--gradient-gold);
  margin-inline: auto;
  border-radius: 2px;
}

/* Text gradient utility */
.text-gradient-gold {
  background: var(--gradient-gold);
  -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;
  color: transparent;
}
```

### 3.5 Stats Counter

```html
<div class="alubram-counter" data-aos="fade-up">
  <span class="alubram-counter__value"
        data-count="15"
        data-suffix="+"
        aria-label="15 Jahre Erfahrung">0</span>
  <span class="alubram-counter__label">Jahre Erfahrung</span>
</div>
```

```css
.alubram-counter {
  text-align: center;
  padding: 2rem 1rem;
}

.alubram-counter__value {
  display: block;
  font-family: var(--font-heading);
  font-size: var(--text-5xl);
  font-weight: 800;
  background: var(--gradient-gold);
  -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;
  line-height: 1;
  margin-bottom: 0.5rem;
}

.alubram-counter__label {
  font-size: var(--text-sm);
  font-weight: 500;
  color: var(--color-gray-500);
  text-transform: uppercase;
  letter-spacing: 0.1em;
}
```

```typescript
// assets/ts/counter.ts
export function initCounters(): void {
  const counters = document.querySelectorAll<HTMLElement>('[data-count]');
  if (!counters.length) return;

  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (!entry.isIntersecting) return;
      const el = entry.target as HTMLElement;
      const target = parseInt(el.dataset.count ?? '0', 10);
      const suffix = el.dataset.suffix ?? '';
      const duration = 2000;
      const steps = 60;
      const increment = target / steps;
      let current = 0;
      let step = 0;

      const timer = setInterval(() => {
        step++;
        current = Math.min(Math.round(increment * step), target);
        el.textContent = current + suffix;
        if (current >= target) clearInterval(timer);
      }, duration / steps);

      observer.unobserve(el);
    });
  }, { threshold: 0.5 });

  counters.forEach(counter => observer.observe(counter));
}
```

### 3.6 Breadcrumbs

```html
<!-- template-parts/components/breadcrumbs.php -->
<nav class="alubram-breadcrumbs" aria-label="Breadcrumb">
  <ol class="alubram-breadcrumbs__list" itemscope itemtype="https://schema.org/BreadcrumbList">
    <li class="alubram-breadcrumbs__item"
        itemprop="itemListElement" itemscope itemtype="https://schema.org/ListItem">
      <a href="/" class="alubram-breadcrumbs__link" itemprop="item">
        <span class="material-symbols-outlined" aria-hidden="true">home</span>
        <span itemprop="name">Startseite</span>
      </a>
      <meta itemprop="position" content="1">
    </li>
    <li class="alubram-breadcrumbs__separator" aria-hidden="true">
      <span class="material-symbols-outlined">chevron_right</span>
    </li>
    <li class="alubram-breadcrumbs__item alubram-breadcrumbs__item--current"
        itemprop="itemListElement" itemscope itemtype="https://schema.org/ListItem"
        aria-current="page">
      <span itemprop="name">Zäune & Zaunfelder</span>
      <meta itemprop="position" content="2">
    </li>
  </ol>
</nav>
```

```css
.alubram-breadcrumbs {
  padding: 1rem 0;
}

.alubram-breadcrumbs__list {
  list-style: none;
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  gap: 0.25rem;
  margin: 0;
  padding: 0;
}

.alubram-breadcrumbs__link {
  display: inline-flex;
  align-items: center;
  gap: 0.25rem;
  color: var(--color-gray-500);
  font-size: var(--text-sm);
  text-decoration: none;
  transition: color var(--transition-fast);
}
.alubram-breadcrumbs__link:hover { color: var(--color-accent-dark); }

.alubram-breadcrumbs__link .material-symbols-outlined {
  font-size: 16px;
}

.alubram-breadcrumbs__separator .material-symbols-outlined {
  font-size: 16px;
  color: var(--color-gray-200);
}

.alubram-breadcrumbs__item--current span {
  color: var(--color-primary);
  font-weight: 500;
  font-size: var(--text-sm);
}
```

### 3.7 Form Elements

```html
<form class="alubram-form" novalidate>
  <div class="alubram-form__group">
    <label for="name" class="alubram-form__label">
      Ihr Name <span class="alubram-form__required" aria-label="Pflichtfeld">*</span>
    </label>
    <input type="text"
           id="name"
           name="name"
           class="alubram-form__input"
           placeholder="Max Mustermann"
           required
           autocomplete="name">
    <span class="alubram-form__error" role="alert"></span>
  </div>

  <div class="alubram-form__group">
    <label for="interest" class="alubram-form__label">Produktinteresse</label>
    <select id="interest" name="interest" class="alubram-form__select">
      <option value="">Bitte wählen...</option>
      <option value="zaune">Zäune & Zaunfelder</option>
      <option value="tore">Tore & Einfahrtstore</option>
      <option value="carports">Carports</option>
      <option value="ueberdachungen">Überdachungen</option>
    </select>
  </div>

  <div class="alubram-form__group alubram-form__group--checkbox">
    <input type="checkbox" id="dsgvo" name="dsgvo" class="alubram-form__checkbox" required>
    <label for="dsgvo" class="alubram-form__checkbox-label">
      Ich habe die <a href="/datenschutzerklarung/">Datenschutzerklärung</a> gelesen
      und stimme der Verarbeitung meiner Daten zu. *
    </label>
  </div>

  <!-- Honeypot anti-spam -->
  <div style="display:none" aria-hidden="true">
    <input type="text" name="website" tabindex="-1" autocomplete="off">
  </div>

  <button type="submit" class="alubram-btn alubram-btn--primary alubram-btn--lg">
    <span>Anfrage absenden</span>
    <span class="material-symbols-outlined" aria-hidden="true">send</span>
  </button>
</form>
```

```css
.alubram-form__group {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
  margin-bottom: 1.25rem;
}

.alubram-form__label {
  font-family: var(--font-heading);
  font-size: var(--text-sm);
  font-weight: 600;
  color: var(--color-gray-800);
}

.alubram-form__required {
  color: var(--color-error);
  margin-left: 0.25rem;
}

.alubram-form__input,
.alubram-form__select,
.alubram-form__textarea {
  width: 100%;
  padding: 0.875rem 1rem;
  font-family: var(--font-body);
  font-size: var(--text-base);
  color: var(--color-dark);
  background: var(--color-white);
  border: 1.5px solid var(--color-gray-200);
  border-radius: var(--border-radius);
  transition: border-color var(--transition-fast), box-shadow var(--transition-fast);
  outline: none;
  appearance: none;
}

.alubram-form__input:focus,
.alubram-form__select:focus,
.alubram-form__textarea:focus {
  border-color: var(--color-accent);
  box-shadow: 0 0 0 3px rgba(200, 169, 110, 0.2);
}

.alubram-form__input:invalid:not(:placeholder-shown),
.alubram-form__input.is-error {
  border-color: var(--color-error);
  box-shadow: 0 0 0 3px rgba(211, 47, 47, 0.1);
}

.alubram-form__error {
  font-size: var(--text-xs);
  color: var(--color-error);
  display: none;
}
.alubram-form__error.is-visible { display: block; }
```

### 3.8 Hero Section

```html
<section class="alubram-hero" aria-label="Willkommen bei ALUBRAM GMBH">
  <!-- Background: Video / Parallax Image -->
  <div class="alubram-hero__bg" data-parallax data-parallax-speed="0.3">
    <picture>
      <source type="image/avif" srcset="hero-bg.avif">
      <source type="image/webp" srcset="hero-bg.webp">
      <img src="hero-bg.jpg"
           alt=""
           fetchpriority="high"
           decoding="async"
           width="1920"
           height="1080">
    </picture>
    <div class="alubram-hero__overlay"></div>
  </div>

  <div class="alubram-container alubram-hero__content">
    <!-- Eyebrow -->
    <span class="alubram-hero__eyebrow" data-aos="fade-down">
      Ihr Aluminium-Spezialist aus Österreich
    </span>

    <!-- H1 -->
    <h1 class="alubram-hero__title" data-aos="fade-up" data-aos-delay="100">
      Premium Aluminiumzäune,<br>
      Tore &amp; Carports —<br>
      <span class="text-gradient-gold">direkt vom Hersteller</span>
    </h1>

    <!-- Subtitle -->
    <p class="alubram-hero__subtitle" data-aos="fade-up" data-aos-delay="200">
      Lieferung in 3–6 Wochen garantiert · 24/7 erreichbar · Montage inklusive
    </p>

    <!-- CTA Buttons -->
    <div class="alubram-hero__actions" data-aos="fade-up" data-aos-delay="300">
      <a href="/kontakt/" class="alubram-btn alubram-btn--primary alubram-btn--lg">
        Kostenlos beraten lassen
        <span class="material-symbols-outlined" aria-hidden="true">arrow_forward</span>
      </a>
      <a href="/produkte/" class="alubram-btn alubram-btn--ghost alubram-btn--lg">
        Produkte entdecken
        <span class="material-symbols-outlined" aria-hidden="true">inventory_2</span>
      </a>
    </div>

    <!-- USP Badges -->
    <div class="alubram-hero__badges" data-aos="fade-up" data-aos-delay="400">
      <span class="alubram-hero__badge">
        <span class="material-symbols-outlined" aria-hidden="true">verified</span>
        Kein Zwischenhändler
      </span>
      <span class="alubram-hero__badge">
        <span class="material-symbols-outlined" aria-hidden="true">schedule</span>
        24/7 Erreichbar
      </span>
      <span class="alubram-hero__badge">
        <span class="material-symbols-outlined" aria-hidden="true">local_shipping</span>
        3–6 Wochen Lieferzeit
      </span>
    </div>
  </div>

  <!-- Scroll indicator -->
  <div class="alubram-hero__scroll" aria-hidden="true">
    <span class="alubram-hero__scroll-line"></span>
  </div>
</section>
```

```css
.alubram-hero {
  position: relative;
  min-height: 100svh;
  display: flex;
  align-items: center;
  overflow: hidden;
  background: var(--color-primary);
}

.alubram-hero__bg {
  position: absolute;
  inset: 0;
  z-index: var(--z-behind);
  will-change: transform;
}
.alubram-hero__bg img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: center;
}
.alubram-hero__overlay {
  position: absolute;
  inset: 0;
  background: var(--gradient-hero);
}

.alubram-hero__content {
  position: relative;
  z-index: 1;
  padding-block: 8rem 6rem;
  max-width: 900px;
}

.alubram-hero__eyebrow {
  display: inline-block;
  font-size: var(--text-sm);
  font-weight: 600;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  color: var(--color-accent);
  margin-bottom: 1.25rem;
}

.alubram-hero__title {
  font-family: var(--font-heading);
  font-size: var(--text-hero);
  font-weight: 800;
  color: var(--color-white);
  line-height: 1.1;
  margin-bottom: 1.5rem;
}

.alubram-hero__subtitle {
  font-size: var(--text-lg);
  color: rgba(255, 255, 255, 0.8);
  margin-bottom: 2.5rem;
  line-height: 1.6;
}

.alubram-hero__actions {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
  margin-bottom: 3rem;
}

.alubram-hero__badges {
  display: flex;
  flex-wrap: wrap;
  gap: 0.75rem;
}

.alubram-hero__badge {
  display: inline-flex;
  align-items: center;
  gap: 0.375rem;
  padding: 0.5rem 1rem;
  background: rgba(255, 255, 255, 0.1);
  border: 1px solid rgba(255, 255, 255, 0.2);
  border-radius: var(--border-radius-full);
  backdrop-filter: blur(8px);
  color: var(--color-white);
  font-size: var(--text-sm);
  font-weight: 500;
}

.alubram-hero__badge .material-symbols-outlined {
  font-size: 18px;
  color: var(--color-accent);
}

/* Scroll indicator */
.alubram-hero__scroll {
  position: absolute;
  bottom: 2.5rem;
  left: 50%;
  transform: translateX(-50%);
  z-index: 2;
}
.alubram-hero__scroll-line {
  display: block;
  width: 1px;
  height: 60px;
  background: linear-gradient(to bottom, rgba(200, 169, 110, 0.8), transparent);
  margin: 0 auto;
  animation: alubram-scroll-line 2s ease-in-out infinite;
}
@keyframes alubram-scroll-line {
  0%, 100% { opacity: 1; transform: scaleY(1); transform-origin: top; }
  50% { opacity: 0.4; transform: scaleY(0.5); }
}
```

---

## 4. Navigation

### 4.1 Header Structure

```html
<header class="site-header" id="site-header" role="banner">
  <!-- Topbar -->
  <div class="alubram-topbar">
    <div class="alubram-container alubram-topbar__inner">
      <a href="tel:+43223584793" class="alubram-topbar__contact">
        <span class="material-symbols-outlined" aria-hidden="true">phone</span>
        +43 (0) 223 584 793
      </a>
      <a href="mailto:himberg@alubram.at" class="alubram-topbar__contact">
        <span class="material-symbols-outlined" aria-hidden="true">email</span>
        himberg@alubram.at
      </a>
      <span class="alubram-topbar__usp">
        <span class="material-symbols-outlined" aria-hidden="true">schedule</span>
        Geöffnet 24/7
      </span>
    </div>
  </div>

  <!-- Main Nav -->
  <nav class="alubram-nav" aria-label="Hauptnavigation">
    <div class="alubram-container alubram-nav__inner">
      <!-- Logo -->
      <a href="/" class="alubram-logo" aria-label="ALUBRAM GMBH – Zur Startseite">
        <img src="..." class="logo-white" alt="ALUBRAM GMBH" width="200" height="60"
             fetchpriority="high">
        <img src="..." class="logo-color" alt="ALUBRAM GMBH" width="200" height="60"
             fetchpriority="high">
      </a>

      <!-- Desktop Menu -->
      <ul class="alubram-nav__menu" role="menubar">
        <li role="none"><a href="/" class="alubram-nav__link" role="menuitem">Startseite</a></li>
        <li role="none" class="has-dropdown">
          <a href="/produkte/" class="alubram-nav__link" role="menuitem"
             aria-haspopup="true" aria-expanded="false">
            Produkte
            <span class="material-symbols-outlined" aria-hidden="true">expand_more</span>
          </a>
          <ul class="alubram-nav__dropdown" role="menu" aria-label="Produkte Untermenü">
            <li role="none"><a href="/produkte/zaune-zaunfelder/" role="menuitem">Zäune &amp; Zaunfelder</a></li>
            <li role="none"><a href="/produkte/tore/" role="menuitem">Tore &amp; Einfahrtstore</a></li>
            <li role="none"><a href="/produkte/carports/" role="menuitem">Carports</a></li>
            <li role="none"><a href="/produkte/uberdachungen/" role="menuitem">Überdachungen</a></li>
          </ul>
        </li>
        <li role="none"><a href="/referenzen/" class="alubram-nav__link" role="menuitem">Referenzen</a></li>
        <li role="none"><a href="/uber-uns/" class="alubram-nav__link" role="menuitem">Über uns</a></li>
        <li role="none"><a href="/ratgeber/" class="alubram-nav__link" role="menuitem">Ratgeber</a></li>
      </ul>

      <!-- CTA + Hamburger -->
      <div class="alubram-nav__actions">
        <a href="/kontakt/" class="alubram-btn alubram-btn--primary alubram-btn--sm">
          Kostenlos beraten
        </a>
        <button class="alubram-hamburger"
                aria-label="Menü öffnen"
                aria-expanded="false"
                aria-controls="mobile-menu">
          <span></span><span></span><span></span>
        </button>
      </div>
    </div>
  </nav>
</header>
```

---

## 5. AOS Animation Conventions

```html
<!-- Sekcja wchodząca od dołu -->
<section data-aos="fade-up" data-aos-duration="800">

<!-- Karty (delay per element) -->
<div class="alubram-card" data-aos="zoom-in-up" data-aos-delay="0">
<div class="alubram-card" data-aos="zoom-in-up" data-aos-delay="100">
<div class="alubram-card" data-aos="zoom-in-up" data-aos-delay="200">
<div class="alubram-card" data-aos="zoom-in-up" data-aos-delay="300">

<!-- Tekst z lewej, obraz z prawej -->
<div class="content" data-aos="fade-right">
<div class="image"   data-aos="fade-left">

<!-- CTA banery -->
<div class="cta-section" data-aos="fade-up" data-aos-duration="1200">
```

```typescript
// assets/ts/main.ts — AOS init
import AOS from 'aos';

AOS.init({
  duration: 800,
  easing: 'ease-in-out-cubic',
  once: true,
  offset: 80,
  delay: 0,
  anchorPlacement: 'top-bottom',
  disable: 'phone',   // Wyłącz na mobile dla performance
});
```

---

## 6. Accessibility (WCAG 2.1 AA)

### 6.1 Focus States

```css
/* Custom focus ring — brand gold */
:focus-visible {
  outline: 3px solid var(--color-accent);
  outline-offset: 3px;
  border-radius: 2px;
}

/* Remove default outline (tylko gdy :focus-visible jest wspierany) */
:focus:not(:focus-visible) {
  outline: none;
}
```

### 6.2 Skip Link

```html
<a href="#main-content" class="alubram-skip-link">
  Zum Hauptinhalt springen
</a>
<main id="main-content" tabindex="-1">
```

```css
.alubram-skip-link {
  position: absolute;
  top: -100%;
  left: 1rem;
  z-index: var(--z-maximum);
  padding: 0.75rem 1.5rem;
  background: var(--color-accent);
  color: var(--color-primary);
  font-weight: 700;
  text-decoration: none;
  border-radius: var(--border-radius-md);
  transition: top var(--transition-fast);
}
.alubram-skip-link:focus {
  top: 1rem;
}
```

### 6.3 ARIA Checklist

```
□ Każdy <img> ma alt="" (opisowy po DE lub pusty dla dekoracyjnych)
□ Ikony Material Symbols: aria-hidden="true"
□ Formularze: każdy <input> ma powiązany <label>
□ Nawigacja: aria-label na każdym <nav>
□ Przyciski toggle: aria-expanded + aria-controls
□ Aktywna strona w nav: aria-current="page"
□ Dialog/Modal: aria-modal="true", role="dialog"
□ Live regions: role="alert" dla błędów formularza
□ Focus trap w mobile menu
```

---

## 7. Responsive Breakpoints

```css
/* Tailwind Breakpoints — Mobile First */
/* (używaj prefix Tailwind lub custom media queries) */

/* Mobile:  < 640px  — domyślny (bez prefixu) */
/* sm:       ≥ 640px */
/* md:       ≥ 768px */
/* lg:      ≥ 1024px */
/* xl:      ≥ 1280px */
/* 2xl:     ≥ 1536px */

/* Custom (dla specyficznych potrzeb) */
@media (max-width: 767px)  { /* Mobile only  */ }
@media (min-width: 768px)  { /* Tablet+      */ }
@media (min-width: 1024px) { /* Desktop+     */ }
@media (min-width: 1280px) { /* Large+       */ }
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    transition-duration: 0.01ms !important;
  }
}
```

---

## 8. Dark Mode (opcjonalne — future)

```css
/* Przygotowanie pod dark mode toggle */
[data-theme="dark"] {
  --color-primary:  #E8D5A3;   /* Gold jako primary na ciemnym */
  --color-light:    #1A1A2E;
  --color-white:    #16213E;
  --color-gray-800: #F8F6F1;
  --color-gray-500: #B8C5D6;
}
```

---

*DESIGN-SYSTEM.md — ALUBRAM GMBH WordPress | v1.0.0 | 2026-02-26*
