# Safaricom Decode · AI Workshop Materials

Teaching materials for the Safaricom Decode AI track: a chalk talk on designing production AI systems and a hands-on lab on building agents. Each folder is self-contained and has its own README.

| Module | Format | What it covers |
|---|---|---|
| [`design-ai-systems-end-to-end/`](design-ai-systems-end-to-end/) | Interactive HTML deck, 2 hours | From `y = mx + c` to a four-layer architecture (Data → Model → API → Frontend), design patterns (RAG, cascade, fallback, human-in-the-loop) and the rules for AI that takes real actions. Participants vote, argue and draw an architecture on paper. |
| [`builder-labs/`](builder-labs/) | Jupyter notebook lab | Anatomy of an agent: model, instructions, context, tools, state and memory, guardrails, evaluation, observability. Ends with a working `MiniAgent` chatbot. Comes with a `_SOLVED` version for facilitators. |

## Quick start

**Chalk talk.** Open `design-ai-systems-end-to-end/deck.html` in a browser. Press `F` for fullscreen and `N` for presenter notes. The [module README](design-ai-systems-end-to-end/README.md) has the run-sheet, keyboard controls, external demo links and prize plan.

**Builder lab.** Open `builder-labs/agent_anatomy_lab.ipynb` in Jupyter or Google Colab and work through the numbered TODOs. Facilitators use `agent_anatomy_lab_SOLVED.ipynb`.

## Suggested order

1. Chalk talk first. It gives the vocabulary (layers, patterns, guardrails) the lab assumes.
2. Builder lab second. It turns the "Model" and "API" layers from the talk into running code.

## Repository layout

```
.
├── README.md
├── design-ai-systems-end-to-end/
│   ├── README.md      # facilitator guide and run-sheet
│   └── deck.html      # the whole interactive deck, single file
└── builder-labs/
    ├── agent_anatomy_lab.ipynb
    └── agent_anatomy_lab_SOLVED.ipynb
```
