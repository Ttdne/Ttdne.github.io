---
layout: page
title: Self-Defending AI Agent Architecture
description: Multi-turn adversarial exploits and safety-aligned agent design
importance: 4
category: industry
---

An agent that can write and run code is only as safe as its worst conversation. Single-turn safety filters miss the interesting attacks, because the interesting attacks are spread across turns.

I studied **multi-turn adversarial exploits** — prompt injection and logic deception, where each individual turn looks benign and only the trajectory is malicious — and used what they revealed to design safety-aligned agent architectures that:

- **detect malicious intent** as it accumulates across a conversation rather than within a single message, and
- **enforce a safe execution policy** at the moment of code and Bash generation.

Research conducted at Viettel Cyber Security.
