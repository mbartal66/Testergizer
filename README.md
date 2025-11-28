<p align="center">
  <img src="https://raw.githubusercontent.com/rundom-tech/Testergizer/main/assets/logo.png" height="110" alt="Testergizer Logo">
</p>

<h1 align="center">Testergizer</h1>

<p align="center">
  <strong>AI-ready, data-driven UI automation framework built on Playwright.</strong><br/>
  Unified locator dictionary • Chrome flow recorder • JSON-based scripts • Sandbox mode<br/>
  Extensible RLIS engine for intelligent locator drift modeling.<br/>
  <em>Open-core by RunDOM Technologies.</em>
</p>

---

## 🌟 What is Testergizer?

**Testergizer** is a hyper-modern, open-core, data-driven UI automation framework designed for stability, consistency, and development speed.

Instead of flaky scripts scattered across codebases, Testergizer introduces:

- A **unified locator dictionary**
- A **Chrome recorder** that generates JSON scripts
- A **Playwright-powered engine** that runs them
- A **sandbox mode** for testing UI flows before real DOM exists
- The **RLIS engine (RunDOM Locator Intelligence System)** for drift modeling & smart locator analysis

This open-core repo includes everything needed to record, build, and execute robust UI automation.

Advanced AI-powered locator healing, cloud dashboards, and enterprise integrations are developed separately in **Testergizer-Pro** and **Testergizer-Cloud**.

---

## ⚡ Features

### 🧩 JSON-Based Test Scripts
Define UI flows using pure JSON:
- `rd.navigate`
- `rd.click`
- `rd.fill`
- `rd.expectVisible`
- Dataset-driven variables

Readable, deterministic, version-friendly, and IDE-independent.

---

### 🔍 Unified Locator Dictionary
Testergizer maps logical element names → selectors:

```
locators/
  real-locators.json
  sandbox-locators.json
```

Benefits:
- Eliminate selector duplication  
- Update DOM changes in one place  
- Multi-environment support  
- Cross-app consistency  

---

### 🎥 Chrome Flow Recorder
Record real UI flows with the included Chrome Extension:
- Clicks  
- Inputs  
- Visibility checks  
- Navigations  

Events are sent to the Testergizer Recorder Server.  
The server normalizes them and produces JSON test scripts.

---

### 🏜 Sandbox Mode
Run tests **before real UI exists**, using alternate locator sets.

Perfect for:
- Shift-left QA  
- Mock environments  
- Pre-integration testing  

---

### 🧠 RLIS Engine (Open-Core)
RLIS provides:
- Locator drift modeling  
- Selector candidate scoring models (structure only)  
- Healer hooks (runtime-pluggable)  

Open-core includes:
- Types
- Hooks
- Drift examples  

Pro edition adds:
- ML scoring  
- Automatic self-healing  
- DOM graph analysis  

---

### ⚙ Built on Playwright
Reliable, fast, cross-browser execution.

---

### 🧱 Clean Monorepo Architecture
```
Testergizer/
  packages/
    engine/          → test runner (Playwright)
    cli/             → testergizer command-line tool
    locator-intel/   → RLIS base types + extension hooks
    recorder-server/ → recording endpoint → JSON
    extension/       → Chrome recorder extension
  locators/          → real + sandbox dictionaries
  scripts/           → user-generated JSON scripts
  examples/          → SauceDemo examples
```

---

## 🚀 Quickstart

### 1. Install deps
```bash
npm install
```

### 2. Build the monorepo
```bash
npm run build
```

### 3. Start the recorder server
```bash
npx testergizer record-server
```

### 4. Load Chrome extension
- Go to `chrome://extensions`
- Enable **Developer Mode**
- Load unpacked → `packages/extension/`

### 5. Record a flow
JSON will be generated under `scripts/ui-scripts/`.

### 6. Run a real test
```bash
npx testergizer run examples/saucedemo/basic-login/script.json real
```

### 7. Run in sandbox mode
```bash
TESTERGIZER_MODE=sandbox npx testergizer run examples/saucedemo/basic-login/script.json
```

---

## 🧪 Examples

Included example: **SauceDemo login flow** (https://www.saucedemo.com)

---

## 🛠 Architecture Overview

Testergizer follows an **open-core model**:
- **Public repo** → Engine, Recorder, CLI, RLIS hooks.
- **Private repo** → Testergizer-Pro (AI healing, ML selectors).
- **Cloud repo** → Testergizer-Cloud (SaaS dashboards).

---

## 🗺 Roadmap

- RLIS Pro (AI healing)
- Auto sandbox → real locator mapping
- Dashboard & analytics
- Cloud execution grid
- Mocking Studio
- CI templates
- Plugin ecosystem

---

## 🤝 Contributing

Contributions welcome!  
See `CONTRIBUTING.md`.

---

## 📜 License

Apache 2.0 License for open-core.  
Enterprise modules are proprietary.

© 2025 RunDOM Technologies.
