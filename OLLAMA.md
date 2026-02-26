# OLLAMA.md — Ollama Local AI Configuration

> **Dokument:** Konfiguracja i instrukcje dla Ollama Local AI w projekcie ALUBRAM GMBH
> **Projekt:** `piotroq/alubram-gmbh-wordpress`
> **Modele:** Qwen 2.5 Coder, Llama 3.1, Mistral, Codellama
> **Wersja:** 1.0.0 | 2026-02-26

---

## 📋 Spis Treści

1. [Wprowadzenie](#1-wprowadzenie)
2. [Instalacja Ollama](#2-instalacja-ollama)
3. [Dostępne Modele](#3-dostępne-modele)
4. [Konfiguracja](#4-konfiguracja)
5. [Użycie z VS Code](#5-użycie-z-vs-code)
6. [API Reference](#6-api-reference)
7. [Przykłady Użycia](#7-przykłady-użycia)
8. [Troubleshooting](#8-troubleshooting)

---

## 1. Wprowadzenie

### 1.1 O Ollama

**Ollama** to narzędzie do lokalnego uruchamiania modeli AI (LLM) na Twoim komputerze.

**Zalety:**
- ✅ Działa offline (prywatność)
- ✅ Brak opłat za API
- ✅ Pełna kontrola nad danymi
- ✅ Szybkie odpowiedzi (no network latency)
- ✅ Wiele modeli do wyboru

**Zastosowanie w Projekcie:**
- Code generation (PHP, TypeScript, CSS)
- Code review i debugging
- Documentation writing
- Quick Q&A o projekcie

### 1.2 Wymagania Systemowe

| Komponent | Minimum | Recommended |
|-----------|---------|-------------|
| **RAM** | 8 GB | 16-32 GB |
| **GPU** | Optional | NVIDIA 8GB+ VRAM |
| **Storage** | 10 GB | 50 GB SSD |
| **OS** | macOS 12+, Windows 10+, Linux | Latest |

---

## 2. Instalacja Ollama

### 2.1 macOS

```bash
# Download and install
curl -fsSL https://ollama.com/install.sh | sh

# Or via Homebrew
brew install ollama

# Verify installation
ollama --version

# Start Ollama (runs as background service automatically)
ollama serve
```

### 2.2 Linux

```bash
# Download and install
curl -fsSL https://ollama.com/install.sh | sh

# Start as service
sudo systemctl start ollama
sudo systemctl enable ollama

# Verify
ollama --version
```

### 2.3 Windows

```powershell
# Download installer from https://ollama.com/download/windows
# Run OllamaSetup.exe

# Verify installation
ollama --version

# Start Ollama
ollama serve
```

### 2.4 Docker

```bash
# Pull Ollama image
docker pull ollama/ollama

# Run container
docker run -d -v ollama:/root/.ollama -p 11434:11434 --name ollama ollama/ollama

# Verify
docker exec -it ollama ollama --version
```

---

## 3. Dostępne Modele

### 3.1 Recommended Models for Development

| Model | Size | Best For | Command |
|-------|------|----------|---------|
| **Qwen 2.5 Coder 32B** | 32B | Code generation, reviews | `ollama pull qwen2.5-coder:32b` |
| **Qwen 2.5 Coder 7B** | 7B | Fast code completion | `ollama pull qwen2.5-coder:7b` |
| **Llama 3.1 70B** | 70B | General tasks, reasoning | `ollama pull llama3.1:70b` |
| **Llama 3.1 8B** | 8B | Fast responses | `ollama pull llama3.1:8b` |
| **Codellama 34B** | 34B | Code-specific tasks | `ollama pull codellama:34b` |
| **Mistral 7B** | 7B | General purpose | `ollama pull mistral:7b` |

### 3.2 Pulling Models

```bash
# Pull specific model
ollama pull qwen2.5-coder:32b

# Pull with specific quantization
ollama pull qwen2.5-coder:32b-q4_K_M

# List downloaded models
ollama list

# Remove model
ollama rm qwen2.5-coder:7b

# Update model
ollama pull qwen2.5-coder:32b
```

### 3.3 Model Comparison

```
┌─────────────────────────────────────────────────────────────────┐
│                    MODEL PERFORMANCE                            │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  Code Generation:                                               │
│  1. Qwen 2.5 Coder 32B  ████████████████████  (Best)           │
│  2. Codellama 34B       ██████████████████░░  (Great)           │
│  3. Llama 3.1 70B       █████████████████░░░  (Good)            │
│                                                                 │
│  Speed (responses/sec):                                         │
│  1. Mistral 7B          ████████████████████  (Fastest)         │
│  2. Llama 3.1 8B        ██████████████████░░  (Fast)            │
│  3. Qwen 2.5 Coder 7B   █████████████████░░░  (Fast)            │
│  4. Qwen 2.5 Coder 32B  ████████████░░░░░░░░  (Moderate)        │
│  5. Llama 3.1 70B       ██████████░░░░░░░░░░  (Slow)            │
│                                                                 │
│  RAM Requirements:                                              │
│  - 7B models:   ~4-8 GB                                        │
│  - 32B models:  ~16-24 GB                                      │
│  - 70B models:  ~32-48 GB                                      │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

---

## 4. Konfiguracja

### 4.1 Modelfile

**Modelfile** allows you to customize model behavior:

```dockerfile
# Create custom Modelfile
cat > Modelfile << EOF
FROM qwen2.5-coder:32b

# Set system message
SYSTEM """
You are an expert WordPress developer working on the ALUBRAM GMBH project.
Always follow these rules:
1. Use strict_types=1 in PHP
2. Escape all output (esc_html, esc_url, esc_attr)
3. Sanitize all input (sanitize_text_field, sanitize_email)
4. Use brand colors from BRAND-SETTINGS.md
5. Add AOS animations to sections
6. Write German content (de_AT)
"""

# Set parameters
PARAMETER temperature 0.2
PARAMETER top_p 0.9
PARAMETER num_ctx 4096

# Set template
TEMPLATE """
{{ if .System }}<|im_start|>system
{{ .System }}<|im_end|><|im_start|>user
{{ else }}<|im_start|>user
{{ end }}{{ .Prompt }}<|im_end|>
<|im_start|>assistant
{{ .Response }}
"""
EOF

# Create model
ollama create alubram-dev -f Modelfile

# Use custom model
ollama run alubram-dev
```

### 4.2 Configuration File

```json
// ~/.ollama/config.json
{
  "host": "0.0.0.0:11434",
  "origins": ["*"],
  "debug": false,
  "models": {
    "qwen2.5-coder:32b": {
      "num_ctx": 8192,
      "num_batch": 512,
      "num_gpu": 1
    }
  }
}
```

### 4.3 Environment Variables

```bash
# .env (do not commit)
OLLAMA_HOST=0.0.0.0:11434
OLLAMA_MODEL=qwen2.5-coder:32b
OLLAMA_NUM_CTX=4096
OLLAMA_TEMPERATURE=0.2
```

---

## 5. Użycie z VS Code

### 5.1 Continue.dev Extension

```json
// .continue/config.json
{
  "models": [
    {
      "title": "Ollama - Qwen 2.5 Coder",
      "provider": "ollama",
      "model": "qwen2.5-coder:32b",
      "apiBase": "http://localhost:11434"
    },
    {
      "title": "Ollama - Llama 3.1",
      "provider": "ollama",
      "model": "llama3.1:8b",
      "apiBase": "http://localhost:11434"
    }
  ],
  "tabAutocompleteModel": {
    "title": "Ollama - Qwen 2.5 Coder",
    "provider": "ollama",
    "model": "qwen2.5-coder:32b"
  }
}
```

### 5.2 CodeGPT Extension

```json
// VS Code Settings (settings.json)
{
  "codegpt.provider": "ollama",
  "codegpt.ollama.model": "qwen2.5-coder:32b",
  "codegpt.ollama.endpoint": "http://localhost:11434",
  "codegpt.ollama.maxTokens": 4096
}
```

### 5.3 Twinny Extension (Offline Copilot)

```json
// VS Code Settings
{
  "twinny.enabled": true,
  "twinny.provider": "ollama",
  "twinny.ollamaModel": "qwen2.5-coder:32b",
  "twinny.ollamaEndpoint": "http://localhost:11434",
  "twinny.contextLength": 4096
}
```

---

## 6. API Reference

### 6.1 Generate Endpoint

```bash
# Basic generation
curl http://localhost:11434/api/generate -d '{
  "model": "qwen2.5-coder:32b",
  "prompt": "Write a PHP function to sanitize email input",
  "stream": false
}'

# With options
curl http://localhost:11434/api/generate -d '{
  "model": "qwen2.5-coder:32b",
  "prompt": "Create WordPress contact form template",
  "stream": false,
  "options": {
    "temperature": 0.2,
    "top_p": 0.9,
    "num_ctx": 4096
  },
  "system": "You are a WordPress expert. Always use strict_types=1 and escape output."
}'
```

### 6.2 Chat Endpoint

```bash
# Chat completion
curl http://localhost:11434/api/chat -d '{
  "model": "qwen2.5-coder:32b",
  "messages": [
    {
      "role": "system",
      "content": "You are a WordPress developer."
    },
    {
      "role": "user",
      "content": "How do I register a custom post type?"
    }
  ],
  "stream": false
}'
```

### 6.3 Python Client

```python
# Install client
pip install ollama

# Basic usage
import ollama

response = ollama.chat(
    model='qwen2.5-coder:32b',
    messages=[{
        'role': 'user',
        'content': 'Write a PHP function for WordPress CPT registration'
    }]
)

print(response['message']['content'])

# Stream response
stream = ollama.chat(
    model='qwen2.5-coder:32b',
    messages=[{'role': 'user', 'content': 'Hello'}],
    stream=True
)

for chunk in stream:
    print(chunk['message']['content'], end='')
```

### 6.4 Node.js Client

```javascript
// Install client
npm install ollama

// Basic usage
import ollama from 'ollama';

const response = await ollama.chat({
  model: 'qwen2.5-coder:32b',
  messages: [{
    role: 'user',
    content: 'Write a TypeScript function to fetch products'
  }]
});

console.log(response.message.content);
```

---

## 7. Przykłady Użycia

### 7.1 Code Generation

```bash
# Generate PHP template
ollama run qwen2.5-coder:32b "
Generate a complete WordPress page template for contact page.
Requirements:
- German language (de_AT)
- AJAX contact form
- Google Maps integration
- AOS animations
- Brand colors from ALUBRAM GMBH
Include:
- Security checks
- Nonce verification
- Input sanitization
- Output escaping
"
```

### 7.2 Code Review

```bash
# Review code
ollama run qwen2.5-coder:32b "
Review this PHP code for security and WordPress best practices:

<?php
function handle_form_submission() {
    \$email = \$_POST['email'];
    echo \$email;
}

Identify issues and provide fixed code.
"
```

### 7.3 Debugging

```bash
# Debug error
ollama run qwen2.5-coder:32b "
I'm getting error: 'Cannot modify header information' in WordPress.
The error occurs when I try to redirect after form submission.

Here's my code:
[insert code]

What's causing this and how to fix it?
"
```

### 7.4 Documentation

```bash
# Generate documentation
ollama run qwen2.5-coder:32b "
Write PHPDoc documentation for this function:

function alubram_register_product_cpt() {
    register_post_type('alubram_product', [...]);
}

Include:
- Description
- @package
- @version
- @return
- Usage example
"
```

---

## 8. Troubleshooting

### 8.1 Common Issues

| Problem | Solution |
|---------|----------|
| **Model not found** | `ollama pull <model-name>` |
| **Out of memory** | Use smaller model (7B instead of 32B) |
| **Slow responses** | Reduce context size, use GPU |
| **Connection refused** | Check if Ollama is running: `ollama serve` |
| **CUDA error** | Update NVIDIA drivers, check GPU compatibility |
| **Context too long** | Reduce `num_ctx` parameter |

### 8.2 Performance Optimization

```bash
# Use GPU (NVIDIA)
OLLAMA_NUM_GPU=1 ollama run qwen2.5-coder:32b

# Limit context length
ollama run qwen2.5-coder:32b --num_ctx 2048

# Use quantized model (smaller, faster)
ollama pull qwen2.5-coder:32b-q4_K_M
ollama run qwen2.5-coder:32b-q4_K_M
```

### 8.3 Monitoring

```bash
# Check running models
ollama list

# Check server status
curl http://localhost:11434/api/tags

# View logs (Linux)
journalctl -u ollama -f

# View logs (macOS)
log show --predicate 'process == "ollama"' --last 1h
```

---

## 9. Integration Examples

### 9.1 Custom Script

```python
#!/usr/bin/env python3
"""
ALUBRAM AI Assistant using Ollama
"""

import ollama

SYSTEM_PROMPT = """
You are an AI assistant for the ALUBRAM GMBH WordPress project.
Always follow these rules:
1. Use German (de_AT) for content
2. Follow WordPress coding standards
3. Use brand colors from BRAND-SETTINGS.md
4. Include security best practices
"""

def generate_code(prompt: str) -> str:
    """Generate code using Ollama"""
    response = ollama.chat(
        model='qwen2.5-coder:32b',
        messages=[
            {'role': 'system', 'content': SYSTEM_PROMPT},
            {'role': 'user', 'content': prompt}
        ],
        options={
            'temperature': 0.2,
            'num_ctx': 4096
        }
    )
    return response['message']['content']

if __name__ == '__main__':
    prompt = "Create WordPress contact form AJAX handler"
    code = generate_code(prompt)
    print(code)
```

### 9.2 VS Code Snippet

```json
// .vscode/snippets.json
{
  "Ollama Generate": {
    "prefix": "ollama-gen",
    "body": [
      "// Generated by Ollama AI",
      "${1:code}"
    ],
    "description": "Insert Ollama generated code"
  }
}
```

---

*OLLAMA.md — ALUBRAM GMBH WordPress Project | v1.0.0 | 2026-02-26*
