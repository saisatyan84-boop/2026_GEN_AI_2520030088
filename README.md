# 2026_GEN_AI_2520030088
# LLM Quality Monitoring for Silent Regression Detection

> A monitoring system that continuously evaluates Large Language Model (LLM) responses and automatically detects hidden quality drops after model, prompt, or configuration changes.

**Domain:** AI / Machine Learning
**Institution:** KL Deemed to be University (KLH), Freshman Engineering Department
**Status:** Review-1 (project proposal stage)

---

## Abstract

Large Language Models (LLMs) are now widely used in chatbots, virtual assistants, educational tools, and automated decision-support systems. However, an LLM-based application can degrade in quality after a model update, prompt change, or configuration change without raising any error or crash. This is known as **silent regression**. The system keeps running normally while its answers become less accurate, less relevant, more repetitive, slower, or more prone to hallucination. Because nothing visibly fails, such degradation often goes unnoticed until users are affected.

This project proposes a monitoring system that continuously evaluates LLM responses and automatically detects these hidden quality drops. A fixed set of test prompts is sent to the LLM at regular intervals, and each response is scored on several parameters: accuracy, relevance, consistency, latency, and hallucination level. Scoring uses embedding-based similarity, rule-based checks, and an LLM-as-a-judge approach. The current scores are compared against previously recorded baseline results, and statistical testing is used to decide whether a change is a real degradation or just normal variation in model output. When a significant drop is detected, the system raises an alert and helps identify which prompt, model version, or configuration change is the likely cause. Results and historical trends are shown on an interactive dashboard.

The prototype will be built in Python using the Gemini or Groq API, a FastAPI or Flask backend, SQLite for storing results, and Streamlit with Plotly for visualization. The aim of the project is to improve the reliability, consistency, and trustworthiness of AI-powered applications through automated quality monitoring and early regression detection.

**Keywords:** Large Language Models, Silent Regression, Quality Monitoring, LLM-as-a-Judge, Baseline Comparison, Statistical Degradation Detection

---

## Problem Statement

When an LLM application changes (new model version, edited prompt, tweaked temperature or settings), its output quality can quietly drop. There are no exceptions and no failed requests, so traditional monitoring does not catch it. Teams usually find out only after users complain.

## Objectives

- Run a fixed suite of test prompts against an LLM at regular intervals.
- Score every response on accuracy, relevance, consistency, latency, and hallucination.
- Compare current scores with a stored baseline.
- Use statistical testing to separate real degradation from normal output variation.
- Raise alerts and point to the likely cause (prompt, model, or configuration change).
- Present historical trends on an interactive dashboard.

## How It Works

```
Test Prompts ──► LLM (Gemini / Groq) ──► Responses
                                            │
                                            ▼
              Scoring: embedding similarity + rule-based checks + LLM-as-a-judge
                                            │
                                            ▼
                   Baseline vs. current comparison + statistical test
                                            │
                          ┌─────────────────┴─────────────────┐
                          ▼                                   ▼
                 Alert + cause attribution            SQLite history ──► Dashboard
```

## Quality Parameters

| Parameter | What it measures |
|---|---|
| Accuracy | Correctness of the answer against reference or expected output |
| Relevance | How well the answer addresses the prompt |
| Consistency | Stability of answers across repeated runs |
| Latency | Response time |
| Hallucination | Presence of unsupported or fabricated content |

## Tech Stack

- **Language:** Python
- **LLM API:** Gemini or Groq
- **Backend:** FastAPI / Flask
- **Database:** SQLite
- **Dashboard:** Streamlit + Plotly

## Planned Features

- [ ] Test prompt suite and baseline recording
- [ ] Multi-parameter scoring pipeline
- [ ] Statistical degradation detection
- [ ] Alerting and change-cause attribution
- [ ] Historical results dashboard

## Team

| Name | Roll No. | Role |
|---|---|---|
| Satyan | _Roll No._ | _Role_ |
| SHAMRUTH | 2520030191 | _Role_ |
| _Member name_ | _Roll No._ | _Role_ |

**Department:** Freshman Engineering Department (FED), KL Deemed to be University (KLH)

## Project Structure (planned)

```
.
├── backend/        # API and evaluation pipeline
├── scoring/        # embedding, rule-based, and LLM-judge scorers
├── dashboard/      # Streamlit app
├── data/           # test prompts and baselines
└── README.md
```

## Getting Started

```bash
git clone <repo-url>
cd <repo-folder>
pip install -r requirements.txt
```

Setup and run instructions will be added as the prototype develops.

## References

- *(Why) Is My Prompt Getting Worse?* (2024)
- *When LLMs Get Significantly Worse* (ICLR 2026)
- *PromptPex* (2025)
- *LLM-as-a-Judge* survey (2024)

## License

To be decided.
