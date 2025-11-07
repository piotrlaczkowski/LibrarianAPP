---
title: Continuous Autoregressive Language Models
url: https://arxiv.org/abs/2510.27688
tags: [news, ai, code, development, machine-learning, research, academic, documentation]
category: Research Paper
date: 2025-11-07
id: DF93C680-03EF-4A56-AA2E-FD871987BA42
created: 2025-11-07T09:02:18Z
modified: 2025-11-07T09:02:18Z
---
# Continuous Autoregressive Language Models

## Summary

The efficiency of large language models (LLMs) is fundamentally limited by their sequential, token-by-token generation process. We argue that overcoming this bottleneck requires a new design axis for LLM scaling: increasing the semantic bandwidth of each generative step.

**Category:** `Research Paper`  

**Tags:** `news` `ai` `code` `development` `machine-learning` `research` `academic` `documentation`

**Source:** [https://arxiv.org/abs/2510.27688](https://arxiv.org/abs/2510.27688)

---

## Content

Continuous Autoregressive Language Models

[2510.27688] Continuous Autoregressive Language Models In just 5 minutes help us improve arXiv: Annual Global Survey We gratefully acknowledge support from the Simons Foundation, member institutions , and all contributors. > cs > arXiv:2510.27688 Help | Advanced Search All fields Journal reference ACM classification MSC classification Report number arXiv identifier arXiv author ID Help pages quick links Help Pages Computer Science > Computation and Language arXiv:2510.27688 (cs) [Submitted on 31 Oct 2025] Title: Continuous Autoregressive Language Models Authors: Chenze Shao , Darren Li , Fandong Meng , Jie Zhou View a PDF of the paper titled Continuous Autoregressive Language Models, by Chenze Shao and 3 other authors HTML (experimental) Abstract: The efficiency of large language models (LLMs) is fundamentally limited by their sequential, token-by-token generation process. We argue that overcoming this bottleneck requires a new design axis for LLM scaling: increasing the semantic bandwidth of each generative step. To this end, we introduce Continuous Autoregressive Language Models (CALM), a paradigm shift from discrete next-token prediction to continuous next-vector prediction. CALM uses a high-fidelity autoencoder to compress a chunk of K tokens into a single continuous vector, from which the original tokens can be reconstructed with over 99.9\% accuracy. This allows us to model language as a sequence of continuous vectors instead of discrete tokens, which reduces the number of generative steps by a factor of K. The paradigm shift necessitates a new modeling toolkit; therefore, we develop a comprehensive likelihood-free framework that enables robust training, evaluation, and controllable sampling in the continuous domain. Experiments show that CALM significantly improves the performance-compute trade-off, achieving the performance of strong discrete baselines at a significantly lower computational cost. More importantly, these findings establish next-vector prediction as a powerful and scalable pathway towards ultra-efficient language models. Code: this https URL . Project: this https URL . Computation and Language (cs.CL) ; Artificial Intelligence (cs.AI); Machine Learning (cs.LG) arXiv:2510.27688 [cs.CL] arXiv:2510.27688v1 [cs.CL] for this version) https://doi.org/10.48550/arXiv.2510.27688 Focus to learn more arXiv-issued DOI via DataCite Submission history From: Chenze Shao [ view email ] [v1] Fri, 31 Oct 2025 17:58:11 UTC (133 KB) Full-text links: Access Paper: View a PDF of the paper titled Continuous Autoregressive Language Models, by Chenze Shao and 3 other authors View PDF HTML (experimental) TeX Source view license Current browse context: cs.CL | 2025-10 Change to browse by: References & Citations NASA ADS Google Scholar Semantic Scholar export BibTeX citation BibTeX formatted citation Data provided by: Bibliographic Tools Bibliographic and Citation Tools Bibliographic Explorer Toggle Bibliographic Explorer ( What is the Explorer? ) Connected Papers Toggle Connected Papers ( What is Connected Papers? ) Litmaps Toggle Litmaps ( What is Litmaps? ) scite.ai Toggle scite Smart Citations ( What are Smart Citations? ) Code, Data, Media Code, Data and Media Associated with this Article alphaXiv Toggle alphaXiv ( What is alphaXiv? ) Links to Code Toggle CatalyzeX Code Finder for Papers ( What is CatalyzeX? ) DagsHub Toggle DagsHub ( What is DagsHub? ) GotitPub Toggle Gotit.pub ( What is GotitPub? ) Huggingface Toggle Hugging Face ( What is Huggingface? ) Links to Code Toggle Papers with Code ( What is Papers with Code? ) ScienceCast Toggle ScienceCast ( What is ScienceCast? ) Replicate Toggle Replicate ( What is Replicate? ) Spaces Toggle Hugging Face Spaces ( What is Spaces? ) Spaces Toggle TXYZ.AI ( What is TXYZ.AI? ) Related Papers Recommenders and Search Tools Link to Influence Flower Influence Flower ( What are Influence Flowers? ) Core recommender toggle CORE Recommender ( What is CORE? ) Institution About arXivLabs arXivLabs: experimental projects with community collaborators arXivLabs is a framework that allows collaborators to develop and share new arXiv features directly on our website. Both individuals and organizations that work with arXivLabs have embraced and accepted our values of openness, community, excellence, and user data privacy. arXiv is committed to these values and only works with partners that adhere to them. Have an idea for a project that will add value for arXiv's community? Learn more about arXivLabs . Which authors of this paper are endorsers? | Disable MathJax ( What is MathJax? ) Privacy Policy Web Accessibility Assistance arXiv Operational Status
