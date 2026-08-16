---
layout: page
title: EDR-SLM Framework
description: Replacing heavy LLMs with fine-tuned small models in a multi-agent NL-to-SQL pipeline
importance: 3
category: industry
---

A multi-agent EDR pipeline was leaning on large language models for every step, including the narrow, highly structured one: turning an analyst's natural-language question into SQL.

I fine-tuned **Qwen models from 0.5B to 8B** with **Unsloth** and **LoRA** to take over that step, then optimized along three axes at once:

- **execution outcome** — does the generated SQL actually run and return the right rows,
- **inference latency**,
- **VRAM footprint**.

The result is a pipeline that keeps the accuracy of the large-model version at a fraction of the serving cost.
