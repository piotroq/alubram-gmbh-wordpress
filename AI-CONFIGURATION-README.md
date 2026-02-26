# AI-CONFIGURATION-README.md — AI Configuration Guide

> **Dokument:** Kompletny przewodnik konfiguracji AI dla projektu ALUBRAM GMBH
> **Projekt:** `piotroq/alubram-gmbh-wordpress`
> **Wersja:** 1.0.0 | 2026-02-26

---

## 📋 Spis Treści

1. [Wprowadzenie](#1-wprowadzenie)
2. [Claude AI Configuration](#2-claude-ai-configuration)
3. [Qwen AI Configuration](#3-qwen-ai-configuration)
4. [Ollama Local AI Configuration](#4-ollama-local-ai-configuration)
5. [GitHub Copilot Configuration](#5-github-copilot-configuration)
6. [Cursor AI Configuration](#6-cursor-ai-configuration)
7. [VS Code Extensions](#7-vs-code-extensions)
8. [Environment Setup](#8-environment-setup)

---

## 1. Wprowadzenie

### 1.1 Dostępne Modele AI

Projekt ALUBRAM GMBH używa wielu modeli AI do wspomagania developmentu:

| Model | Provider | Zastosowanie | Cost |
|-------|----------|-------------|------|
| **Claude Sonnet 4.6** | Anthropic | Primary code generation | Paid |
| **Claude Opus 4.6** | Anthropic | Complex tasks, architecture | Paid |
| **Qwen 2.5 Coder 32B** | Alibaba | Code generation, reviews | Free/Paid |
| **Qwen 2.5 Coder 7B** | Alibaba | Fast completion | Free |
| **Llama 3.1** | Meta | General purpose (via Ollama) | Free |
| **Codellama 34B** | Meta | Code-specific (via Ollama) | Free |
| **GitHub Copilot** | GitHub | Autocomplete | Paid |

### 1.2 Architektura

```
┌─────────────────────────────────────────────────────────────────┐
│                    AI CONFIGURATION STACK                       │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  Cloud-Based:                                                   │
│  ┌─────────────────┐  ┌─────────────────┐  ┌─────────────────┐ │
│  │  Claude.ai      │  │  Qwen DashScope │  │  GitHub Copilot │ │
│  │  (Primary)      │  │  (Alternative)  │  │  (Autocomplete) │ │
│  └─────────────────┘  └─────────────────┘  └─────────────────┘ │
│                                                                 │
│  Local (Ollama):                                                │
│  ┌─────────────────┐  ┌─────────────────┐  ┌─────────────────┐ │
│  │  Qwen 2.5 32B   │  │  Llama 3.1 70B  │  │  Codellama 34B  │ │
│  └─────────────────┘  └─────────────────┘  └─────────────────┘ │
│                                                                 │
│  IDE Integration:                                               │
│  ┌─────────────────┐  ┌─────────────────┐  ┌─────────────────┐ │
│  │  Continue.dev   │  │  CodeGPT        │  │  Twinny         │ │
│  └─────────────────┘  └─────────────────┘  └─────────────────┘ │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

---

## 2. Claude AI Configuration

### 2.1 Claude.ai (Web Interface)

**Krok 1: Logowanie**
```
1. Odwiedź https://claude.ai
2. Zaloguj się (Google/Email)
3. Utwórz nowy projekt "ALUBRAM GMBH WordPress"
```

**Krok 2: Konfiguracja Projektu**
```
1. W project settings dodaj kontekst:
   - TECHNICAL-SHEETS.md
   - BRAND-SETTINGS.md
   - docs/ARCHITECTURE.md
   - docs/DESIGN-SYSTEM.md

2. Ustaw domyślny model:
   - Claude Sonnet 4.6 (domyślnie)
   - Claude Opus 4.6 (dla complex tasks)
```

**Krok 3: System Prompt**
```markdown
You are an expert WordPress developer working on the ALUBRAM GMBH project.

Project Context:
- Client: ALUBRAM GMBH, Austrian aluminum fence manufacturer
- Language: German (de_AT)
- Stack: WordPress 6.9, PHP 8.2+, TypeScript, Tailwind CSS

Always follow these rules:
1. Use strict_types=1 in PHP
2. Escape all output (esc_html, esc_url, esc_attr)
3. Sanitize all input (sanitize_text_field, sanitize_email)
4. Use brand colors from BRAND-SETTINGS.md
5. Add AOS animations to sections
6. Write German content (de_AT)
7. Follow PSR-12 and WordPress Coding Standards
```

### 2.2 Claude API

**Krok 1: API Key**
```bash
# Get API key from https://console.anthropic.com
export ANTHROPIC_API_KEY="sk-ant-xxxxxxxxxxxxxxxx"
```

**Krok 2: Python SDK**
```python
# Install
pip install anthropic

# Usage
import anthropic

client = anthropic.Anthropic(api_key="sk-ant-xxx")

response = client.messages.create(
    model="claude-sonnet-4-20260101",
    max_tokens=4096,
    system="You are a WordPress expert. Always use strict_types=1.",
    messages=[
        {"role": "user", "content": "Generate WordPress contact form template"}
    ]
)

print(response.content[0].text)
```

**Krok 3: Node.js SDK**
```javascript
// Install
npm install @anthropic-ai/sdk

// Usage
import Anthropic from '@anthropic-ai/sdk';

const anthropic = new Anthropic({
  apiKey: process.env.ANTHROPIC_API_KEY,
});

const response = await anthropic.messages.create({
  model: 'claude-sonnet-4-20260101',
  max_tokens: 4096,
  system: 'You are a WordPress expert.',
  messages: [
    { role: 'user', content: 'Generate WordPress contact form template' }
  ]
});

console.log(response.content[0].text);
```

### 2.3 VS Code Integration (Continue.dev)

**Krok 1: Install Extension**
```
1. Open VS Code
2. Extensions → Search "Continue"
3. Install "Continue - Autocomplete & Chat"
```

**Krok 2: Configure**
```json
// .continue/config.json
{
  "models": [
    {
      "title": "Claude Sonnet 4.6",
      "provider": "anthropic",
      "model": "claude-sonnet-4-20260101",
      "apiKey": "sk-ant-xxx"
    },
    {
      "title": "Claude Opus 4.6",
      "provider": "anthropic",
      "model": "claude-opus-4-20260101",
      "apiKey": "sk-ant-xxx"
    }
  ],
  "tabAutocompleteModel": {
    "title": "Claude Sonnet 4.6",
    "provider": "anthropic",
    "model": "claude-sonnet-4-20260101"
  },
  "systemMessage": "You are a WordPress expert working on ALUBRAM GMBH project."
}
```

---

## 3. Qwen AI Configuration

### 3.1 Alibaba Cloud DashScope

**Krok 1: API Key**
```bash
# Register at https://dashscope.console.aliyun.com
export DASHSCOPE_API_KEY="sk-xxxxxxxxxxxxxxxx"
```

**Krok 2: Python SDK**
```python
# Install
pip install dashscope

# Usage
import dashscope
from dashscope import Generation

dashscope.api_key = "sk-xxx"

response = Generation.call(
    model="qwen2.5-coder-32b-instruct",
    prompt="Generate WordPress PHP template",
    max_tokens=4096
)

print(response.output.text)
```

### 3.2 Ollama (Local)

**Krok 1: Install Ollama**
```bash
# macOS
brew install ollama

# Linux
curl -fsSL https://ollama.com/install.sh | sh

# Windows
# Download from https://ollama.com/download/windows
```

**Krok 2: Pull Models**
```bash
# Pull Qwen 2.5 Coder
ollama pull qwen2.5-coder:32b

# Pull Llama 3.1
ollama pull llama3.1:8b

# List models
ollama list
```

**Krok 3: Run Model**
```bash
# Interactive mode
ollama run qwen2.5-coder:32b

# API call
curl http://localhost:11434/api/generate -d '{
  "model": "qwen2.5-coder:32b",
  "prompt": "Generate WordPress contact form",
  "stream": false
}'
```

**Krok 4: VS Code Integration**
```json
// .continue/config.json
{
  "models": [
    {
      "title": "Ollama - Qwen 2.5 Coder",
      "provider": "ollama",
      "model": "qwen2.5-coder:32b",
      "apiBase": "http://localhost:11434"
    }
  ]
}
```

---

## 4. Ollama Local AI Configuration

### 4.1 Full Setup Guide

**System Requirements:**
- RAM: 16-32 GB (for 32B models)
- GPU: Optional (NVIDIA 8GB+ VRAM recommended)
- Storage: 50 GB SSD

**Installation:**
```bash
# macOS
brew install ollama

# Linux
curl -fsSL https://ollama.com/install.sh | sh
sudo systemctl start ollama
sudo systemctl enable ollama

# Docker
docker run -d -v ollama:/root/.ollama -p 11434:11434 ollama/ollama
```

**Models:**
```bash
# Code generation (best)
ollama pull qwen2.5-coder:32b

# Code generation (fast)
ollama pull qwen2.5-coder:7b

# General purpose
ollama pull llama3.1:8b

# Code-specific
ollama pull codellama:34b
```

**Configuration:**
```bash
# Create Modelfile
cat > Modelfile << EOF
FROM qwen2.5-coder:32b

SYSTEM """
You are an expert WordPress developer working on ALUBRAM GMBH project.
Always use strict_types=1 in PHP.
Escape all output.
Write German content (de_AT).
"""

PARAMETER temperature 0.2
PARAMETER top_p 0.9
EOF

# Create custom model
ollama create alubram-dev -f Modelfile

# Run custom model
ollama run alubram-dev
```

### 4.2 API Usage

**Python Client:**
```python
import ollama

response = ollama.chat(
    model='qwen2.5-coder:32b',
    messages=[{
        'role': 'user',
        'content': 'Generate WordPress PHP template'
    }]
)

print(response['message']['content'])
```

**Node.js Client:**
```javascript
import ollama from 'ollama';

const response = await ollama.chat({
  model: 'qwen2.5-coder:32b',
  messages: [{
    role: 'user',
    content: 'Generate WordPress PHP template'
  }]
});

console.log(response.message.content);
```

---

## 5. GitHub Copilot Configuration

### 5.1 Installation

**Krok 1: Subscribe**
```
1. Visit https://github.com/settings/copilot
2. Start free trial or subscribe
3. Verify email
```

**Krok 2: Install Extension**
```
1. Open VS Code
2. Extensions → Search "GitHub Copilot"
3. Install "GitHub Copilot"
4. Sign in to GitHub
```

### 5.2 Configuration

**VS Code Settings:**
```json
{
  "github.copilot.enable": true,
  "github.copilot.editor.enableAutoCompletions": true,
  "github.copilot.chat.codeGeneration.enabled": true,
  "github.copilot.suggestions.inline.enabled": true
}
```

**Custom Instructions:**
```json
// .github/copilot-instructions.md
# GitHub Copilot Instructions for ALUBRAM GMBH

## Project Context
- WordPress 6.9 theme (alubramat-child)
- PHP 8.2+, strict_types=1
- TypeScript ES6+
- Tailwind CSS
- German language (de_AT)

## Code Style
- Always escape output: esc_html(), esc_url()
- Always sanitize input: sanitize_text_field()
- Use brand colors from BRAND-SETTINGS.md
- Add AOS animations: data-aos="fade-up"
```

---

## 6. Cursor AI Configuration

### 6.1 Installation

```
1. Download from https://cursor.sh
2. Install application
3. Sign in (Google/GitHub)
```

### 6.2 Configuration

**Settings:**
```json
{
  "ai.model": "claude-sonnet-4",
  "ai.temperature": 0.2,
  "ai.maxTokens": 4096,
  "context.files": [
    "TECHNICAL-SHEETS.md",
    "BRAND-SETTINGS.md",
    "docs/ARCHITECTURE.md"
  ]
}
```

**Rules:**
```
.cursorrules/php.mdc:
- Always use strict_types=1
- Escape all output
- Sanitize all input
- Follow PSR-12

.cursorrules/typescript.mdc:
- Use TypeScript strict mode
- Async/await pattern
- Type all functions
```

---

## 7. VS Code Extensions

### 7.1 Recommended Extensions

```json
{
  "recommendations": [
    "anthropic.claude-vscode",
    "continue.continue",
    "github.copilot",
    "github.copilot-chat",
    "ms-python.python",
    "ms-vscode.vscode-typescript-next",
    "devsense.intelephense-php",
    "wix.vscode-import-cost"
  ]
}
```

### 7.2 Extension Configuration

**Continue.dev:**
```json
// .continue/config.json
{
  "models": [
    {
      "title": "Claude Sonnet 4.6",
      "provider": "anthropic",
      "model": "claude-sonnet-4-20260101"
    },
    {
      "title": "Ollama - Qwen 2.5",
      "provider": "ollama",
      "model": "qwen2.5-coder:32b"
    }
  ],
  "tabAutocompleteModel": {
    "provider": "ollama",
    "model": "qwen2.5-coder:32b"
  },
  "systemMessage": "WordPress expert for ALUBRAM GMBH"
}
```

**CodeGPT:**
```json
// settings.json
{
  "codegpt.provider": "anthropic",
  "codegpt.anthropic.model": "claude-sonnet-4-20260101",
  "codegpt.anthropic.apiKey": "sk-ant-xxx",
  "codegpt.systemMessage": "WordPress expert"
}
```

---

## 8. Environment Setup

### 8.1 Environment Variables

```bash
# .env (do not commit to git)

# Claude API
ANTHROPIC_API_KEY=sk-ant-xxxxxxxxxxxxxxxx

# Qwen DashScope
DASHSCOPE_API_KEY=sk-xxxxxxxxxxxxxxxx

# Ollama
OLLAMA_HOST=http://localhost:11434
OLLAMA_MODEL=qwen2.5-coder:32b

# GitHub Copilot
GITHUB_TOKEN=ghp_xxxxxxxxxxxxxxxxxxxx

# General
AI_MODEL=claude-sonnet-4-20260101
AI_MAX_TOKENS=4096
AI_TEMPERATURE=0.2
```

### 8.2 Git Ignore

```gitignore
# AI Configuration (sensitive)
.env
.anthropic/
.dashscope/
.ollama-config.json

# AI generated content (optional)
ai-generated/
*.ai.md
```

### 8.3 Package.json Scripts

```json
{
  "scripts": {
    "ai:claude": "python scripts/claude-chat.py",
    "ai:qwen": "python scripts/qwen-chat.py",
    "ai:ollama": "ollama run qwen2.5-coder:32b",
    "ai:review": "python scripts/code-review.py"
  }
}
```

---

*AI-CONFIGURATION-README.md — ALUBRAM GMBH WordPress Project | v1.0.0 | 2026-02-26*
