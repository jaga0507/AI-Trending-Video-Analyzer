## Problem Statement

Small businesses, marketers, and content creators find it difficult to systematically analyze marketing techniques in short-form videos. Identifying hooks, messaging, emotions, video structure, and CTAs manually can be time-consuming and subjective.

This project aims to develop a multimodal AI system that analyzes uploaded short-form videos using speech recognition, visual analysis, and LLMs.

## Evidence of the Problem

- Short-form video advertising research shows that content attributes such as entertainment and advertising strategies are linked to consumer engagement — *Journal of Retailing and Consumer Services*. [https://www.sciencedirect.com/science/article/pii/S0969698922002636](https://www.sciencedirect.com/science/article/pii/S0969698922002636)
- TikTok Creative Codes highlights video structure, attention, sound, and other creative principles as important factors in short-form advertising. [https://ads.tiktok.com/business/en-US/creative-codes](https://ads.tiktok.com/business/en-US/creative-codes)

## Initial Related Work / Existing Solutions

- **TikTok Creative Codes** provides guidelines for attention, video structure, sound, and creative techniques. **Limitation:** requires users to manually apply these principles when evaluating videos. [https://ads.tiktok.com/business/en-US/creative-codes](https://ads.tiktok.com/business/en-US/creative-codes)
- **Google ABCDs of Effective Video Ads** provides creative principles for effective video advertising. **Limitation:** does not automatically analyze uploaded videos. [https://services.google.com/fh/files/misc/formarketingshortsabcdsonesheeters.pdf](https://services.google.com/fh/files/misc/formarketingshortsabcdsonesheeters.pdf)

## Engineering Gap / Limitation

Existing marketing guidelines provide useful principles for creating short-form videos, but applying these principles to individual videos remains largely manual. This creates a need for an automated system combining **audio transcription, visual analysis, and multimodal AI** to identify and explain marketing techniques.

## Project Objectives

- **O1:** To design a multimodal AI pipeline for extracting and processing audio and visual data from uploaded short-form videos.
- **O2:** To develop an AI-based system for detecting hooks, messages, emotional appeals, video structures, and CTAs.
- **O3:** To evaluate the system's accuracy, evidence, latency, and cost using manually labelled short-form videos.

## Target Users

Small business owners, digital marketers, and content creators who want to analyze short-form promotional videos and understand their marketing techniques.

## Data Sources

- **TikTok Creative Codes** — Marketing guidelines covering hooks, video structure, sound, and creative techniques. [https://ads.tiktok.com/business/library/TikTok_CreativeCodes_May2023.pdf](https://ads.tiktok.com/business/library/TikTok_CreativeCodes_May2023.pdf)
- **Pitt Ads Dataset (Hussain et al., CVPR 2017)** — 3,477 video advertisements with annotations for topics, sentiments, and persuasive messages. [https://people.cs.pitt.edu/~kovashka/ads/](https://people.cs.pitt.edu/~kovashka/ads/)
- **TikTok Creative Center — Top Ads** — Public collection of high-performing TikTok advertisements for potential testing. [https://ads.tiktok.com/business/creativecenter/](https://ads.tiktok.com/business/creativecenter/)

## Dataset Attribution

This project uses the VADB (Video Aesthetics Database) dataset by BestiVictoryLab.

- **Source:** https://huggingface.co/datasets/BestiVictoryLab/VADB
- **Licence:** CC BY-NC 4.0
- **Modifications:** Four unintended columns were excluded during data preparation. Original records and missing values were preserved.

The dataset is used for non-commercial academic and research purposes. Original dataset rights and licence conditions remain applicable.

## Different from EduAdvisor

While EduAdvisor extracts information from academic resources to answer student queries, the AI Trending Video Analyzer analyzes **multimodal video content**, including frames and speech transcriptions, to identify marketing techniques.

## Responsible AI Risks

- **AI Hallucination:** The AI may detect marketing elements that are not present. **Solution:** Provide timestamps, supporting evidence, and uncertain classifications.
- **Wrong or Biased Interpretation:** The AI may misunderstand emotional, cultural, or marketing aspects. **Solution:** Use clear classification instructions, annotated examples, and explanations for results.

## Weekly Progress

| **Week** | **Focus** | **Deliverable** | **Status** |
|---|---|---|---|
| W1 | Project scope and problem definition | Project scope, problem evidence and initial research | ✅ |
| W2 | Requirements and system architecture | Evaluation criteria and architecture decisions | ✅ |
| W3 | Data sources and dataset preparation | Dataset investigation, selection and data pipeline planning | ✅ |
| W4 | Video extraction pipeline | Video metadata, frames, audio and speech extraction | 🔄 |
| W5 | Multimodal video analysis | Visual, speech and OCR analysis pipeline | ⬜ |
| W6 | Marketing element detection | Hook, messaging, emotion, structure and CTA detection | ⬜ |
| W7 | Evidence and grounding | Timestamped evidence and uncertainty handling | ⬜ |
| W8 | Model evaluation | Accuracy evaluation using manually labelled videos | ⬜ |
| W9 | Performance evaluation | Latency and cost evaluation | ⬜ |
| W10 | System integration | Integrated video analysis pipeline | ⬜ |
| W11 | Testing and refinement | Error analysis and system improvements | ⬜ |
| W12 | Final evaluation and documentation | Final results, README, report and demonstration | ⬜ |
