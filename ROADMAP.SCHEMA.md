# ROADMAP.SCHEMA.md — Project Roadmap Schema & Structure

> **Dokument:** Schema i struktura roadmapi projektu ALUBRAM GMBH
> **Projekt:** `piotroq/alubram-gmbh-wordpress`
> **Wersja:** 1.0.0 | 2026-02-26

---

## 📋 Spis Treści

1. [Wprowadzenie](#1-wprowadzenie)
2. [Schema Roadmapy](#2-schema-roadmapy)
3. [Fazy Projektu](#3-fazy-projektu)
4. [Kamienie Milowe](#4-kamienie-milowe)
5. [Task Schema](#5-task-schema)
6. [Milestone Schema](#6-milestone-schema)
7. [Risk Schema](#7-risk-schema)
8. [KPI Schema](#8-kpi-schema)
9. [JSON Schema](#9-json-schema)
10. [Przykłady Użycia](#10-przykłady-użycia)

---

## 1. Wprowadzenie

### 1.1 Cel Dokumentu

Ten dokument definiuje ustandaryzowaną schemę dla:
- ✅ Roadmapy projektu
- ✅ Kamieni milowych (milestones)
- ✅ Tasków i zadań
- ✅ Ryzyk projektowych
- ✅ Metryk sukcesu (KPIs)

### 1.2 Zastosowanie

Schema jest używana do:
- Planowania projektu
- Trackingu postępu
- Raportowania statusu
- Zarządzania ryzykiem
- Ewaluacji sukcesu

---

## 2. Schema Roadmapy

### 2.1 Główna Struktura

```yaml
roadmap:
  project:
    name: string                    # Nazwa projektu
    client: string                  # Klient
    repository: string              # GitHub repo URL
    version: string                 # Wersja dokumentu
    lastUpdated: date               # Data ostatniej aktualizacji

  timeline:
    startDate: date                 # Data rozpoczęcia
    endDate: date                   # Data zakończenia
    totalWeeks: number              # Całkowity czas w tygodniach
    currentPhase: string            # Aktualna faza

  phases: array                     # Tablica faz projektu
    - phase:
        number: number              # Numer fazy (1-6)
        name: string                # Nazwa fazy
        description: string         # Opis
        startDate: date             # Data rozpoczęcia
        endDate: date               # Data zakończenia
        duration: number            # Czas trwania (dni robocze)
        status: enum                # Status: not_started|in_progress|completed|blocked
        deliverables: array         # Lista deliverables
        milestones: array           # Lista kamieni milowych
        tasks: array                # Lista zadań
        risks: array                # Lista ryzyk
        owner: string               # Właściciel fazy
```

### 2.2 Status Enum

```typescript
type PhaseStatus = 
  | 'not_started'      // ⬜ Nie rozpoczęto
  | 'in_progress'      // 🟙 W trakcie
  | 'completed'        // ✅ Zakończono
  | 'blocked'          // 🚫 Zablokowane
  | 'at_risk'          // ⚠️ Zagrożone
```

---

## 3. Fazy Projektu

### 3.1 Standardowe Fazy (WordPress Project)

```typescript
interface ProjectPhase {
  number: number;
  name: string;
  description: string;
  duration: number;     // dni robocze
  deliverables: string[];
  milestones: Milestone[];
  tasks: Task[];
  risks: Risk[];
  owner: string;
}
```

### 3.2 Definicje Faz

#### Phase 1: Discovery & Planning (Weeks 1-2)

```yaml
phase:
  number: 1
  name: "Discovery & Planning"
  description: "Analiza wymagań, research, planowanie projektu"
  duration: 10  # dni roboczych
  status: "not_started"
  
  deliverables:
    - "Project kickoff meeting"
    - "Brand identity analysis"
    - "Competitor analysis (5 sites)"
    - "Sitemap & IA"
    - "Technical requirements doc"
    - "Content strategy"
    - "SEO keyword research"
    - "Project plan finalization"
  
  milestones:
    - name: "Project Kickoff Complete"
      dueDate: "Week 1, Day 2"
      criteria: "All stakeholders aligned, access granted"
    
    - name: "Discovery Complete"
      dueDate: "Week 2, Day 5"
      criteria: "All deliverables approved"
  
  owner: "Project Manager"
```

#### Phase 2: Design (Weeks 3-5)

```yaml
phase:
  number: 2
  name: "Design"
  description: "Wireframing, mockupy, prototypowanie UI/UX"
  duration: 15
  status: "not_started"
  
  deliverables:
    - "Moodboard & style tiles"
    - "Homepage wireframe (mobile + desktop)"
    - "Inner page wireframes (5 templates)"
    - "Design system v1"
    - "Homepage high-fidelity mockup"
    - "Inner page mockups (5 templates)"
    - "Interactive prototype"
    - "Design handoff documentation"
  
  milestones:
    - name: "Wireframes Approved"
      dueDate: "Week 3, Day 5"
    
    - name: "Design System Complete"
      dueDate: "Week 4, Day 2"
    
    - name: "All Mockups Approved"
      dueDate: "Week 5, Day 4"
    
    - name: "Design Phase Complete"
      dueDate: "Week 5, Day 5"
  
  owner: "UI/UX Designer"
```

#### Phase 3: Development (Weeks 6-11)

```yaml
phase:
  number: 3
  name: "Development"
  description: "Implementacja WordPress, motyw, funkcjonalności"
  duration: 30
  status: "not_started"
  
  deliverables:
    - "WordPress setup (local + staging)"
    - "Parent theme (alubramat)"
    - "Child theme setup (alubramat-child)"
    - "Brand CSS (style.css)"
    - "Header & Footer"
    - "Homepage (front-page.php)"
    - "CPT Registration"
    - "Produkt templates"
    - "Inner page templates (5)"
    - "ACF fields setup"
    - "Contact form (AJAX)"
    - "Animations (AOS + custom)"
    - "Performance optimization"
    - "SEO implementation"
    - "Content population"
  
  milestones:
    - name: "Theme Foundation Complete"
      dueDate: "Week 6, Day 5"
    
    - name: "Homepage Complete"
      dueDate: "Week 7, Day 5"
    
    - name: "CPT & Products Complete"
      dueDate: "Week 8, Day 5"
    
    - name: "All Templates Complete"
      dueDate: "Week 9, Day 5"
    
    - name: "Development Complete"
      dueDate: "Week 11, Day 5"
  
  owner: "Tech Lead / WordPress Developer"
```

#### Phase 4: Testing & QA (Weeks 12-13)

```yaml
phase:
  number: 4
  name: "Testing & QA"
  description: "Testy funkcjonalne, audyty, bug fixes"
  duration: 10
  status: "not_started"
  
  deliverables:
    - "Functional testing report"
    - "Cross-browser testing report"
    - "Performance audit (Lighthouse)"
    - "Accessibility audit (WCAG)"
    - "Security audit"
    - "Bug fixes (all critical/high)"
    - "UAT preparation"
  
  milestones:
    - name: "Testing Complete"
      dueDate: "Week 12, Day 5"
    
    - name: "Audits Complete"
      dueDate: "Week 13, Day 4"
    
    - name: "QA Phase Complete"
      dueDate: "Week 13, Day 5"
  
  owner: "QA Engineer"
```

#### Phase 5: Deployment (Week 14)

```yaml
phase:
  number: 5
  name: "Deployment"
  description: "Wdrożenie na produkcję, go-live"
  duration: 5
  status: "not_started"
  
  deliverables:
    - "Production environment setup"
    - "Database migration"
    - "Files deployment"
    - "DNS configuration"
    - "SSL certificate"
    - "Production testing"
    - "Go-live approval"
  
  milestones:
    - name: "Deployment Complete"
      dueDate: "Week 14, Day 2"
    
    - name: "DNS & SSL Complete"
      dueDate: "Week 14, Day 3"
    
    - name: "Go-Live"
      dueDate: "Week 14, Day 5"
  
  owner: "DevOps / Tech Lead"
```

#### Phase 6: Post-Launch (Weeks 15-16+)

```yaml
phase:
  number: 6
  name: "Post-Launch"
  description: "Szkolenia, monitoring, optymalizacja"
  duration: 10
  status: "not_started"
  
  deliverables:
    - "Training session (client)"
    - "Documentation handoff"
    - "2-week monitoring report"
    - "SEO performance report (1 month)"
    - "3-month review meeting"
  
  milestones:
    - name: "Training Complete"
      dueDate: "Week 15, Day 2"
    
    - name: "Documentation Handoff"
      dueDate: "Week 15, Day 3"
    
    - name: "2-Week Monitoring Complete"
      dueDate: "Week 16, Day 5"
    
    - name: "3-Month Review"
      dueDate: "Week 26"
  
  owner: "Project Manager"
```

---

## 4. Kamienie Milowe (Milestones)

### 4.1 Milestone Schema

```typescript
interface Milestone {
  id: string;                   // Unikalny ID: M1, M2, M3...
  name: string;                 // Nazwa kamienia
  phase: number;                # Numer fazy
  dueDate: string;              // Termin (Week X, Day Y)
  actualDate?: string;          // Rzeczywista data (opcjonalne)
  status: MilestoneStatus;      // Status
  criteria: string[];           // Kryteria zaliczenia
  deliverables: string[];       // Powiązane deliverables
  owner: string;                // Właściciel
  signOff?: {                   // Sign-off (opcjonalne)
    approved: boolean;
    approvedBy: string;
    approvedDate: string;
    comments?: string;
  };
  dependencies?: string[];      // Zależności od innych milestones
  risks?: string[];             // Powiązane ryzyka
}

type MilestoneStatus = 
  | 'pending'       // ⏳ Oczekujący
  | 'at_risk'      // ⚠️ Zagrożony
  | 'completed'    // ✅ Zakończony
  | 'missed'       // ❌ Przegapiony
```

### 4.2 Przykład Milestone

```yaml
milestone:
  id: "M3.2"
  name: "Homepage Complete"
  phase: 3
  dueDate: "Week 7, Day 5"
  status: "pending"
  
  criteria:
    - "All 11 sections implemented"
    - "AOS animations working"
    - "Mobile responsive verified"
    - "Performance LCP < 2.5s"
    - "SEO meta tags implemented"
  
  deliverables:
    - "front-page.php"
    - "template-parts/sections/*"
    - "assets/js/custom/animations.ts"
  
  owner: "WordPress Developer"
  
  dependencies:
    - "M3.1"  # Theme Foundation Complete
  
  signOff:
    approved: false
    approvedBy: null
    approvedDate: null
```

---

## 5. Task Schema

### 5.1 Task Structure

```typescript
interface Task {
  id: string;                   // Unikalny ID: T1, T2, T3...
  title: string;                // Tytuł zadania
  description: string;          // Opis
  phase: number;                // Numer fazy
  milestone?: string;           // Powiązany milestone ID
  status: TaskStatus;           // Status
  priority: TaskPriority;       // Priorytet
  assignee?: string;            // Przypisana osoba
  estimatedHours?: number;      // Szacowane godziny
  actualHours?: number;         // Rzeczywiste godziny
  dueDate?: string;             // Termin
  completedDate?: string;       // Data ukończenia
  dependencies?: string[];      // Zależności
  tags: string[];               // Tagi (php, css, ts, seo, etc.)
  checklist?: ChecklistItem[];  // Checklista
  attachments?: string[];       // Załączniki
  comments?: Comment[];         // Komentarze
}

type TaskStatus = 
  | 'todo'         // ⬜ Do zrobienia
  | 'in_progress'  // 🟙 W trakcie
  | 'review'       // 🟡 Do review
  | 'done'         // ✅ Zakończone
  | 'blocked'      // 🚫 Zablokowane

type TaskPriority = 
  | 'critical'     // 🔴 Krytyczne
  | 'high'         // 🟠 Wysoki
  | 'medium'       // 🟡 Średni
  | 'low'          // 🟢 Niski
```

### 5.2 Checklist Item

```typescript
interface ChecklistItem {
  id: string;
  text: string;
  completed: boolean;
  completedBy?: string;
  completedDate?: string;
}
```

### 5.3 Przykład Task

```yaml
task:
  id: "T3.15"
  title: "Implement Contact Form AJAX Handler"
  description: "Create AJAX handler for contact form submission with validation and nonce verification"
  
  phase: 3
  milestone: "M3.5"  # Development Complete
  
  status: "todo"
  priority: "high"
  
  assignee: "WordPress Developer"
  estimatedHours: 4
  dueDate: "Week 10, Day 2"
  
  dependencies:
    - "T3.12"  # Contact Form UI
  
  tags:
    - "php"
    - "ajax"
    - "security"
    - "forms"
  
  checklist:
    - id: "1"
      text: "Create AJAX handler function"
      completed: false
    - id: "2"
      text: "Add nonce verification"
      completed: false
    - id: "3"
      text: "Implement input sanitization"
      completed: false
    - id: "4"
      text: "Add server-side validation"
      completed: false
    - id: "5"
      text: "Implement email sending"
      completed: false
    - id: "6"
      text: "Add success/error responses"
      completed: false
    - id: "7"
      text: "Test with various inputs"
      completed: false
```

---

## 6. Risk Schema

### 6.1 Risk Structure

```typescript
interface Risk {
  id: string;                   // Unikalny ID: R1, R2, R3...
  title: string;                // Tytuł ryzyka
  description: string;          // Opis
  category: RiskCategory;       // Kategoria
  probability: RiskLevel;       // Prawdopodobieństwo
  impact: RiskLevel;            // Wpływ
  severity: number;             // Poważność (probability × impact)
  status: RiskStatus;           // Status
  owner: string;                // Właściciel
  mitigation: string[];         // Strategia mitygacji
  contingency?: string;         // Plan awaryjny
  triggers?: string[];          // Wyzwalacze
  dateIdentified: string;       // Data identyfikacji
  dateResolved?: string;        // Data rozwiązania
}

type RiskCategory = 
  | 'technical'     # Techniczne
  | 'schedule'      # Harmonogram
  | 'budget'        # Budżet
  | 'scope'         # Zakres
  | 'quality'       # Jakość
  | 'resource'      # Zasoby
  | 'external'      # Zewnętrzne

type RiskLevel = 
  | 'very_low'   // 1
  | 'low'        // 2
  | 'medium'     // 3
  | 'high'       // 4
  | 'very_high'  // 5

type RiskStatus = 
  | 'identified'   // Zidentyfikowane
  | 'active'       // Aktywne
  | 'mitigated'    // Zmitigowane
  | 'closed'       // Zamknięte
```

### 6.2 Risk Matrix

```
┌─────────────────────────────────────────────────────────────────┐
│                      RISK MATRIX                                │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  IMPACT ↓  |  1 (VL)  |  2 (L)  |  3 (M)  |  4 (H)  |  5 (VH) │
│  ──────────┼──────────┼─────────┼─────────┼─────────┼─────────│
│  5 (VH)    │    5     │   10    │   15    │   20    │   25    │
│  4 (H)     │    4     │    8    │   12    │   16    │   20    │
│  3 (M)     │    3     │    6    │    9    │   12    │   15    │
│  2 (L)     │    2     │    4    │    6    │    8    │   10    │
│  1 (VL)    │    1     │    2    │    3    │    4    │    5    │
│                                                                 │
│  Severity Score: Probability × Impact                          │
│  1-5:   Low (Green)     — Monitor                               │
│  6-10: Medium (Yellow)  — Mitigation plan needed               │
│  11-15: High (Orange)   — Immediate action required            │
│  16-25: Critical (Red)  — Escalate, contingency plan           │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

### 6.3 Przykład Risk

```yaml
risk:
  id: "R3"
  title: "Content Delays"
  description: "Client may not provide content on time, delaying development and launch"
  
  category: "schedule"
  probability: "medium"     # 3
  impact: "high"            # 4
  severity: 12              # 3 × 4 = 12 (High)
  
  status: "active"
  owner: "Project Manager"
  
  mitigation:
    - "Provide content template early (Week 1)"
    - "Set clear content deadlines in contract"
    - "Prepare placeholder content as backup"
    - "Schedule weekly content check-ins"
  
  contingency:
    - "Use AI-generated content as temporary placeholder"
    - "Launch with core pages only, add remaining content post-launch"
  
  triggers:
    - "No content received by Week 3"
    - "Client misses 2+ content deadlines"
  
  dateIdentified: "2026-02-26"
```

---

## 7. KPI Schema

### 7.1 KPI Structure

```typescript
interface KPI {
  id: string;                   // Unikalny ID: KPI1, KPI2...
  name: string;                 // Nazwa
  description: string;          // Opis
  category: KPICategory;        // Kategoria
  baseline?: number;            // Wartość bazowa
  target: number;               // Cel
  current?: number;             // Aktualna wartość
  unit: string;                 // Jednostka
  status: KPIStatus;            // Status
  trend: KPITrend;              // Trend
  lastUpdated: string;          // Ostatnia aktualizacja
  owner: string;                // Właściciel
}

type KPICategory = 
  | 'performance'   // Performance
  | 'seo'          // SEO
  | 'quality'       // Jakość
  | 'business'      // Biznes
  | 'security'      // Bezpieczeństwo

type KPIStatus = 
  | 'on_track'     // ✅ Na torze
  | 'at_risk'      // ⚠️ Zagrożony
  | 'off_track'    // ❌ Poza torem
  | 'achieved'     // 🎯 Osiągnięty

type KPITrend = 
  | 'improving'    // 📈 Poprawia się
  | 'stable'       // ➡️ Stabilny
  | 'declining'    // 📉 Spada
```

### 7.2 Technical KPIs

```yaml
kpis:
  technical:
    - id: "KPI-T1"
      name: "PageSpeed Mobile"
      description: "Google PageSpeed Insights score for mobile"
      category: "performance"
      baseline: 0
      target: 90
      unit: "score (0-100)"
      status: "on_track"
      trend: "improving"
    
    - id: "KPI-T2"
      name: "PageSpeed Desktop"
      description: "Google PageSpeed Insights score for desktop"
      category: "performance"
      baseline: 0
      target: 95
      unit: "score (0-100)"
    
    - id: "KPI-T3"
      name: "LCP (Largest Contentful Paint)"
      description: "Time to render largest content element"
      category: "performance"
      baseline: 0
      target: 2.5
      unit: "seconds"
    
    - id: "KPI-T4"
      name: "CLS (Cumulative Layout Shift)"
      description: "Measure of visual stability"
      category: "performance"
      baseline: 0
      target: 0.1
      unit: "score"
    
    - id: "KPI-T5"
      name: "INP (Interaction to Next Paint)"
      description: "Responsiveness to user interactions"
      category: "performance"
      baseline: 0
      target: 100
      unit: "milliseconds"
    
    - id: "KPI-T6"
      name: "Accessibility Score"
      description: "Lighthouse accessibility audit score"
      category: "quality"
      baseline: 0
      target: 90
      unit: "score (0-100)"
    
    - id: "KPI-T7"
      name: "SEO Score"
      description: "Lighthouse SEO audit score"
      category: "seo"
      baseline: 0
      target: 100
      unit: "score (0-100)"
    
    - id: "KPI-T8"
      name: "Security Score"
      description: "Security audit score"
      category: "security"
      baseline: 0
      target: 100
      unit: "score (0-100)"
```

### 7.3 Business KPIs

```yaml
kpis:
  business:
    - id: "KPI-B1"
      name: "Organic Traffic"
      description: "Monthly organic search traffic"
      category: "business"
      baseline: 0
      target: 5000
      unit: "visits/month"
      timeline: "12 months"
    
    - id: "KPI-B2"
      name: "Keyword Rankings (Top 3)"
      description: "Number of keywords in top 3 search results"
      category: "seo"
      baseline: 0
      target: 20
      unit: "keywords"
      timeline: "12 months"
    
    - id: "KPI-B3"
      name: "Lead Forms per Month"
      description: "Monthly contact form submissions"
      category: "business"
      baseline: 0
      target: 30
      unit: "forms/month"
    
    - id: "KPI-B4"
      name: "Bounce Rate"
      description: "Percentage of single-page sessions"
      category: "business"
      baseline: 0
      target: 40
      unit: "percentage"
    
    - id: "KPI-B5"
      name: "Domain Rating"
      description: "Ahrefs Domain Rating"
      category: "seo"
      baseline: 0
      target: 25
      unit: "score (0-100)"
      timeline: "12 months"
```

---

## 8. JSON Schema

### 8.1 Full Roadmap JSON Schema

```json
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "$id": "https://alubram.at/schema/roadmap.json",
  "title": "ALUBRAM Project Roadmap",
  "type": "object",
  "properties": {
    "project": {
      "type": "object",
      "properties": {
        "name": { "type": "string" },
        "client": { "type": "string" },
        "repository": { "type": "string" },
        "version": { "type": "string" },
        "lastUpdated": { "type": "string", "format": "date" }
      },
      "required": ["name", "client", "repository"]
    },
    "timeline": {
      "type": "object",
      "properties": {
        "startDate": { "type": "string", "format": "date" },
        "endDate": { "type": "string", "format": "date" },
        "totalWeeks": { "type": "integer", "minimum": 1 },
        "currentPhase": { "type": "integer", "minimum": 1, "maximum": 6 }
      }
    },
    "phases": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "number": { "type": "integer", "minimum": 1, "maximum": 6 },
          "name": { "type": "string" },
          "description": { "type": "string" },
          "duration": { "type": "integer", "minimum": 1 },
          "status": { 
            "type": "string", 
            "enum": ["not_started", "in_progress", "completed", "blocked", "at_risk"]
          },
          "deliverables": {
            "type": "array",
            "items": { "type": "string" }
          },
          "milestones": {
            "type": "array",
            "items": { "$ref": "#/definitions/milestone" }
          },
          "tasks": {
            "type": "array",
            "items": { "$ref": "#/definitions/task" }
          },
          "owner": { "type": "string" }
        },
        "required": ["number", "name", "duration", "status"]
      }
    },
    "kpis": {
      "type": "array",
      "items": { "$ref": "#/definitions/kpi" }
    },
    "risks": {
      "type": "array",
      "items": { "$ref": "#/definitions/risk" }
    }
  },
  "definitions": {
    "milestone": {
      "type": "object",
      "properties": {
        "id": { "type": "string" },
        "name": { "type": "string" },
        "phase": { "type": "integer" },
        "dueDate": { "type": "string" },
        "status": { 
          "type": "string", 
          "enum": ["pending", "at_risk", "completed", "missed"]
        },
        "criteria": {
          "type": "array",
          "items": { "type": "string" }
        }
      }
    },
    "task": {
      "type": "object",
      "properties": {
        "id": { "type": "string" },
        "title": { "type": "string" },
        "status": { 
          "type": "string", 
          "enum": ["todo", "in_progress", "review", "done", "blocked"]
        },
        "priority": { 
          "type": "string", 
          "enum": ["critical", "high", "medium", "low"]
        },
        "assignee": { "type": "string" },
        "estimatedHours": { "type": "number" }
      }
    },
    "risk": {
      "type": "object",
      "properties": {
        "id": { "type": "string" },
        "title": { "type": "string" },
        "probability": { 
          "type": "string", 
          "enum": ["very_low", "low", "medium", "high", "very_high"]
        },
        "impact": { 
          "type": "string", 
          "enum": ["very_low", "low", "medium", "high", "very_high"]
        },
        "severity": { "type": "integer", "minimum": 1, "maximum": 25 },
        "mitigation": {
          "type": "array",
          "items": { "type": "string" }
        }
      }
    },
    "kpi": {
      "type": "object",
      "properties": {
        "id": { "type": "string" },
        "name": { "type": "string" },
        "target": { "type": "number" },
        "current": { "type": "number" },
        "unit": { "type": "string" },
        "status": { 
          "type": "string", 
          "enum": ["on_track", "at_risk", "off_track", "achieved"]
        }
      }
    }
  }
}
```

---

## 9. Przykłady Użycia

### 9.1 GitHub Project Board

```yaml
# .github/project-board.yml
project:
  name: "ALUBRAM GMBH WordPress"
  columns:
    - name: "📋 Backlog"
      filters:
        status: "todo"
    
    - name: "🟙 In Progress"
      filters:
        status: "in_progress"
    
    - name: "🟡 In Review"
      filters:
        status: "review"
    
    - name: "✅ Done"
      filters:
        status: "done"
    
    - name: "🚫 Blocked"
      filters:
        status: "blocked"

labels:
  - name: "phase:discovery"
    color: "1d76db"
  - name: "phase:design"
    color: "0e8a16"
  - name: "phase:development"
    color: "fbca04"
  - name: "phase:testing"
    color: "ff9f1c"
  - name: "phase:deployment"
    color: "e11d48"
  - name: "priority:critical"
    color: "b60205"
  - name: "priority:high"
    color: "ff9f1c"
  - name: "priority:medium"
    color: "fbca04"
  - name: "priority:low"
    color: "0e8a16"
```

### 9.2 Progress Tracking Script

```typescript
// scripts/calculate-progress.ts

interface Phase {
  number: number;
  status: string;
  tasks: Task[];
}

interface Task {
  status: string;
}

function calculateProgress(phases: Phase[]): number {
  const totalTasks = phases.reduce(
    (sum, phase) => sum + phase.tasks.length, 
    0
  );
  
  const completedTasks = phases.reduce(
    (sum, phase) => sum + phase.tasks.filter(t => t.status === 'done').length, 
    0
  );
  
  return Math.round((completedTasks / totalTasks) * 100);
}

// Usage
const progress = calculateProgress(projectPhases);
console.log(`Project Progress: ${progress}%`);
```

### 9.3 Status Report Template

```markdown
# Weekly Status Report

**Week:** [X]  
**Date:** [YYYY-MM-DD]  
**Report By:** [Name]

## Executive Summary
- **Overall Status:** 🟢 On Track / 🟡 At Risk / 🔴 Off Track
- **Progress:** [X]% complete
- **Current Phase:** Phase [X] - [Name]

## This Week's Accomplishments
- [ ] Task 1 completed
- [ ] Task 2 completed
- [ ] Task 3 completed

## Next Week's Plan
- [ ] Task 4 planned
- [ ] Task 5 planned
- [ ] Task 6 planned

## Blockers & Risks
| ID | Description | Impact | Mitigation |
|----|-------------|--------|------------|
| R1 | [Risk] | [High/Med/Low] | [Action] |

## KPIs Status
| KPI | Target | Current | Status |
|-----|--------|---------|--------|
| PageSpeed Mobile | 90 | [X] | 🟢/🟡/🔴 |
| PageSpeed Desktop | 95 | [X] | 🟢/🟡/🔴 |
| LCP | < 2.5s | [X]s | 🟢/🟡/🔴 |

## Decisions Needed
- [Decision 1]
- [Decision 2]
```

---

*ROADMAP.SCHEMA.md — ALUBRAM GMBH WordPress Project | v1.0.0 | 2026-02-26*
