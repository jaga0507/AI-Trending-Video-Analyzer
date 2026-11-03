# Evaluation Criteria — AI Trending Video Analyzer

**Version:** 1.0  
**Project:** AI Trending Video Analyzer — A Multimodal AI System for Short-Form Video Marketing Analysis

## Part B — Evaluation Criteria

| Objective / Requirement ID | Evaluation Criterion | Capability Bucket | Measurement Method | Metric | Threshold | User / Business Outcome |
|---|---|---|---|---|---|---|
| O3 / NFR2 | Marketing Element Detection Accuracy | Domain-specific capability | Compare AI-generated hook and CTA labels against 20–30 manually annotated videos. | Macro-averaged F1-score for hook classification and CTA detection, measured separately. | ≥ 0.75 for each task | Users receive sufficiently accurate identification of important video marketing elements. |
| O2 / FR3 / RAI1 | Evidence Grounding | Instruction-following capability | Review detected marketing elements and verify that timestamps and transcript or visual evidence support each finding. | Evidence presence rate; evidence correctness rate. | 100% presence; ≥ 90% correctness | Users can verify AI-generated insights against actual video content. |
| O2 / FR4 | Marketing Insight Quality | Generation capability | Evaluate AI-generated marketing insights and improvement suggestions using a human assessment rubric covering relevance, clarity, and actionability. | Average rubric score on a 1–5 scale. | ≥ 4.0/5 | Users receive understandable and actionable suggestions for improving video content. |
| O3 / NFR1 | Video Processing Latency | Cost and latency | Measure processing time for 20 short-form videos of up to 60 seconds, excluding upload transfer time. | 90th-percentile processing latency (seconds). | ≤ 120 seconds | Users receive video analysis results within a reasonable waiting period. |
| O3 / NFR4 | AI Processing Cost | Cost and latency | Record AI model/API usage and calculate average processing cost across the evaluation dataset. | Average model/API cost per video (USD). | ≤ US$0.10 per video | Small businesses and content creators can access affordable video analysis. |
| O2 / FR5 / RAI2 | Interpretation Transparency | Instruction-following capability | Review emotional appeal classifications and check whether subjective interpretations are appropriately qualified and uncertain findings are clearly indicated. | Percentage of subjective interpretations appropriately qualified. | ≥ 90% | Users are less likely to mistake subjective AI interpretations for confirmed facts. |

## Reflection

**Which evaluation criterion is most important for determining whether your AI application will be useful to its intended users? Why?**

Marketing Element Detection Accuracy is the most important evaluation criterion because the main purpose of the AI Trending Video Analyzer is to identify marketing techniques within short-form videos. If the system incorrectly identifies hooks, messages, or calls to action, the generated insights and recommendations may be misleading. Therefore, evaluating the AI's predictions against manually annotated videos is essential to determine whether the system provides reliable and useful analysis for marketers, small businesses, and content creators.