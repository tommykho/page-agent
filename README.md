```
██████╗  █████╗  ██████╗ ███████╗    █████╗  ██████╗ ███████╗ ███╗   ██╗ ████████╗
██╔══██╗ ██╔══██╗ ██╔════╝ ██╔════╝    ██╔══██╗ ██╔════╝ ██╔════╝ ████╗  ██║ ╚══██╔══╝
██████╔╝ ███████║ ██║  ███╗ █████╗      ███████║ ██║  ███╗ █████╗   ██╔██╗ ██║    ██║
██╔═══╝  ██╔══██║ ██║   ██║ ██╔══╝      ██╔══██║ ██║   ██║ ██╔══╝   ██║╚██╗██║    ██║
██║      ██║  ██║ ╚██████╔╝ ███████╗    ██║  ██║ ╚██████╔╝ ███████╗ ██║ ╚████║    ██║
╚═╝      ╚═╝  ╚═╝  ╚═════╝ ╚══════╝    ╚═╝  ╚═╝  ╚═════╝ ╚══════╝ ╚═╝  ╚═══╝    ╚═╝
GUI Agent Playground for the Web
```

![License](https://img.shields.io/badge/license-MIT-green) ![HTML](https://img.shields.io/badge/html-single--file-orange?logo=html5) ![NIM](https://img.shields.io/badge/NVIDIA-NIM-76b900?logo=nvidia) ![Stars](https://img.shields.io/github/stars/tommykho/page-agent?style=social)

---

A single-file HTML demo that turns any LLM into a web UI agent — no backend, no extensions, no build step. Open the file in a browser, paste your API key, and control the page with natural language.

Built on [alibaba/page-agent](https://github.com/alibaba/page-agent).

---

## How it works

[page-agent](https://github.com/alibaba/page-agent) reads the live DOM of a webpage and uses an LLM to reason about what clicks, form fills, and interactions are needed to complete a task you describe in plain English. Everything runs in-page — no screenshots, no Python, no browser extension required.

This playground wraps that library in a clean UI so you can try it immediately against a set of demo controls, or drop the script into any page you want to automate.

---

## Quick start

1. Clone or download this repo
2. Open `index.html` in any modern browser (double-click works)
3. Fill in your credentials in the **LLM Configuration** panel
4. Type a task and hit **Run task**

No `npm install`, no server, no build.

---

## Configuration

| Field | Default | Notes |
|---|---|---|
| Base URL | `https://integrate.api.nvidia.com/v1` | Any OpenAI-compatible endpoint |
| API Key | — | Your `nvapi-…` key from [build.nvidia.com](https://build.nvidia.com) |
| Model | `meta/llama-3.3-70b-instruct` | Any NIM-hosted or compatible model |
| Language | `en-US` | Used by the agent for DOM reasoning |

Credentials are saved to `localStorage` and pre-filled on reload.

### Other providers

Swap the Base URL and model to use any OpenAI-compatible API:

| Provider | Base URL | Example model |
|---|---|---|
| NVIDIA NIM | `https://integrate.api.nvidia.com/v1` | `meta/llama-3.3-70b-instruct` |
| OpenAI | `https://api.openai.com/v1` | `gpt-4o-mini` |
| Alibaba DashScope | `https://dashscope.aliyuncs.com/compatible-mode/v1` | `qwen-plus` |
| Local (Ollama) | `http://localhost:11434/v1` | `llama3.2` |

---

## Sample tasks

These are pre-loaded as chips in the UI:

- *Fill in the sample form with realistic data*
- *Click the first action button*
- *Increment the counter to 5*
- *Fill name "Alice" and message "Hello world"*
- *Set the counter to 0*

---

## Files

```
index.html            — the entire app (HTML + CSS + JS, ~1000 lines)
page-agent.bundle.js  — local copy of the page-agent IIFE build (CDN fallback)
```

The page loads the library from jsDelivr CDN first. If that fails (offline, network restriction, CSP), it silently falls back to `page-agent.bundle.js`.

---

## Credits

- [alibaba/page-agent](https://github.com/alibaba/page-agent) — MIT License
- Defaults to [NVIDIA NIM](https://build.nvidia.com) for inference

---

## Support

If you find this useful, consider buying me a coffee!

[![Donate via PayPal](https://img.shields.io/badge/Donate-PayPal-blue?logo=paypal)](https://paypal.me/tommykho)
