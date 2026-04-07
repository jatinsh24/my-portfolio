# Data Analyst → AI/LLM Engineer Transition Project

An interactive, AI-powered career transition tool built for data analysts who want to break into AI/LLM engineering. The app includes a personalised roadmap, skill gap analyser, hands-on project tracker, curated resources, and a live AI mentor powered by Claude.

---

## Features

- **Dashboard** — Progress overview with radar chart (current vs target skills), transferable skill highlights, and monthly progress chart
- **Roadmap** — 4-phase interactive stepper (Foundation → Core LLM → Engineering → Production) with actionable steps tied to your existing DA knowledge
- **Skill gap analyser** — Visual bar chart of 12 LLM engineering skills with a priority matrix (start now / month 2–4 / month 5–8)
- **Project tracker** — 5 portfolio-ready hands-on projects ordered by difficulty, with check-off functionality
- **Resources** — Curated list of free and paid courses, docs, and books for the transition path
- **AI mentor** — Live Claude-powered career advisor that knows your DA background and gives role-specific guidance

---

## Tech stack

| Layer | Technology |
|---|---|
| Frontend | Vanilla HTML, CSS, JavaScript |
| Charts | Chart.js 4.4.1 (via CDN) |
| AI backend | Anthropic Claude API (`claude-sonnet-4-20250514`) |
| Hosting | Any static file server |

---

## Getting started

### Prerequisites

- A modern browser (Chrome, Firefox, Safari, Edge)
- An [Anthropic API key](https://console.anthropic.com/) for the AI mentor feature

### Running locally

1. Clone or download the project files:

```bash
git clone https://github.com/your-username/da-to-ai-transition.git
cd da-to-ai-transition
```

2. Open `index.html` directly in your browser, or serve with a local server:

```bash
# Python
python -m http.server 8080

# Node.js
npx serve .
```

3. Visit `http://localhost:8080`

### API key setup

The AI mentor tab calls the Anthropic API. To enable it, add your API key to the fetch request in `index.html` (or move it to a backend proxy for production use):

```javascript
headers: {
  "Content-Type": "application/json",
  "x-api-key": "YOUR_API_KEY_HERE",   // add this line
  "anthropic-version": "2023-06-01"
}
```

> **Note:** Never expose API keys in client-side code in production. Use a backend proxy or serverless function to keep your key secure.

---

## Project structure

```
da-to-ai-transition/
├── index.html          # Main app (single-file, self-contained)
├── README.md           # This file
└── assets/             # Optional: icons, screenshots
```

The entire application is a single HTML file — no build tools, no package manager, no framework required.

---

## The 5 portfolio projects inside the app

| # | Project | Level | Key skills |
|---|---|---|---|
| 1 | SQL → LLM query assistant | Beginner | Prompt engineering, OpenAI function calling |
| 2 | RAG analytics chatbot | Intermediate | RAG, LangChain, vector databases |
| 3 | LLM-powered dashboard insights | Intermediate | Multimodal, GPT-4 Vision, Streamlit |
| 4 | Fine-tune a classifier on your data | Advanced | LoRA, Hugging Face, dataset prep |
| 5 | Autonomous data analysis agent | Advanced | LangChain agents, tool use, SQL |

---

## The 4-phase roadmap

### Phase 1 — Foundation (weeks 1–6)
Python strengthening, LLM fundamentals, first API calls, prompt engineering basics.

### Phase 2 — Core LLM skills (months 2–3)
Embeddings, vector search, RAG pipelines, LangChain/LlamaIndex, LLM evaluation.

### Phase 3 — Engineering depth (months 4–5)
Fine-tuning with LoRA, agents and tool use, data pipelines for LLM training.

### Phase 4 — Production (months 6–8)
MLOps for LLMs, cost and latency optimisation, deploying with FastAPI and cloud services.

---

## Skill gap tracked

The app tracks proficiency across 12 skills:

**Already strong (DA background):** SQL & data prep, statistical analysis, data visualisation, Python (intermediate)

**To acquire:** Prompt engineering, LLM API integration, vector databases, RAG pipelines, LangChain/LlamaIndex, embeddings, LLM evaluation, fine-tuning (LoRA)

---

## Customisation

To personalise the app for your own skill level, edit the `skills` array in the `<script>` block:

```javascript
const skills = [
  { name: 'Prompt engineering', pct: 15, color: '#E24B4A' },
  { name: 'SQL & data prep',    pct: 90, color: '#639922' },
  // ... update pct values to match your actual level (0–100)
];
```

To change the AI mentor system prompt, find and edit:

```javascript
system: `You are a senior AI/LLM engineer and career mentor helping a data analyst...`
```

---

## Resources included

- fast.ai — Practical Deep Learning (free)
- LangChain docs & tutorials (free)
- Hugging Face NLP course (free)
- DeepLearning.AI LLM specialisation (paid)
- OpenAI Cookbook (free)
- Anthropic prompt engineering guide (free)
- LlamaIndex docs (free)
- *Building LLM Apps* — Chip Huyen (paid)
- Weights & Biases LLMOps course (free)

---

## Contributing

Pull requests welcome. Ideas for contribution:

- Add more projects to the tracker
- Build a backend proxy for the API key
- Add a progress persistence layer (localStorage or Supabase)
- Add more role paths (ML engineer, AI product manager, etc.)

---

## License

MIT — free to use, modify, and distribute.

---

## Acknowledgements

Built with the [Anthropic Claude API](https://www.anthropic.com) and [Chart.js](https://www.chartjs.org/).
