Project Name	A Multimodal AI System for Short-Form Video Marketing Analysis

Domain	Multimodal AI

Problem Statement	Small businesses, marketers and content creators usually find it hard to systematically analyze the marketing techniques employed in short-form videos. Manual identification of elements like hooks, key messaging, emotions, structure of the video and call-to-action (CTAs) can take time and be subjective



This project aims to develop an AI system for analysis short-form videos uploaded to the platform through speech recognition, visual analysis and large language models (LLMs)

Evidence of the Problem	Evidence 1: 

Studies on short form videos advertisements have found that content attributes such as entertainment and the use of advertising strategies, are linked to consumer engagement. This indicated the need to study the creativity attributes present in marketing videos



Source / citation:

Exploring the factors influencing consumer engagement behavior regarding short-form video advertising. Journal of Retailing and Consumer Services.

https://www.sciencedirect.com/science/article/pii/S0969698922002636



Evidence 2:

Creative Codes of TikTok considers aspects such as video structure, attention stimulation, sound, and other principles as essential consideration in short-form video advertisements. Such considerations entail going beyond the basics of the views and likes.



Source / citation:

TikTok for Business — Creative Codes.

https://ads.tiktok.com/business/en-US/creative-codes



Initial Related	Study / Solution 1: TikTok Creative Codes

Source / citation:

https://ads.tiktok.com/business/en-US/creative-codes

Key limitation: Provides marketing guidelines but does not directly offer automated, evidence based analysis uploaded videos.



Study / Solution 2: Google — ABCDs of Effective Video Ads

Source / citation:

https://services.google.com/fh/files/misc/formarketingshortsabcdsonesheeters.pdf

Key limitation: Provides creative principles for effective video advertising but requires users to manually apply them when evaluating video content.

Engineering Gap / Limitations	The current guidelines for marketing, as well as marketing research, provide valuable information on how video content should be made, yet it is difficult to analyze individual videos based on such frameworks, which calls for a need to develop an automatic system that will integrate audio transcription, image processing, and interpretation by AI algorithms.

Initial Project Objectives	Objective O1: To design a multi-modal AI pipeline for extraction and processing of audio and visual data of uploaded short-form videos.



Objective O2: To create an AI-based video analysis system capable of detecting hooks, messages, emotional appeals, video structures, and call-to-action messages by means of multi-modal AI and public marketing guides.



Objective O3: To analyze the accuracy, evidence, latency, and cost of the system by using manually label short-form videos.

Target Users	Small business owners, digital marketers, and content creators who want to analyze short-form promotional videos and improve their understanding of video marketing strategies.

Data Sources	Source 1: TikTok Creative Codes

Official marketing guidelines covering attention-grabbing hooks, video structure, sound, and creative techniques. Used as reference knowledge for AI-based video analysis.

URL: https://ads.tiktok.com/business/library/TikTok\_CreativeCodes\_May2023.pdf



Source 2: Pitt Ads Dataset (Hussain et al., CVPR 2017)

An academic advertising dataset containing 3,477 video advertisements with human annotations for topics, sentiments, and persuasive messages. Intended for evaluating the AI system's video understanding and marketing-element identification, subject to video availability and usage permissions.

URL: https://people.cs.pitt.edu/\~kovashka/ads/



Source 3: TikTok Creative Center — Top Ads

A public collection of high-performing TikTok advertisements. Potentially useful for identifying realistic short-form promotional videos for testing, subject to platform access and usage permissions.

URL: https://ads.tiktok.com/business/creativecenter/



Different from EduAdvisor	While EduAdvisor works towards extracting information from academic resources to respond to queries posed by students, the AI Trending Video Analyzer analyzes multimedia content like video frames and transcriptions of voice over to detect marketing tactics.

Responsible AI Risks	Risk 1 – AI Hallucination: The AI might erroneously detect marketing components in the video that don’t exist.

Solution: Provide timestamp support and require either transcripts or visual proof, as well as room for undetectable and uncertain classifications.



Risk 2 – Wrong or Biased Interpretation: The AI might misunderstand the emotional appeal, cultural aspects, or marketing message.

Solution: Include clear classification instructions, annotated sample cases, and explanations for AI results.





