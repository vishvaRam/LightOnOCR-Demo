# LightOnOCR Inference Client & Viewer

A minimal inference client, CLI, and interactive web viewer for **LightOnOCR** (LightOnOCR 1, 2, and 3) served via **vLLM**.

This tool provides side-by-side document layout inspection, bounding-box grounding overlays, and clean Markdown transcription rendering.

---

## Features

- **Interactive Viewer**: Synchronized, side-by-side document inspector with layout block highlighting and filtering.
- **LightOnOCR-3 Grounding Support**: Bounding box coordinate parsing (`[x1, y1, x2, y2]`) on a 0–1000 normalized grid.
- **CLI & Web Interface**: Run batch inference directly from the terminal or through the web dashboard.
- **Markdown & LaTeX Rendering**: Powered by `marked.js` and `KaTeX` for mathematical formula and table formatting.
- **vLLM Integration**: Works with standard OpenAI-compatible vLLM endpoints.

---

## Requirements

* Python >= 3.10
* An active vLLM instance serving a LightOnOCR model

Key Python dependencies:

* `openai >= 1.40`
* `pillow >= 10`
* `pypdfium2 >= 4`

---

## Installation

Install using `uv` (recommended) or standard `pip`:

```bash
git clone https://github.com/vishvaRam/LightOnOCR-Demo.git
cd LightOnOCR

# Install dependencies using uv
uv sync
```

---

## Usage

### 1. Configure Model Endpoint

Set the environment variables pointing to your vLLM model server:

```bash
export LIGHTONOCR_BASE_URL="http://69.8.146.173:11337/v1"
export LIGHTONOCR_MODEL="Vishva007/LightOnOCR-3-4B-W4A16-AutoRound"
```

*(On Windows PowerShell, use `$env:LIGHTONOCR_BASE_URL="..."`)*

### 2. Launch the Web Viewer

Start the local dashboard server:

```bash
lightonocr viewer --host 0.0.0.0 --port 8000
```

Open `http://localhost:8000` (or your host IP) in your browser to run OCR jobs and inspect grounded layouts.

---
