---
title: "Google Summer of Code @ DeepMind"
date: 2025-09-14
subtitle: "Facet AI: democratizing SLM fine tuning"
---

This summer I had the incredible opportunity to build Facet AI as my Google Summer of Code project. Facet AI’s purpose is simple: democratize fine-tuning for small language models by turning complex, error-prone workflows into a polished, streamlined experience — from dataset formatting and augmentation to evaluation and deployment — so anyone can craft their own "facet" of Gemma, DeepMind’s open-source vision-language model.

<!--more-->

{{< youtube JGnzoLSZReI >}}

{{< button url="https://github.com/gemma-facet" >}}Checkout Facet AI's GitHub{{< /button >}}

## The Small Language Model Revolution

SLMs are moving fast. Weekly releases and focused research mean smaller models now beat larger ones on many specialized benchmarks once they’re tuned. [Researchers from NVIDIA also suggested that SLMs might power the future of agentic AI](https://arxiv.org/pdf/2506.02153). They’re cheaper, faster, and—critically—easier to deploy. That creates an opportunity: if we make fine-tuning accessible, teams outside of AI labs can build high-value, domain-specific models without huge cost or infrastructure overhead.

![Growth of SLMs](https://cdn-bdmhh.nitrocdn.com/JNiKLBzGPsfbQJqUQoZqIbUrxBklWopT/assets/images/optimized/rev-a72f3cd/objectbox.io/wordpress/wp-content/uploads/2024/12/2024_12_16_SLMs_2-1-1.png)

_Online image, slightly outdated as of Sep 2025_

Facet AI is built to be that bridge. Instead of asking users to stitch together notebooks, config files, and ad-hoc scripts, we provide a single, secure place to manage experiments, reproduce results, and iterate with confidence.

### Why Gemma?

![Gemma 3](https://storage.googleapis.com/gweb-developer-goog-blog-assets/images/gemma-3_2.original.png)

Gemma was a natural choice. It comes in many sizes (270M to 27B), supports multimodal and multilingual tasks out of the box, and shows competitive performance across sizes. The community around Gemma — [the "Gemmaverse"](https://deepmind.google/models/gemma/gemmaverse/) — is creative and active, which makes it a great foundation for a platform intended for wide adoption and experimentation.

## Highlights

Working with [Adarsh Dubey](https://www.linkedin.com/in/dubeyadarsh/), we built Facet AI to cover the full fine-tuning lifecycle. Key features include:

1. **Everything dataset!** Formatting, preprocessing, augmentation, LLM-assisted synthesis, and convenient import/export options. Dataset handling is often the messiest part of fine-tuning for newcomers; we standardize and automate the heavy lifting and support TRL-style formats for both supervised fine-tuning and reinforcement approaches.

2. **Configurable training — but beginner friendly.** There are easily 50+ knobs for a training job. We organized parameters into meaningful categories, added sensible defaults, and unified different trainer types (SFT, GRPO, DPO, ORPO, and more) behind the same workflow. The result: with a clear goal, your model is a click away — not buried in 10 pages of docs.

3. A full suite of utilities. **Fine-tuning isn’t just training, just as software engineering isn't just coding**: you need evaluation, benchmarking, and reliable export. Facet provides metrics, comparisons, and export paths directly integrated with vLLM, SGLang, Ollama, LM Studio, llama.cpp, and others so you can move from experiment to production formats fast.

With these capabilities and an account-backed environment that protects user data, Facet moves teams from scattered Colab scripts and fragile repos to a standardized, collaborative, production-minded platform — think managed platform-as-a-service but for fine-tuning.

## My Contributions

This section lists my core technical contributions with links to the PRs:

- Scaffolding the project and initial services: [PR #2](https://github.com/gemma-facet/cloud-services/pull/2) + private old repo
- Text dataset augmentation and synthesis: [services PR](https://github.com/gemma-fine-tuning/services/pull/4)
- Training service using Unsloth and TRL: [PR #7](https://github.com/gemma-facet/cloud-services/pull/7)
- Setup and maintenance of cloud architecture: [PR #14](https://github.com/gemma-facet/cloud-services/pull/14), [PR #36](https://github.com/gemma-facet/cloud-services/pull/36)
- Multimodal training support: [PR #22](https://github.com/gemma-facet/cloud-services/pull/22)
- Evaluation and export tooling (with vLLM optimization): [PR #29](https://github.com/gemma-facet/cloud-services/pull/29), [PR #57](https://github.com/gemma-facet/cloud-services/pull/57)
- Full-stack features (CRUD, accounts, authentication): [PR #34](https://github.com/gemma-facet/cloud-services/pull/34), [PR #35](https://github.com/gemma-facet/cloud-services/pull/35)
- Built-in support for multiple dataset types: [PR #39](https://github.com/gemma-facet/cloud-services/pull/39)
- Reinforcement fine-tuning (RFT) work: [PR #44](https://github.com/gemma-facet/cloud-services/pull/44)
- Terraform IaC and quick deployment on custom clouds: [PR #64](https://github.com/gemma-facet/cloud-services/pull/64)
- Frontend contributions and integrations: [frontend repo](https://github.com/gemma-facet/frontend-ui)

## Challenges

### Unsloth and TRL

Unsloth and TRL are powerful, but they’re actively developed and occasionally break or change behavior. These moving parts sometimes slowed us down. I've engaged with upstream communities — opening issues, discussing on Discord and GitHub, and contributing fixes (e.g. for GRPO, DPO, GGUF export, and evaluation bugs).

### Working with GCP

Designing a maintainable cloud architecture and integrating Terraform taught me a lot about tradeoffs. Scaling from prototype to production surface many migration and refactor decisions; several earlier choices needed rework as our scope and requirements evolved over the months.

## Next Steps for Facet AI

We have a roadmap of improvements tracked here: [Project Roadmap](https://github.com/gemma-facet/cloud-services/issues/52) — contributions, issues, and PRs are welcome.

We’re also raising awareness and looking for collaborators to help drive the platform forward!

## Acknowledgements

Huge thanks to my mentor, Paige Bailey, and the Gemma and Google Cloud teams for their support across the four months. This work also stands on the shoulders of many open-source projects and communities — Unsloth, Transformers, TRL, vLLM, Hugging Face, and the people behind them. Facet AI would not be possible without them.
