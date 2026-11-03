# V1 Architecture Decisions and Traceability — AI Trending Video Analyzer

**Version:** 1.0  
**Scope:** Single uploaded video, up to 60 seconds; no virality prediction or live trend monitoring.

## C1 — Simplest architecture

User → Application Interface → AI Video Analysis → Marketing Insights Dashboard.

This simple architecture is insufficient for timestamped evidence, reference-grounded recommendations, video validation, privacy controls, and objective evaluation. The V1 architecture adds only components needed for those requirements.

## C2 — Architecture needs

| Requirement ID | What does the requirement need? | Architecture response |
|---|---|---|
| FR1 | Accept a single supported video of up to 60 seconds | Upload validation |
| O1 / FR2 | Analyze audio and visual content | Video preprocessing and multimodal analysis |
| FR3 / RAI1 | Provide timestamps and evidence | Evidence tracking and output validation |
| FR4 | Ground insights in marketing guidance | Marketing knowledge source and insight generation |
| FR5 / RAI2 | Show clear results and uncertainty | Structured output validation and dashboard |
| RAI3 | Protect uploads and limit retention | Privacy and temporary-file management |
| O3 / NFR1 / NFR4 | Track processing speed and cost | Evaluation and usage logging |
| O3 / NFR2 | Measure detection accuracy | Human-annotated evaluation videos |

## C3 — V1 conceptual architecture

See `docs/week2_architecture_v1.png`. The main flow is: User → Interface → Upload Validation → Video Preprocessing → Multimodal Analysis → Insight Generation → Output Validation → Dashboard. Public marketing guidelines support the analysis and insight generation. Privacy controls manage temporary uploaded content. An offline evaluation dataset and usage logs support measurement.

## C4 — Architecture Decision Record (ADR)

| Decision | Requirement / Constraint | Alternatives Considered | Selected Option | Trade-off Accepted |
|---|---|---|---|---|
| Separate audio and visual preprocessing | O1 / FR2: analyze both spoken and visible content | Send raw video directly to a model; analyze transcript only; extract audio and frames separately | Video preprocessing feeding multimodal analysis | More processing and integration complexity, but better access to timestamped multimodal evidence |
| Include public marketing guideline access | FR4: insights informed by reference guidelines | Model knowledge alone; hard-coded checklist; knowledge-source component | Small marketing knowledge source supporting insight generation | Additional document handling and possible retrieval errors, but clearer basis for recommendations |
| Validate evidence and uncertainty before displaying findings | FR3 / FR5 / RAI1 / RAI2 | Display free-form model output; validate structured results | Output validation with timestamp/evidence checks and uncertain/undetected labels | Extra checks and possible rejection of useful but weakly supported insights, in exchange for better transparency |
| Keep uploads temporary | RAI3: limit video retention | Persistent upload library; temporary storage | Temporary-file management with deletion after processing and a 24-hour maximum retention window | No built-in historical reanalysis without reupload, but lower storage and privacy risk |

## Initial Requirements Traceability Matrix

| Objective | Requirement | Evaluation Criterion | Architecture Element | Later Evidence |
|---|---|---|---|---|
| O1 | FR1 / FR2 | Successful processing of supported video inputs | Upload validation; video preprocessing; multimodal analysis | Upload test cases and sample analysis records |
| O2 | FR3 / RAI1 | Evidence grounding: 100% presence and ≥90% correctness | Evidence tracking; output validation | Human-reviewed timestamp and evidence checklist |
| O2 | FR4 | Marketing insight quality: average rubric score ≥4.0/5 | Marketing guidelines; insight generation | Scored human review rubric |
| O3 | NFR2 | Hook and CTA detection: macro-F1 ≥0.75 each | Multimodal analysis; annotated evaluation videos | Classification reports on 20–30 annotated videos |
| O3 | NFR1 / NFR4 | p90 latency ≤120 seconds; average model/API cost ≤US$0.10/video | Evaluation and usage logging | Timed runs and API usage/cost logs |
| O2 | FR5 / RAI2 | ≥90% subjective interpretations appropriately qualified | Output validation; dashboard | Interpretation-transparency review |
| O2 | RAI3 | 100% temporary files deleted within 24 hours | Privacy and temporary-file management | Retention/deletion test logs |

## Final Architecture Review

- Each component has a requirement or evaluation justification.
- The marketing knowledge source contains the approved public guideline documents.
- The design includes evidence checks, uncertainty handling, privacy controls, and offline evaluation.
- It intentionally omits trend prediction, social-media scraping, vector databases, model-specific dependencies, and production-scale deployment.
- Model/framework selection is deferred to later project phases.

## Reflection

**Which architecture decision involved the most important trade-off? Which requirement drove it, and what trade-off did you accept?**

The most important decision was to separate video preprocessing from multimodal AI analysis. FR2 and Objective O1 require the system to interpret both audio and visual content, while FR3 and RAI1 require timestamped evidence for its findings. Sending a whole video directly to a single model would simplify the architecture, but it could make evidence tracking and evaluation less controllable. We accepted additional processing and integration complexity in exchange for more traceable, testable analysis.
