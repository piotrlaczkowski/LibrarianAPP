---
title: "No-Human in the Loop: Agentic Evaluation at Scale for Recommendation"
url: https://arxiv.org/abs/2511.03051
tags: [framework, AI/ML, research]
category: Research Paper
date: 2025-11-10
id: A8AFAB7E-DE2F-4FD8-91A2-4FFA3217ECE1
created: 2025-11-10T07:56:54Z
modified: 2025-11-10T07:56:54Z
---
# No-Human in the Loop: Agentic Evaluation at Scale for Recommendation

## Summary

The paper shows how LLMs can judge product recommendations at scale without humans while staying reliable.

It introduces ScalingEval, a multi agent setup that audits pairs, flags issues, and writes reports.

Agents check complement patterns and tag problems like wrong size or too similar for each pair.

Many different models judge the same pairs, and a majority vote creates ground truth labels. 

This reduces bias from any single model and shows where they disagree.

They tested 36 models on 1,745 pairs across common retail categories.

Gemini-1.5-Pro led overall, GPT-4o had the best speed cost mix, and Claude-3.5-Sonnet had the highest confidence near 99%.

GPT-OSS-20B led the open source group.

Electronics and Sports showed strong agreement, while Clothing and Food were harder.

The system outputs counts, issues, conf

**Category:** `Research Paper`  

**Tags:** `framework` `AI/ML` `research`

**Source:** [https://arxiv.org/abs/2511.03051](https://arxiv.org/abs/2511.03051)

---

## Content

No-Human in the Loop: Agentic Evaluation at Scale for Recommendation

[2511.03051] No-Human in the Loop: Agentic Evaluation at Scale for Recommendation In just 5 minutes help us improve arXiv: Annual Global Survey We gratefully acknowledge support from the Simons Foundation, member institutions , and all contributors. > cs > arXiv:2511.03051 Help | Advanced Search All fields Journal reference ACM classification MSC classification Report number arXiv identifier arXiv author ID Help pages quick links Help Pages Computer Science > Artificial Intelligence arXiv:2511.03051 (cs) [Submitted on 4 Nov 2025] Title: No-Human in the Loop: Agentic Evaluation at Scale for Recommendation Authors: Tao Zhang , Kehui Yao , Luyi Ma , Jiao Chen , Reza Yousefi Maragheh , Kai Zhao , Jianpeng Xu , Evren Korpeoglu , Sushant Kumar , Kannan Achan View a PDF of the paper titled No-Human in the Loop: Agentic Evaluation at Scale for Recommendation, by Tao Zhang and 9 other authors HTML (experimental) Abstract: Evaluating large language models (LLMs) as judges is increasingly critical for building scalable and trustworthy evaluation pipelines. We present ScalingEval, a large-scale benchmarking study that systematically compares 36 LLMs, including GPT, Gemini, Claude, and Llama, across multiple product categories using a consensus-driven evaluation protocol. Our multi-agent framework aggregates pattern audits and issue codes into ground-truth labels via scalable majority voting, enabling reproducible comparison of LLM evaluators without human annotation. Applied to large-scale complementary-item recommendation, the benchmark reports four key findings: (i) Anthropic Claude 3.5 Sonnet achieves the highest decision confidence; (ii) Gemini 1.5 Pro offers the best overall performance across categories; (iii) GPT-4o provides the most favorable latency-accuracy-cost tradeoff; and (iv) GPT-OSS 20B leads among open-source models. Category-level analysis shows strong consensus in structured domains (Electronics, Sports) but persistent disagreement in lifestyle categories (Clothing, Food). These results establish ScalingEval as a reproducible benchmark and evaluation protocol for LLMs as judges, with actionable guidance on scaling, reliability, and model family tradeoffs. 4 page, NeurIPS 2025 Workshop: Evaluating the Evolving LLM Lifecycle Artificial Intelligence (cs.AI) ; Information Retrieval (cs.IR) arXiv:2511.03051 [cs.AI] arXiv:2511.03051v1 [cs.AI] for this version) https://doi.org/10.48550/arXiv.2511.03051 Focus to learn more arXiv-issued DOI via DataCite (pending registration) Submission history From: Tao Zhang [ view email ] [v1] Tue, 4 Nov 2025 22:49:39 UTC (13,190 KB) Full-text links: Access Paper: View a PDF of the paper titled No-Human in the Loop: Agentic Evaluation at Scale for Recommendation, by Tao Zhang and 9 other authors View PDF HTML (experimental) TeX Source view license Current browse context: cs.AI | 2025-11 Change to browse by: References & Citations NASA ADS Google Scholar Semantic Scholar export BibTeX citation BibTeX formatted citation Data provided by: Bibliographic Tools Bibliographic and Citation Tools Bibliographic Explorer Toggle Bibliographic Explorer ( What is the Explorer? ) Connected Papers Toggle Connected Papers ( What is Connected Papers? ) Litmaps Toggle Litmaps ( What is Litmaps? ) scite.ai Toggle scite Smart Citations ( What are Smart Citations? ) Code, Data, Media Code, Data and Media Associated with this Article alphaXiv Toggle alphaXiv ( What is alphaXiv? ) Links to Code Toggle CatalyzeX Code Finder for Papers ( What is CatalyzeX? ) DagsHub Toggle DagsHub ( What is DagsHub? ) GotitPub Toggle Gotit.pub ( What is GotitPub? ) Huggingface Toggle Hugging Face ( What is Huggingface? ) Links to Code Toggle Papers with Code ( What is Papers with Code? ) ScienceCast Toggle ScienceCast ( What is ScienceCast? ) Replicate Toggle Replicate ( What is Replicate? ) Spaces Toggle Hugging Face Spaces ( What is Spaces? ) Spaces Toggle TXYZ.AI ( What is TXYZ.AI? ) Related Papers Recommenders and Search Tools Link to Influence Flower Influence Flower ( What are Influence Flowers? ) Core recommender toggle CORE Recommender ( What is CORE? ) Institution About arXivLabs arXivLabs: experimental projects with community collaborators arXivLabs is a framework that allows collaborators to develop and share new arXiv features directly on our website. Both individuals and organizations that work with arXivLabs have embraced and accepted our values of openness, community, excellence, and user data privacy. arXiv is committed to these values and only works with partners that adhere to them. Have an idea for a project that will add value for arXiv's community? Learn more about arXivLabs . Which authors of this paper are endorsers? | Disable MathJax ( What is MathJax? ) Privacy Policy Web Accessibility Assistance arXiv Operational Status
