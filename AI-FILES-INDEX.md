# AI-FILES-INDEX.md — AI Files Index & Reference

> **Dokument:** Indeks i reference wszystkich plików konfiguracyjnych AI
> **Projekt:** `piotroq/alubram-gmbh-wordpress`
> **Wersja:** 1.0.0 | 2026-02-26

---

## 📋 Spis Treści

1. [Overview](#1-overview)
2. [Claude AI Files](#2-claude-ai-files)
3. [Qwen AI Files](#3-qwen-ai-files)
4. [Ollama Files](#4-ollama-files)
5. [VS Code Extension Files](#5-vs-code-extension-files)
6. [Project Context Files](#6-project-context-files)
7. [File Structure Diagram](#7-file-structure-diagram)

---

## 1. Overview

### 1.1 File Categories

| Category | Location | Purpose |
|----------|----------|---------|
| **Claude Config** | `.claude/` | Claude AI agents, prompts, settings |
| **Qwen Config** | `.qwen/` | Qwen AI agents, skills |
| **Ollama Config** | `ollama/` (optional) | Local models, Modelfiles |
| **VS Code Config** | `.vscode/` | Extension settings |
| **Documentation** | Root `*.md` | Usage guides |
| **Context Files** | `docs/` | Project knowledge |

### 1.2 Quick Reference

| File | Purpose | Required |
|------|---------|----------|
| `CLAUDE.md` | Claude usage guide | ✅ |
| `QWEN.md` | Qwen usage guide | ✅ |
| `OLLAMA.md` | Ollama setup guide | ✅ |
| `AI-CONFIGURATION-README.md` | Full AI config | ✅ |
| `.claude/settings.local.json` | Claude settings | ✅ |
| `.qwen/settings.json` | Qwen settings | ✅ |
| `TECHNICAL-SHEETS.md` | Master instructions | ✅ |
| `BRAND-SETTINGS.md` | Brand guidelines | ✅ |

---

## 2. Claude AI Files

### 2.1 Directory Structure

```
.claude/
├── settings.local.json           # Global Claude settings
├── CLAUDE.md                     # Link to root CLAUDE.md
├── agents/
│   ├── business-product/
│   │   └── wordpress-master.md   # WordPress expert agent
│   ├── code-review/
│   │   └── php-reviewer.md       # PHP code reviewer
│   ├── seo/
│   │   └── seo-de-specialist.md  # SEO DE/AT specialist
│   ├── design/
│   │   └── ui-ux-designer.md     # UI/UX designer
│   └── security/
│       └── wp-security-auditor.md # Security auditor
├── prompts/
│   ├── all-prompts.md            # All prompts collection
│   └── system-prompts/
│       ├── agent-prompt-*.md     # System prompts
└── skills/
    └── *.md                      # Custom skills
```

### 2.2 File Descriptions

#### `.claude/settings.local.json`

**Purpose:** Global Claude AI settings

**Content:**
```json
{
  "model": "claude-sonnet-4-20260101",
  "maxTokens": 4096,
  "temperature": 0.2,
  "topP": 0.9,
  "contextFiles": [
    "TECHNICAL-SHEETS.md",
    "BRAND-SETTINGS.md",
    "docs/ARCHITECTURE.md",
    "docs/DESIGN-SYSTEM.md"
  ],
  "systemMessage": "You are a WordPress expert working on ALUBRAM GMBH project."
}
```

#### `.claude/agents/business-product/wordpress-master.md`

**Purpose:** WordPress development expert agent

**Content:**
```markdown
---
name: wordpress-master
description: Elite WordPress architect specializing in full-stack development
tools: Read, Write, Edit, Bash, Glob, Grep, WebFetch, WebSearch
---

You are a senior WordPress architect with 15+ years of expertise...

WordPress mastery checklist:
- Page load < 1.5s achieved
- Security score 100/100 maintained
- Core Web Vitals passed excellently
...
```

#### `.claude/agents/code-review/php-reviewer.md`

**Purpose:** PHP code review specialist

**Content:**
```markdown
---
name: php-reviewer
description: PHP code review specialist for PSR-12 and WordPress standards
---

You are a PHP code review specialist...

Review checklist:
### Security
- [ ] if (!defined('ABSPATH')) { exit; }
- [ ] All echo with esc_html()/esc_url()
...
```

### 2.3 Prompts Collection

#### `.claude/prompts/all-prompts.md`

**Purpose:** Collection of all reusable prompts

**Content:**
```markdown
# All Prompts Collection

## Code Generation
- Template generation prompt
- CPT registration prompt
- Function generation prompt

## Code Review
- Security review prompt
- PSR-12 review prompt
- Performance review prompt

## Debugging
- Error analysis prompt
- Root cause prompt
...
```

---

## 3. Qwen AI Files

### 3.1 Directory Structure

```
.qwen/
├── settings.json                 # Qwen settings
├── agents/
│   └── *.md                      # Qwen agents
└── skills/
    └── *.md                      # Qwen skills
```

### 3.2 File Descriptions

#### `.qwen/settings.json`

**Purpose:** Qwen AI configuration

**Content:**
```json
{
  "model": "qwen2.5-coder-32b-instruct",
  "maxTokens": 4096,
  "temperature": 0.2,
  "topP": 0.9,
  "apiKey": "sk-xxx",
  "apiBase": "https://dashscope.aliyuncs.com/api/v1"
}
```

#### `.qwen/agents/*.md`

**Purpose:** Qwen agent definitions

**Example:**
```markdown
---
name: qwen-wordpress
model: qwen2.5-coder-32b-instruct
---

You are a WordPress expert using Qwen model...
```

---

## 4. Ollama Files

### 4.1 Directory Structure (Optional)

```
ollama/
├── Modelfile                     # Custom model definition
├── config.json                   # Ollama config
└── scripts/
    ├── pull-models.sh            # Model pull script
    └── run-chat.sh               # Chat runner
```

### 4.2 File Descriptions

#### `ollama/Modelfile`

**Purpose:** Custom Ollama model definition

**Content:**
```dockerfile
FROM qwen2.5-coder:32b

SYSTEM """
You are an expert WordPress developer working on ALUBRAM GMBH project.
Always follow these rules:
1. Use strict_types=1 in PHP
2. Escape all output
3. Sanitize all input
4. Use brand colors
5. Add AOS animations
6. Write German content (de_AT)
"""

PARAMETER temperature 0.2
PARAMETER top_p 0.9
PARAMETER num_ctx 4096
```

#### `ollama/scripts/pull-models.sh`

**Purpose:** Script to pull all required models

**Content:**
```bash
#!/bin/bash

# Pull Qwen models
ollama pull qwen2.5-coder:32b
ollama pull qwen2.5-coder:7b

# Pull Llama models
ollama pull llama3.1:8b
ollama pull llama3.1:70b

# Pull Codellama
ollama pull codellama:34b

echo "All models pulled successfully!"
```

---

## 5. VS Code Extension Files

### 5.1 Directory Structure

```
.vscode/
├── settings.json                 # VS Code settings
├── extensions.json               # Recommended extensions
└── launch.json                   # Debug configurations
```

### 5.2 File Descriptions

#### `.vscode/settings.json`

**Purpose:** VS Code workspace settings

**Content:**
```json
{
  "editor.formatOnSave": true,
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "[php]": {
    "editor.defaultFormatter": "devsense.intelephense-php"
  },
  "[typescript]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "continue.systemMessage": "WordPress expert for ALUBRAM GMBH",
  "codegpt.provider": "anthropic",
  "codegpt.anthropic.model": "claude-sonnet-4-20260101"
}
```

#### `.vscode/extensions.json`

**Purpose:** Recommended extensions

**Content:**
```json
{
  "recommendations": [
    "anthropic.claude-vscode",
    "continue.continue",
    "github.copilot",
    "github.copilot-chat",
    "ms-python.python",
    "devsense.intelephense-php",
    "esbenp.prettier-vscode"
  ]
}
```

---

## 6. Project Context Files

### 6.1 Root Documentation

| File | Purpose | Size |
|------|---------|------|
| `TECHNICAL-SHEETS.md` | Master instructions | 757 lines |
| `CLAUDE.md` | Claude usage guide | 650 lines |
| `QWEN.md` | Qwen usage guide | 650 lines |
| `OLLAMA.md` | Ollama setup guide | 700 lines |
| `AI-CONFIGURATION-README.md` | Full AI config | 500 lines |
| `AGENTS.mde` | Agents documentation | 600 lines |
| `PROJECT-SPECIFICATION.md` | Project specs | 1000 lines |
| `PAGES-WIREFRAMES.md` | Wireframes | 900 lines |
| `ROADMAP.SCHEMA.md` | Roadmap schema | 900 lines |
| `CONTRIBUTING.md` | Contribution guide | 800 lines |

### 6.2 docs/ Directory

```
docs/
├── ARCHITECTURE.md               # Technical architecture (671 lines)
├── BRAND-SETTINGS.md             # Brand guidelines (521 lines)
├── DESIGN-SYSTEM.md              # Design system (1161 lines)
├── README.agents.md              # Agents overview
├── README.collections.md         # Resources collection
└── analiza-elementów-logo-alubram.md  # Logo analysis
```

### 6.3 Context Loading Order

**Priority 1 (Always Load):**
```
1. TECHNICAL-SHEETS.md      ← Master instructions
2. BRAND-SETTINGS.md        ← Colors, fonts, brand
3. docs/ARCHITECTURE.md     ← Technical structure
```

**Priority 2 (As Needed):**
```
4. docs/DESIGN-SYSTEM.md    ← Components, patterns
5. PAGES-WIREFRAMES.md      ← Layout specifications
6. PROJECT-SPECIFICATION.md ← Requirements
```

**Priority 3 (Reference):**
```
7. CLAUDE.md                ← AI usage guide
8. QWEN.md                  ← Qwen usage guide
9. OLLAMA.md                ← Ollama setup
```

---

## 7. File Structure Diagram

### 7.1 Complete Structure

```
alubram-gmbh-wordpress/
│
├── 📄 README.md                        ← Project readme
├── 📄 TECHNICAL-SHEETS.md              ← Master instructions
├── 📄 CLAUDE.md                        ← Claude guide
├── 📄 QWEN.md                          ← Qwen guide
├── 📄 OLLAMA.md                        ← Ollama guide
├── 📄 AI-CONFIGURATION-README.md       ← Full AI config
├── 📄 AGENTS.mde                       ← Agents documentation
├── 📄 AI-FILES-INDEX.md                ← This file
├── 📄 PROJECT-SPECIFICATION.md         ← Project specs
├── 📄 PAGES-WIREFRAMES.md              ← Wireframes
├── 📄 ROADMAP.SCHEMA.md                ← Roadmap schema
├── 📄 CONTRIBUTING.md                  ← Contribution guide
├── 📄 FETCH-TEMPLATE-WEBSITE.md        ← Fetch template
│
├── 📁 .claude/                         ← Claude AI config
│   ├── settings.local.json
│   ├── agents/
│   │   ├── business-product/
│   │   │   └── wordpress-master.md
│   │   ├── code-review/
│   │   │   └── php-reviewer.md
│   │   ├── seo/
│   │   │   └── seo-de-specialist.md
│   │   ├── design/
│   │   │   └── ui-ux-designer.md
│   │   └── security/
│   │       └── wp-security-auditor.md
│   ├── prompts/
│   │   ├── all-prompts.md
│   │   └── system-prompts/
│   └── skills/
│
├── 📁 .qwen/                           ← Qwen AI config
│   ├── settings.json
│   ├── agents/
│   └── skills/
│
├── 📁 .vscode/                         ← VS Code config
│   ├── settings.json
│   └── extensions.json
│
├── 📁 docs/                            ← Documentation
│   ├── ARCHITECTURE.md
│   ├── BRAND-SETTINGS.md
│   ├── DESIGN-SYSTEM.md
│   ├── README.agents.md
│   ├── README.collections.md
│   └── analiza-elementów-logo-alubram.md
│
└── 📁 ollama/                          ← Ollama config (optional)
    ├── Modelfile
    ├── config.json
    └── scripts/
```

### 7.2 File Size Summary

| Category | Files | Total Lines |
|----------|-------|-------------|
| **Root MD** | 12 files | ~8,000 lines |
| **Claude Config** | 10+ files | ~3,000 lines |
| **Qwen Config** | 5+ files | ~1,000 lines |
| **Docs** | 6 files | ~4,000 lines |
| **TOTAL** | 33+ files | ~16,000 lines |

---

## 8. Quick Reference Table

### 8.1 Essential Files

| File | When to Use |
|------|-------------|
| `TECHNICAL-SHEETS.md` | Always - master instructions |
| `BRAND-SETTINGS.md` | Design/color questions |
| `CLAUDE.md` | Using Claude AI |
| `QWEN.md` | Using Qwen AI |
| `OLLAMA.md` | Using local Ollama |
| `AGENTS.mde` | Agent configuration |
| `CONTRIBUTING.md` | Contributing code |

### 8.2 Agent Files

| Agent | File | Purpose |
|-------|------|---------|
| wordpress-master | `.claude/agents/business-product/wordpress-master.md` | WordPress dev |
| php-reviewer | `.claude/agents/code-review/php-reviewer.md` | Code review |
| seo-de-specialist | `.claude/agents/seo/seo-de-specialist.md` | SEO DE/AT |
| ui-ux-designer | `.claude/agents/design/ui-ux-designer.md` | UI/UX design |
| wp-security-auditor | `.claude/agents/security/wp-security-auditor.md` | Security audit |

---

*AI-FILES-INDEX.md — ALUBRAM GMBH WordPress Project | v1.0.0 | 2026-02-26*
