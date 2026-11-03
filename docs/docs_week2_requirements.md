# Requirements Specification — AI Trending Video Analyzer

**Version:** 1.0  
**Project:** AI Trending Video Analyzer — A Multimodal AI System for Short-Form Video Marketing Analysis

---

## Section 1 — Functional Requirements (FR)

| # | Requirement — The system SHALL | Scope Boundary — SHALL NOT (where relevant) |
|---|---|---|
| FR1 | The system shall provide users with the possibility to upload a single short-form video no longer than 60 seconds and show whether the upload was accepted or rejected. | Shall not accept unsupported formats of files and/or videos of length surpassing the defined limitation. |
| FR2 | The system shall identify the marketing elements in the video such as hooks, key messages, emotional elements, structure of the video and calls to actions (CTAs). | Shall not make claims that the detected elements will lead to video popularity and engagement. |
| FR3 | The system shall present marketing elements with timestamps and supporting transcript or image (when applicable). | Shall not represent unsupported interpretations as confirmed findings. |
| FR4 | The system shall generate insights and recommendations for improving marketing aspects according to the analyzed video and reference guidelines. | Shall not forecast virality of the video, track real-time social media trends and guarantee marketing success. |
| FR5 | The system shall provide the results of analysis in the form of well-structured dashboard and shall mark if the element was detected in an unreliable manner. | Shall not make up any information that is absent or force any classification without enough evidence. |

---

## Section 2 — Non-Functional Requirements (NFR)

| # | Quality Attribute | Requirement | Measurement Method | Metric | Threshold |
|---|---|---|---|---|---|
| NFR1 | Performance | The system shall process the video in an acceptable period of time. | Evaluate the end-to-end latency of processing 20 test videos no longer than 60 seconds, excluding upload transfer time. | 90th-percentile latency for end-to-end processing (seconds) | ≤ 120 seconds |
| NFR2 | Correctness | The system shall correctly recognize hooks and CTAs in short-form videos. | Compare predicted labels to manually annotated reference labels from 20–30 videos according to predefined annotation rubric. | Macro-averaged F1-score for hook classification and CTA detection, separately. | ≥ 0.75 for each task |
| NFR3 | Reliability | The system shall process the video upload successfully. | Launch 30 video analysis attempts and count successful ones. | Rate of successful video processing (%) | ≥ 90% |
| NFR4 | Cost | The system shall keep low AI processing costs per video. | Evaluate the model/API usage and calculate the average cost per video in the testing dataset. | Model/API cost per analyzed video (USD) | ≤ US$0.10 per video |

Section 3 — Responsible AI Requirements (RAI)
#	Responsible AI Risk	Requirement	Measurement Method	Metric	Threshold
RAI1	Hallucination / Grounding	The system shall provide verifiable transcript or visual evidence for each detected marketing element and indicate when evidence is insufficient.	Manually inspect 20–30 analyzed videos and verify the evidence supporting each detected element.	Evidence presence rate; evidence correctness rate	100% evidence presence; ≥ 90% evidence correctness
RAI2	Bias / Inaccurate Interpretation	The system shall avoid presenting subjective emotional interpretations as objective facts and shall identify uncertainty where appropriate.	Review emotional appeal outputs against a predefined rubric using human-annotated examples.	Percentage of subjective interpretations appropriately qualified	≥ 90%
RAI3	Privacy / Data Protection	The system shall protect uploaded video content and avoid retaining uploaded files beyond the required analysis period.	Inspect temporary storage after each completed or failed analysis and verify file deletion within the defined retention window.	Percentage of uploaded videos deleted within 24 hours after analysis completion or failure	100%
________________________________________
Reflection
Which Responsible AI requirement will be the most difficult to measure or enforce technically? Why?
RAI2 — Bias and Inaccurate Interpretation will be the most difficult to measure because emotional appeals and marketing messages are subjective and may be interpreted differently depending on cultural background, audience expectations, and personal experiences. Unlike detecting a spoken CTA, identifying an intended emotion does not always have one correct answer. Therefore, the system will require clear annotation guidelines, human evaluation, and appropriate uncertainty indicators to reduce misleading interpretations.
