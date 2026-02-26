# CONTRIBUTING.md — Contribution Guidelines

> **Dokument:** Wytyczne dla kontrybutorów projektu ALUBRAM GMBH WordPress
> **Projekt:** `piotroq/alubram-gmbh-wordpress`
> **Wersja:** 1.0.0 | 2026-02-26

---

## 📋 Spis Treści

1. [Wprowadzenie](#1-wprowadzenie)
2. [Code of Conduct](#2-code-of-conduct)
3. [Getting Started](#3-getting-started)
4. [Development Workflow](#4-development-workflow)
5. [Coding Standards](#5-coding-standards)
6. [Commit Guidelines](#6-commit-guidelines)
7. [Pull Request Process](#7-pull-request-process)
8. [Issue Reporting](#8-issue-reporting)
9. [Documentation](#9-dokumentacja)
10. [Testing](#10-testing)

---

## 1. Wprowadzenie

### 1.1 O Projekcie

**ALUBRAM GMBH WordPress** to projekt strony internetowej dla austriackiego producenta aluminiowych ogrodzeń, bram, wiat garażowych i zadaszeń.

**Stack:**
- WordPress 6.9
- PHP 8.2+
- TypeScript/JavaScript ES6+
- Tailwind CSS
- AOS, Swiper.js

### 1.2 Jak Możesz Pomóc

Szukamy pomocy w:
- ✅ Development WordPress (PHP, TypeScript)
- ✅ UI/UX Design
- ✅ SEO optimization
- ✅ Testing (unit, integration, E2E)
- ✅ Documentation
- ✅ Translations (DE/PL/EN)

### 1.3 Kontakty

- **Repository:** https://github.com/piotroq/alubram-gmbh-wordpress
- **Issues:** https://github.com/piotroq/alubram-gmbh-wordpress/issues
- **Email:** [your-email@example.com]

---

## 2. Code of Conduct

### 2.1 Nasze Zobowiązanie

W celu wspierania otwartego i przyjaznego środowiska, zobowiązujemy się do:

- ✅ Szanowania różnych perspektyw i doświadczeń
- ✅ Konstruktywnej krytyki
- ✅ Skupienia na tym, co najlepsze dla społeczności
- ✅ Empatii wobec innych członków społeczności

### 2.2 Niedopuszczalne Zachowania

- ❌ Używanie seksualnego języka lub obrazów
- ❌ Obraźliwe komentarze, trolling
- ❌ Publiczne lub prywatne nękanie
- ❌ Publikowanie prywatnych informacji innych osób
- ❌ Inne zachowania nieetyczne lub nieprofesjonalne

### 2.3 Egzekwowanie

Instancje obraźliwego, nękającego lub w inny sposób niedopuszczalnego zachowania mogą być zgłaszane do administratorów projektu.

---

## 3. Getting Started

### 3.1 Wymagania

```bash
# Wymagane oprogramowanie
PHP >= 8.2
Node.js >= 20.x LTS
npm >= 10.x
Composer >= 2.7
MySQL 8.0 / MariaDB 10.6+
Git >= 2.40

# Opcjonalnie
Docker >= 24.x
wp-cli >= 2.9
```

### 3.2 Instalacja

```bash
# 1. Forkuj repozytorium
git clone https://github.com/YOUR_USERNAME/alubram-gmbh-wordpress.git
cd alubram-gmbh-wordpress

# 2. Zainstaluj Node.js dependencies
npm install

# 3. Zainstaluj Composer dependencies
composer install

# 4. Skonfiguruj lokalne środowisko
npx @wordpress/env start

# 5. Build TypeScript
npm run build

# 6. Watch mode (development)
npm run watch
```

### 3.3 Struktura Katalogów

```
alubram-gmbh-wordpress/
├── .claude/                    ← AI agents configuration
├── .github/                    ← GitHub workflows, templates
├── docs/                       ← Documentation
├── src/
│   └── wp-content/
│       └── themes/
│           ├── alubramat/      ← Parent theme
│           └── alubramat-child/← Child theme (ACTIVE)
├── scripts/                    ← Build scripts
└── tests/                      ← Test files
```

---

## 4. Development Workflow

### 4.1 Branching Model

```
main (production)
  └── develop (staging)
        └── feature/feature-name (new features)
        └── bugfix/bugfix-name (bug fixes)
        └── hotfix/hotfix-name (urgent fixes)
        └── docs/docs-name (documentation)
```

### 4.2 Nazewnictwo Branchy

| Typ | Format | Przykład |
|-----|--------|----------|
| **Feature** | `feature/description` | `feature/contact-form` |
| **Bugfix** | `bugfix/description` | `bugfix/header-scroll` |
| **Hotfix** | `hotfix/description` | `hotfix/security-patch` |
| **Documentation** | `docs/description` | `docs/readme-update` |
| **Refactor** | `refactor/description` | `refactor/php-82-upgrade` |

### 4.3 Workflow

```bash
# 1. Aktualizacja develop
git checkout develop
git pull origin develop

# 2. Utwórz nowy branch
git checkout -b feature/your-feature

# 3. Pracuj nad zmianami
# ... code, test, commit ...

# 4. Push zmian
git push origin feature/your-feature

# 5. Utwórz Pull Request
# https://github.com/piotroq/alubram-gmbh-wordpress/pulls
```

---

## 5. Coding Standards

### 5.1 PHP Standards

**PSR-12 + WordPress Coding Standards:**

```php
<?php
/**
 * Example function with proper documentation
 *
 * @package alubramat-child
 * @version 1.0.0
 */

declare(strict_types=1);

// Use strict types
function alubram_example_function(string $input, int $count = 10): array {
    // Sanitize input
    $sanitized = sanitize_text_field($input);
    
    // Process
    $result = [];
    for ($i = 0; $i < $count; $i++) {
        $result[] = $sanitized . '_' . $i;
    }
    
    // Return with type declaration
    return $result;
}
```

**Checklist:**
- ✅ `declare(strict_types=1);` w plikach z logiką
- ✅ Type declarations dla argumentów i return types
- ✅ PHPDoc dla funkcji i klas
- ✅ `if (!defined('ABSPATH')) { exit; }` w template'ach
- ✅ Escape output: `esc_html()`, `esc_url()`, `esc_attr()`
- ✅ Sanitize input: `sanitize_text_field()`, `sanitize_email()`

### 5.2 TypeScript Standards

```typescript
/**
 * Fetch products from API
 * @param category - Product category filter
 * @param limit - Maximum number of products
 * @returns Array of products
 */
export async function fetchProducts(
    category?: string,
    limit: number = 10
): Promise<Product[]> {
    const params = new URLSearchParams({
        limit: limit.toString(),
        ...(category && { category })
    });

    const response = await fetch(`/wp-json/alubram/v1/products?${params}`);
    
    if (!response.ok) {
        throw new Error(`HTTP error! status: ${response.status}`);
    }

    return await response.json();
}

// Interface definition
export interface Product {
    id: number;
    title: string;
    slug: string;
    price: number;
    category: 'zaune' | 'tore' | 'carports' | 'ueberdachungen';
    deliveryTime: string;
}
```

**Checklist:**
- ✅ TypeScript zamiast JavaScript
- ✅ Interfaces dla typów
- ✅ Async/await zamiast .then()
- ✅ Optional chaining (?.) i nullish coalescing (??)
- ✅ JSDoc dla funkcji

### 5.3 CSS Standards

```css
/* BEM-like naming with brand variables */
.alubram-section {
    padding: var(--section-padding-mobile);
}

@media (min-width: 768px) {
    .alubram-section {
        padding: 60px 0;
    }
}

@media (min-width: 1024px) {
    .alubram-section {
        padding: var(--section-padding);
    }
}

/* Component example */
.alubram-card {
    background: var(--color-white);
    border-radius: var(--border-radius-lg);
    box-shadow: var(--shadow-sm);
    transition: var(--transition-base);
}

.alubram-card:hover {
    transform: translateY(-8px);
    box-shadow: var(--shadow-lg);
}

.alubram-card__image {
    aspect-ratio: 4 / 3;
    overflow: hidden;
}

.alubram-card__title {
    font-family: var(--font-heading);
    font-size: var(--text-xl);
    color: var(--color-primary);
}
```

**Checklist:**
- ✅ Brand variables z `:root`
- ✅ Mobile-first CSS
- ✅ BEM-like naming
- ✅ No hard-coded colors/values
- ✅ Proper media queries

---

## 6. Commit Guidelines

### 6.1 Conventional Commits

```
<type>(<scope>): <description>

[optional body]

[optional footer]
```

### 6.2 Types

| Type | Description |
|------|-------------|
| `feat` | New feature |
| `fix` | Bug fix |
| `docs` | Documentation changes |
| `style` | Code style changes (formatting) |
| `refactor` | Code refactoring |
| `test` | Adding tests |
| `chore` | Build/config changes |
| `perf` | Performance improvements |
| `security` | Security fixes |

### 6.3 Przykłady

```bash
# Feature
git commit -m "feat(contact-form): add AJAX contact form with validation"

# Bug fix
git commit -m "fix(header): resolve sticky header scroll issue"

# Documentation
git commit -m "docs(readme): update installation instructions"

# Refactor
git commit -m "refactor(php): upgrade to PHP 8.2 strict types"

# Multiple lines
git commit -m "feat(products): add product gallery with Swiper

- Implement Swiper.js slider
- Add thumbnail navigation
- Support touch gestures
- Lazy loading images

Closes #42"
```

### 6.4 Pre-commit Hooks

```json
// package.json
{
  "husky": {
    "hooks": {
      "pre-commit": "npm run lint && npm run type-check",
      "commit-msg": "commitlint -E HUSKY_GIT_PARAMS"
    }
  }
}
```

---

## 7. Pull Request Process

### 7.1 Przed Utworzeniem PR

```markdown
## PR Checklist

### Code Quality
- [ ] Code follows project standards
- [ ] PHP linting passed (`composer run lint`)
- [ ] TypeScript compilation passed (`npm run build`)
- [ ] No console errors
- [ ] No TODO comments in production code

### Testing
- [ ] Unit tests added/updated
- [ ] Integration tests passed
- [ ] Manual testing completed
- [ ] Cross-browser testing done

### Documentation
- [ ] Code documented (PHPDoc, JSDoc)
- [ ] README updated if needed
- [ ] Changelog updated

### Security
- [ ] No sensitive data committed
- [ ] Input sanitization implemented
- [ ] Output escaping implemented
- [ ] Nonce verification for forms
```

### 7.2 Tworzenie PR

1. **Forkuj repozytorium** (jeśli nie masz access)
2. **Utwórz branch** z swojego forka
3. **Wypełnij PR template**
4. **Dodaj reviewerów**
5. **Czekaj na review**

### 7.3 PR Template

```markdown
## Description
<!-- Describe your changes in detail -->

## Related Issue
<!-- Link to related issue: Fixes #123 -->

## Type of Change
- [ ] Bug fix (non-breaking change which fixes an issue)
- [ ] New feature (non-breaking change which adds functionality)
- [ ] Breaking change (fix or feature that would cause existing functionality to change)
- [ ] Documentation update

## Testing Done
<!-- Describe the tests you ran -->

## Screenshots (if applicable)
<!-- Add screenshots of UI changes -->

## Checklist
- [ ] My code follows the style guidelines
- [ ] I have performed a self-review
- [ ] I have commented my code
- [ ] I have updated documentation
- [ ] My changes generate no new warnings
- [ ] I have added tests
- [ ] New and existing tests pass locally
```

### 7.4 Review Process

```
1. PR Created
       ↓
2. Automated Checks (CI/CD)
   - Linting
   - Tests
   - Build
       ↓
3. Code Review (1-2 reviewers)
   - Code quality
   - Security
   - Performance
       ↓
4. Changes Requested / Approved
       ↓
5. Merge to develop
```

---

## 8. Issue Reporting

### 8.1 Bug Report Template

```markdown
## Bug Report

### Description
<!-- Clear description of the bug -->

### Steps to Reproduce
1. Step 1
2. Step 2
3. Step 3

### Expected Behavior
<!-- What should happen -->

### Actual Behavior
<!-- What actually happens -->

### Environment
- **WordPress:** 6.9
- **PHP:** 8.2
- **Browser:** Chrome 120
- **OS:** macOS 14.2

### Screenshots
<!-- Add screenshots if applicable -->

### Additional Context
<!-- Any other information -->
```

### 8.2 Feature Request Template

```markdown
## Feature Request

### Problem Statement
<!-- What problem does this feature solve? -->

### Proposed Solution
<!-- Describe the solution you'd like -->

### Alternatives Considered
<!-- Any alternative solutions -->

### Additional Context
<!-- Mockups, examples, references -->
```

### 8.3 Issue Labels

| Label | Description |
|-------|-------------|
| `bug` | Something isn't working |
| `enhancement` | New feature request |
| `documentation` | Documentation improvements |
| `good first issue` | Good for newcomers |
| `help wanted` | Extra attention needed |
| `priority:high` | High priority |
| `priority:critical` | Critical issue |
| `status:in-progress` | Being worked on |
| `status:blocked` | Blocked by something |

---

## 9. Dokumentacja

### 9.1 Gdzie Dodawać Dokumentację

| Typ | Lokalizacja |
|-----|-------------|
| **API Documentation** | `docs/api/` |
| **Architecture** | `docs/architecture/` |
| **User Guides** | `docs/guides/` |
| **Code Comments** | W plikach (PHPDoc, JSDoc) |
| **README** | Root lub katalogi |

### 9.2 Documentation Standards

```markdown
# Tytuł Dokumentu

> **Opis:** Krótki opis (1-2 zdania)
> **Wersja:** 1.0.0
> **Data:** 2026-02-26

## Spis Treści
1. [Sekcja 1](#sekcja-1)
2. [Sekcja 2](#sekcja-2)

## Sekcja 1

Treść sekcji...
```

---

## 10. Testing

### 10.1 Rodzaje Testów

| Typ | Narzędzie | Lokalizacja |
|-----|-----------|-------------|
| **Unit Tests** | PHPUnit, Jest | `tests/unit/` |
| **Integration Tests** | PHPUnit | `tests/integration/` |
| **E2E Tests** | Playwright | `tests/e2e/` |
| **Visual Tests** | Playwright | `tests/visual/` |

### 10.2 Uruchamianie Testów

```bash
# Unit tests (PHP)
composer run test:unit

# Unit tests (TypeScript)
npm run test:unit

# Integration tests
composer run test:integration

# E2E tests
npm run test:e2e

# All tests
npm run test
```

### 10.3 Przykład Testu (PHPUnit)

```php
<?php
/**
 * Test for contact form handler
 * @package alubramat-child
 */

class ContactFormTest extends WP_UnitTestCase {
    
    public function test_valid_submission_returns_success(): void {
        $data = [
            'name' => 'Test User',
            'email' => 'test@example.com',
            'message' => 'Test message',
        ];
        
        $result = alubram_handle_contact_form($data);
        
        $this->assertTrue($result['success']);
        $this->assertEquals('Message sent successfully', $result['message']);
    }
    
    public function test_invalid_email_returns_error(): void {
        $data = [
            'name' => 'Test User',
            'email' => 'invalid-email',
            'message' => 'Test message',
        ];
        
        $result = alubram_handle_contact_form($data);
        
        $this->assertFalse($result['success']);
        $this->assertStringContainsString('Invalid email', $result['message']);
    }
}
```

### 10.4 Przykład Testu (Playwright)

```typescript
// tests/e2e/contact-form.spec.ts
import { test, expect } from '@playwright/test';

test.describe('Contact Form', () => {
  test('should submit form successfully', async ({ page }) => {
    await page.goto('/kontakt/');
    
    await page.fill('input[name="name"]', 'Test User');
    await page.fill('input[name="email"]', 'test@example.com');
    await page.fill('textarea[name="message"]', 'Test message');
    await page.check('input[name="dsgvo"]');
    
    await page.click('button[type="submit"]');
    
    await expect(page.locator('.success-message')).toBeVisible();
    await expect(page.locator('.success-message')).toContainText(
      'Vielen Dank für Ihre Nachricht'
    );
  });
  
  test('should show error for invalid email', async ({ page }) => {
    await page.goto('/kontakt/');
    
    await page.fill('input[name="name"]', 'Test User');
    await page.fill('input[name="email"]', 'invalid');
    await page.click('button[type="submit"]');
    
    await expect(page.locator('.error-message')).toBeVisible();
    await expect(page.locator('.error-message')).toContainText(
      'Bitte geben Sie eine gültige E-Mail-Adresse ein'
    );
  });
});
```

---

## 11. Release Process

### 11.1 Versioning

Projekt używa [Semantic Versioning](https://semver.org/):

```
MAJOR.MINOR.PATCH
  │     │     │
  │     │     └─ Bug fixes (backward compatible)
  │     └─────── New features (backward compatible)
  └───────────── Breaking changes
```

### 11.2 Release Checklist

```markdown
## Pre-Release
- [ ] All tests passing
- [ ] Code review completed
- [ ] Documentation updated
- [ ] Changelog updated
- [ ] Version bumped in package.json
- [ ] Version bumped in theme style.css

## Release
- [ ] Create release branch
- [ ] Tag release
- [ ] Publish to GitHub Releases
- [ ] Deploy to production

## Post-Release
- [ ] Monitor for issues
- [ ] Update documentation
- [ ] Announce release
```

---

## 12. License

By contributing to this project, you agree that your contributions will be licensed under the project's license.

---

*CONTRIBUTING.md — ALUBRAM GMBH WordPress Project | v1.0.0 | 2026-02-26*
