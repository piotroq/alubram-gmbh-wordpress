# FETCH-TEMPLATE-WEBSITE.md — Website Fetch Template & Instructions

> **Dokument:** Instrukcje fetchowania i analizy stron internetowych dla projektu ALUBRAM GMBH
> **Projekt:** `piotroq/alubram-gmbh-wordpress`
> **Wersja:** 1.0.0 | 2026-02-26

---

## 📋 Spis Treści

1. [Wprowadzenie](#1-wprowadzenie)
2. [Narzędzia do Fetchowania](#2-narzędzia-do-fetchowania)
3. [Strony Inspiracji](#3-strony-inspiracji)
4. [Template Fetchowania](#4-template-fetchowania)
5. [Analiza Elementów](#5-analiza-elementów)
6. [Dokumentacja Wyników](#6-dokumentacja-wyników)
7. [Best Practices](#7-best-practices)

---

## 1. Wprowadzenie

### 1.1 Cel Dokumentu

Ten dokument definiuje proces fetchowania i analizy stron internetowych w celu:
- ✅ Zbierania inspiracji designu
- ✅ Analizy rozwiązań technicznych
- ✅ Benchmarkingu konkurencji
- ✅ Walidacji koncepcji UI/UX

### 1.2 Kiedy Fetchować

Fetchuj strony gdy:
- Rozpoczynasz nowy projekt/feature
- Szukasz inspiracji do konkretnego elementu
- Analizujesz konkurencję
- Potrzebujesz zweryfikować rozwiązanie techniczne

---

## 2. Narzędzia do Fetchowania

### 2.1 Web Fetch (AI)

```markdown
[FETCH REQUEST]:
URL: https://arrea.at/
PROMPT: Przeanalizuj strukturę homepage, zwróć uwagę na:
- Hero section layout
- Navigation structure
- Color scheme
- Typography choices
- Animation patterns
```

### 2.2 Browser DevTools

```bash
# Open DevTools
F12 lub Cmd+Option+I (Mac) / Ctrl+Shift+I (Windows/Linux)

# Inspect Element
Right-click → Inspect

# Copy Element
Right-click on element → Copy → Copy element

# Copy Styles
Right-click on style → Copy → Copy declaration
```

### 2.3 Screenshot Tools

| Tool | URL | Purpose |
|------|-----|---------|
| **Full Page Screen Capture** | Chrome Extension | Full page screenshots |
| **GoFullPage** | Chrome Extension | Full page + PDF |
| **Nimbus Screenshot** | Chrome Extension | Annotated screenshots |
| **Snipping Tool** | Windows | Quick screenshots |
| **Cmd+Shift+4** | macOS | Screenshot selection |

### 2.4 Color Picker Tools

| Tool | URL | Purpose |
|------|-----|---------|
| **ColorZilla** | Chrome Extension | Color picker from page |
| **Eye Dropper** | Chrome Extension | Open source color picker |
| **Sip** | macOS App | Color picker for designers |
| **Digital Color Meter** | macOS | Built-in color meter |

---

## 3. Strony Inspiracji

### 3.1 Primary Inspiration Sites

| Strona | URL | Elementy do Analizy |
|--------|-----|-------------------|
| **Arrea** | https://arrea.at/ | Hero video, section transitions, typography |
| **Selt** | https://www.selt.com/home-de | Menu design, product sections, premium fonts |
| **MB Veranda** | https://mbveranda.de/ | Overall look, section layouts, CTA placement |

### 3.2 Additional Inspiration

| Strona | URL | Elementy do Analizy |
|--------|-----|-------------------|
| **Hörmann** | https://www.hoermann.com | Corporate design, product catalog |
| **Kaindl** | https://www.kaindl.com | Material presentation, color schemes |
| **Schöck** | https://www.schoeck.com | Technical product display |

### 3.3 General Design Inspiration

| Strona | URL | Purpose |
|--------|-----|---------|
| **Awwwards** | https://awwwards.com | Premium web design |
| **Dribbble** | https://dribbble.com | UI components |
| **Behance** | https://behance.net | Full projects |
| **Landings** | https://landings.dev | Landing page patterns |
| **Pageflows** | https://pageflows.com | User flow videos |

---

## 4. Template Fetchowania

### 4.1 Fetch Template — Homepage Analysis

```markdown
# HOMEPAGE ANALYSIS TEMPLATE

## URL: [Insert URL]
## Date: [YYYY-MM-DD]
## Analyst: [Your Name]

---

## 1. First Impression

### Visual Impact
- **Overall Style:** [Modern/Classic/Minimal/Bold]
- **Color Palette:** [Primary colors observed]
- **Typography:** [Font families noticed]
- **Imagery:** [Photo style, illustrations, icons]

### Layout
- **Hero Type:** [Fullscreen/Split/Carousel/Video]
- **Grid System:** [Observed grid pattern]
- **Whitespace:** [Minimal/Moderate/Generous]

---

## 2. Header/Navigation

### Structure
```
[Sketch or describe header layout]
- Logo position: [Left/Center/Right]
- Menu items: [List items]
- CTA buttons: [Text, position, style]
- Contact info: [Phone, email placement]
```

### Behavior
- **Sticky:** [Yes/No]
- **Transparent on top:** [Yes/No]
- **Mobile menu:** [Hamburger/Full-screen/Other]

---

## 3. Hero Section

### Content
- **Headline:** [Copy the H1 text]
- **Subheadline:** [Copy the subtitle]
- **CTA Buttons:** [Text, count, style]
- **Background:** [Image/Video/Gradient/Solid]

### Technical Details
- **Height:** [Viewport units or px]
- **Animation:** [AOS/GSAP/Custom]
- **Loading:** [Lazy/Eager]

---

## 4. Sections Breakdown

### Section 1: [Name]
- **Purpose:** [What does this section do?]
- **Layout:** [Grid description]
- **Components:** [Cards, icons, text blocks]
- **Animation:** [Scroll effects, hover]

### Section 2: [Name]
[Repeat structure]

---

## 5. Components Analysis

### Buttons
- **Primary Style:** [Fill/Outline/Ghost]
- **Colors:** [Hex codes if possible]
- **Hover Effects:** [Describe]
- **Border Radius:** [px value]

### Cards
- **Shadow:** [Yes/No, intensity]
- **Border:** [Yes/No, style]
- **Hover:** [Lift/Scale/Overlay]

### Forms
- **Fields:** [List fields]
- **Validation:** [Inline/On submit]
- **Success State:** [Modal/Inline/Redirect]

---

## 6. Technical Stack

### Detected Technologies
- **CMS:** [WordPress/Other/Detect with Wappalyzer]
- **Frameworks:** [React/Vue/Other]
- **CSS:** [Tailwind/Bootstrap/Custom]
- **Animations:** [AOS/GSAP/Framer Motion]

### Performance
- **LCP:** [PageSpeed score]
- **Images:** [WebP/AVIF/Lazy loading]
- **Scripts:** [Deferred/Async]

---

## 7. Adaptable Elements for ALUBRAM

### High Priority
1. [Element 1] — Why adaptable
2. [Element 2] — Why adaptable

### Medium Priority
1. [Element 1] — Considerations
2. [Element 2] — Considerations

### Not Adaptable
1. [Element] — Why not (brand mismatch, technical constraints)

---

## 8. Screenshots

[Attach annotated screenshots]

## 9. Code Snippets

[Copy any interesting code patterns]

## 10. Notes

[Any additional observations]
```

### 4.2 Fetch Template — Product Page Analysis

```markdown
# PRODUCT PAGE ANALYSIS TEMPLATE

## URL: [Insert URL]
## Product Type: [Category]
## Date: [YYYY-MM-DD]

---

## 1. Product Information Architecture

### Above the Fold
- **Product Title:** [H1 text]
- **Price Display:** [Format, position]
- **Main Image:** [Size, type]
- **Primary CTA:** [Text, style]

### Below the Fold
- **Description:** [Length, format]
- **Specifications:** [Table/List]
- **Gallery:** [Slider/Grid]
- **Related Products:** [Yes/No, layout]

---

## 2. Product Gallery

### Type
- [ ] Single image
- [ ] Slider (Swiper/Slick/Other)
- [ ] Grid layout
- [ ] 360° view
- [ ] Zoom functionality

### Features
- **Thumbnails:** [Yes/No, position]
- **Lightbox:** [Yes/No]
- **Fullscreen:** [Yes/No]
- **Touch Support:** [Yes/No]

---

## 3. Product Configuration

### Options Available
- **Colors:** [Swatches/Dropdown]
- **Sizes:** [Buttons/Dropdown]
- **Add-ons:** [Checkboxes]

### Price Updates
- **Dynamic:** [Yes/No]
- **Display:** [Inline/Modal]

---

## 4. Trust Elements

### Social Proof
- **Reviews:** [Stars, count]
- **Testimonials:** [Yes/No]
- **Case Studies:** [Linked]

### Guarantees
- **Warranty:** [Displayed?]
- **Certifications:** [Logos shown]
- **Return Policy:** [Mentioned?]

---

## 5. CTA Strategy

### Primary CTA
- **Text:** [Get Quote/Buy Now/Contact]
- **Position:** [Sticky/End of page]
- **Style:** [Color, size]

### Secondary CTAs
- **Download Brochure:** [Yes/No]
- **Schedule Call:** [Yes/No]
- **Chat:** [Yes/No]

---

## 6. Adaptable for ALUBRAM

[Same structure as homepage template]
```

---

## 5. Analiza Elementów

### 5.1 Element Analysis Checklist

```markdown
## ELEMENT ANALYSIS CHECKLIST

### Visual Design
- [ ] Color scheme identified
- [ ] Typography documented
- [ ] Spacing pattern noted
- [ ] Shadow/border styles captured

### Layout
- [ ] Grid system understood
- [ ] Container widths measured
- [ ] Section heights noted
- [ ] Responsive breakpoints identified

### Interactions
- [ ] Hover effects documented
- [ ] Scroll animations captured
- [ ] Transition timings noted
- [ ] Micro-interactions observed

### Content
- [ ] Heading hierarchy mapped
- [ ] Content length measured
- [ ] CTA copy documented
- [ ] Image styles analyzed

### Technical
- [ ] Loading strategy identified
- [ ] Image optimization checked
- [ ] Script loading pattern noted
- [ ] Cache strategy inferred
```

### 5.2 Screenshot Annotation Guide

```
┌─────────────────────────────────────────────────────────────────┐
│                    SCREENSHOT ANNOTATION                        │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  🔵 Blue Circle:     Key element to replicate                  │
│  🟡 Yellow Highlight: Color to sample                          │
│  🟢 Green Arrow:     Animation direction                       │
│  🔴 Red Box:         Don't copy (brand mismatch)               │
│  📝 Text Note:       Implementation notes                      │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

---

## 6. Dokumentacja Wyników

### 6.1 Organization Structure

```
docs/
└── inspiration/
    ├── arrea/
    │   ├── screenshots/
    │   │   ├── homepage-full.png
    │   │   ├── hero-section.png
    │   │   └── navigation.png
    │   ├── analysis.md
    │   └── code-snippets.txt
    ├── selt/
    │   └── ...
    └── mbveranda/
        └── ...
```

### 6.2 Analysis Document Template

```markdown
# [Site Name] Analysis

> **URL:** https://example.com
> **Date Analyzed:** 2026-02-26
> **Analyst:** [Name]

---

## Executive Summary

[Brief 2-3 sentence summary of key findings]

---

## Key Takeaways

1. **Takeaway 1:** Description
2. **Takeaway 2:** Description
3. **Takeaway 3:** Description

---

## Adaptable Elements

| Element | Adaptation Effort | Priority | Notes |
|---------|------------------|----------|-------|
| Hero layout | Low | High | Direct adaptation |
| Color scheme | Medium | Medium | Adjust to brand |
| Navigation | High | Low | Too complex |

---

## Screenshots

[Embedded screenshots with annotations]

---

## Code Patterns

```css
/* Example CSS pattern */
.example-class {
    /* Adaptable code */
}
```

---

## Action Items

- [ ] Implement hero section pattern
- [ ] Sample color palette
- [ ] Document typography
```

---

## 7. Best Practices

### 7.1 Do's

✅ **DO:**
- Fetch multiple pages from the same site for consistency
- Take full-page screenshots, not just viewport
- Document both visual and technical aspects
- Note what works AND what doesn't
- Consider mobile and desktop versions
- Check page speed and performance
- Look at the source code for implementation details
- Document color hex codes precisely

### 7.2 Don'ts

❌ **DON'T:**
- Copy designs directly (copyright issues)
- Ignore brand guidelines
- Focus only on desktop (mobile is crucial)
- Forget to check accessibility
- Overlook performance implications
- Copy code without understanding it
- Ignore SEO implications
- Forget about responsive behavior

### 7.3 Legal Considerations

```markdown
## COPYRIGHT NOTICE

When analyzing websites:

✅ ALLOWED:
- Analyzing design patterns
- Learning from structure
- Taking inspiration from layouts
- Sampling color palettes (colors aren't copyrightable)
- Studying technical implementations

❌ NOT ALLOWED:
- Copying exact designs
- Stealing logos or branded elements
- Copying proprietary code
- Using copyrighted images
- Replicating unique branded elements

Always adapt and make it your own!
```

---

## 8. Quick Reference

### 8.1 Useful Browser Extensions

| Extension | Purpose | Link |
|-----------|---------|------|
| **Wappalyzer** | Tech stack detection | Chrome Web Store |
| **ColorZilla** | Color picker | Chrome Web Store |
| **WhatFont** | Font identification | Chrome Web Store |
| **Page Ruler** | Measure elements | Chrome Web Store |
| **Lighthouse** | Performance audit | Built-in Chrome |

### 8.2 Keyboard Shortcuts

| Action | Windows/Linux | macOS |
|--------|--------------|-------|
| Open DevTools | Ctrl+Shift+I | Cmd+Option+I |
| Inspect Element | Ctrl+Shift+C | Cmd+Option+C |
| Full Screenshot | Ctrl+Shift+P → "screenshot" | Cmd+Shift+P → "screenshot" |
| View Page Source | Ctrl+U | Cmd+Option+U |
| View Page Info | Ctrl+I | Cmd+I |

### 8.3 Useful Commands

```bash
# Check website tech stack (CLI)
npx wappalyzer https://example.com

# Get page performance
lighthouse https://example.com --output html --output-path report.html

# Download full page screenshot (Playwright)
npx playwright screenshot --full-page https://example.com screenshot.png
```

---

*FETCH-TEMPLATE-WEBSITE.md — ALUBRAM GMBH WordPress Project | v1.0.0 | 2026-02-26*
