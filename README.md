# PenWeb

**Highlight, draw and annotate on any web page.**

PenWeb is a free Chrome extension (Manifest V3) that turns any page — video lectures, in-browser PDFs, handouts, articles — into a study whiteboard. Everything is processed and stored **locally in your browser**: no personal data is collected or transmitted.

🔗 [Chrome Web Store — coming soon](https://chromewebstore.google.com/detail/penweb/mmbhcihaimenkcagobpnkopbhdcgpopd) ·
🌐 [Website](https://thallyz.github.io/penweb/en/) ·
🇧🇷 [Site em português](https://thallyz.github.io/penweb/)

![PenWeb](img/poster.png)

---

## What's new in v1.6

### 〰️ Real-time stroke smoothing
Toggle smoothing on the main toolbar and get a clean, steady line while you draw — no more jittery strokes on touchpads or touchscreens.

### 🧮 Readable math & code
AI responses now render real fractions, code blocks and equations. Every response has a one-click copy button.

### 📸 Region capture + AI vision
Select an area of the page (or paste a screenshot with Ctrl+V) and ask the AI to analyse only that region. Powered by Groq's vision models.

---

## Features

- **Pressure-sensitive pen** — adjustable thickness, colour and opacity with smoothed strokes.
- **Highlighter** — mark passages without changing the original page DOM.
- **Real screen capture** — export your annotations together with the visible page content as PNG.
- **Smart autosave** — reload the page by accident? PenWeb offers to restore your drawing.
- **Trilingual interface** — English, Portuguese and Spanish, auto-detected from your browser language.
- **Accessible** — high-contrast mode, adjustable UI scale and `prefers-reduced-motion` support.

## Privacy first

PenWeb **collects no personal data**. Your drawings are saved only in your browser's local storage. Nothing is sent to any server. [Read the full policy](https://thallyz.github.io/penweb/en/privacy.html).

## Roadmap

- [x] Chrome (Manifest V3) — launching soon on Chrome Web Store
- [ ] Edge Add-ons
- [ ] Firefox
- [ ] Safari
- [ ] PenWeb AI — explain highlights, generate mind maps and flashcards (premium line)

## About this repository

This repo contains the **official website** (static HTML + CSS, hosted on GitHub Pages) and the **remote configuration** (`ofertas.json`) consumed by the extension.

```
penweb/
├── index.html          # landing page (pt-BR)
├── privacidade.html    # privacy policy (pt-BR)
├── ofertas.json        # remote offer-panel config for the extension
├── en/
│   ├── index.html      # landing page (en)
│   └── privacy.html    # privacy policy (en)
├── css/
│   └── style.css       # stylesheet (CSS custom properties at the top)
└── img/                # poster and banner (Open Graph)
```

The PT-BR and EN pages are independent, linked by `hreflang` (`pt-BR`, `en`, `x-default`) for correct indexing. The extension UI uses its own dictionary (`pt` / `en` / `es`) resolved at runtime from the browser language.

### Remote config (`ofertas.json`)

The offer panel inside the extension is fed by this file. The content script flow:

1. Read cache from `localStorage` (key `penweb_ofertas_cache`, 6-hour TTL).
2. If cache is missing or expired, `fetch` from GitHub raw.
3. Validate payload (`emoji`, `texto`, `cta`, `link` with http/https URL).
4. On network failure or invalid payload, fall back to the embedded list.

This lets us update the panel **without publishing a new extension version**.

## Contributing

Issues and pull requests are welcome — typo fixes, translations, accessibility and site improvements are the most useful entry points today. For extension bugs, please include browser, version and steps to reproduce.

## Contact

youthman95@gmail.com

---

<details>
<summary><strong>Português</strong></summary>

**Grife, desenhe e anote em qualquer página da web.** PenWeb é uma extensão para Chrome (Manifest V3) que transforma qualquer página — videoaulas, PDFs no navegador, apostilas, artigos — em um quadro de estudos. Tudo é processado e armazenado **localmente no seu navegador**; nenhum dado pessoal é coletado.

Este repositório contém o **site oficial** (página estática, HTML + CSS puros, hospedada no GitHub Pages) e a **configuração remota** (`ofertas.json`) consumida pela extensão.

Instalação: [Chrome Web Store — em breve](https://chromewebstore.google.com/detail/penweb/mmbhcihaimenkcagobpnkopbhdcgpopd) ·
Privacidade: [política](https://thallyz.github.io/penweb/privacidade.html)

</details>
