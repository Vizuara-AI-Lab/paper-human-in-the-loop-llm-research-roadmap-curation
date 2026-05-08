# A Human-in-the-Loop LLM Workflow for Research Roadmap Curation

A human-in-the-loop LLM workflow for converting raw research ideas into executable research roadmaps. The workflow generates a structured, schema-constrained roadmap, exposes it for human review, and routes revisions through a typed `revision_requested` state.

## Paper

- **PDF**: [tex/main.pdf](tex/main.pdf)
- **Source**: [tex/main.tex](tex/main.tex), compiled with `tectonic -X compile tex/main.tex`
- **Peer review**: [review.md](review.md) (sealed-PDF reviewer pass)

## Primary result

In a blind preference study with 40 evaluators rating four anonymized roadmap variants for one shared research idea, **34 of 40 evaluators (85%)** selected the workflow's roadmap (Variant C) as the one they would adopt overall. The remaining 6 votes (15%) were distributed across three unstructured ChatGPT baselines (variants A, B, D).

## Figures

| Figure id | Description |
| --- | --- |
| fig-workflow | Human-in-the-loop roadmap-curation workflow |
| fig-schema | Roadmap schema components |
| fig-job-states | Asynchronous job state machine |
| fig-study-design | Human preference study design |
| fig-overall-preference | Overall roadmap preference across 40 evaluators |

## Recommended venues

- **ICML 2026 Workshops** (matches workflow + LLM + structured-generation framing)
- **CHI 2026 LBW** (matches HCI / human-AI interaction framing)
- **EMNLP 2026 BEA Workshop** (matches educational-application angle of the workflow)
- **TMLR** (good for v1-strength empirical / system papers)
- **IJHCS** (matches mixed-initiative / human-AI study framing)

## Authors

Prathamesh Joshi, Abraar, Naman Dwivedi, Dr Raj Dandekar, Dr Rajat Dandekar, Dr Sreedath Dandekar

## Provenance

Session id: `20260508-060207-e9e1`. See [log.md](log.md) and [state.json](state.json) for the full audit trail.
