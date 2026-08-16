---
layout: page
title: Multi-Level Knowledge Distillation for Low-Resource NMT
description: Graduation thesis, BKAI NLP Lab — grade 9.3/10
importance: 1
category: research
---

A multi-level knowledge-distillation framework that transfers translation ability from large teacher models into compact students (Qwen3-1.7B, Qwen2.5-0.5B) for language pairs with almost no parallel data.

**What it does**

- Distribution-aware **logit distillation**, so the student matches the teacher's output distribution rather than only its argmax.
- **Full-layer feature alignment** between teacher and student representations, not just the final layer.
- **Intra-student cross-lingual contrastive learning**, pulling the student's representations of the same meaning in different languages together.

**The hard part.** Teacher and student use different tokenizers, so their vocabularies do not line up and logits cannot be compared position by position. I resolved this with **bipartite-graph span alignment**, matching spans across the two tokenizations before computing the distillation loss.

**Results (chrF++ on FLORES-200, 1.7B student)**

| Direction | Before | After |
| --------- | ------ | ----- |
| Vi → Khmer | 10.09 | **30.41** |
| Vi → Lao   | 6.54  | **30.86** |

Supervised by Assoc. Prof. Le Thanh Huong.
