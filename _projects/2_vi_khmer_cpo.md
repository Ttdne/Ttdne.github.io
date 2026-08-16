---
layout: page
title: Vietnamese–Khmer NMT Optimization
description: Contrastive preference optimization for a low-resource pair — published at SOICT '25
importance: 2
category: research
related_publications: true
---

A three-stage pipeline that takes a small general-purpose model and turns it into a competitive Vietnamese→Khmer translator, published as {% cite trinh2025cpo %}.

**Pipeline**

1. **Monolingual continued pre-training** on Khmer text, to give the model a real grip on a script and language it had barely seen.
2. **LoRA supervised fine-tuning** on the available parallel data.
3. **Contrastive Preference Optimization (CPO)** over **27K self-constructed preference triplets** — built without human annotation.

**Results.** Surpassed Sailor2-1B, DPO, and GPT-4o-mini across BLEU, METEOR, COMET, and COMET-KIWI.

<!-- TODO: add the public repository link, e.g.
[Code on GitHub](https://github.com/Ttdne/<repo-name>)
-->
