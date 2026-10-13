---
layout: post
title: Exploring federated learning for AI agents
date: 2026-9-13 10:00:00+0700
description: early notes on federated learning in multi-agent systems, sparked by a conversation with a colleague
tags: notes federated-learning agents
categories:
related_posts: false
---

A conversation with a colleague got me curious about a question I had not thought about before: what happens when AI agents need to learn from each other without sharing their data? I am still at the beginning, so this post is a set of notes and open questions rather than a conclusion.

## Why this caught my attention

My recent work has been about small models that run locally, in low-resource or air-gapped settings. In those settings the data often cannot leave the machine. That is exactly the situation federated learning (FL) was designed for.

## The basic idea

In classic FL (FedAvg), each client trains on its own private data and sends only model updates to a server. The server aggregates the updates into a global model and sends it back. The raw data never moves.

## Where agents come in

An LLM-based agent is more than a model. It also has memory, tools, and a policy for using them. That raises questions that plain FL does not cover:

- **What is shared?** Weights, LoRA adapters, or something higher-level such as skills, prompts, and memory entries?
- **Heterogeneity.** Different agents see different tasks and data, so a single averaged model may fit none of them well.
- **Communication cost.** Sharing full LLM weights is impractical, so parameter-efficient methods look like a natural fit.
- **Privacy.** Updates can still leak information about the data, so differential privacy and secure aggregation matter.
- **Trust.** In a system of many agents, some may be faulty or malicious, which makes robust aggregation important.

## What I plan to look at next

1. Federated fine-tuning of small language models with LoRA adapters.
2. How to aggregate across clients with very different data (non-IID).
3. Whether agent-level knowledge, not just weights, can be shared safely.

I will update this blog as I read more. Thanks to my colleague for the spark, and if you work on this topic I would be glad to hear your thoughts.

Here are the papers I plan to read, roughly in the order I will go through them.

## Foundations

- McMahan et al., 2017. _Communication-Efficient Learning of Deep Networks from Decentralized Data_ (FedAvg).
- Kairouz et al., 2021. _Advances and Open Problems in Federated Learning_.
- Li et al., 2020. _Federated Optimization in Heterogeneous Networks_ (FedProx).
- Bonawitz et al., 2017. _Practical Secure Aggregation for Privacy-Preserving Machine Learning_.

## Federated learning with language models

- Zhang et al., 2023. _FedPETuning: When Federated Learning Meets the Parameter-Efficient Tuning Methods of Pre-trained Language Models_.
- Ye et al., 2024. _OpenFedLLM: Training Large Language Models on Decentralized Private Data via Federated Learning_.

## Agentic and federated learning

- [_Agentic Federated Learning: The Future of Distributed Training Orchestration_](https://arxiv.org/abs/2604.04895), 2026. A position paper on using LM-agents to orchestrate FL.
- [_FL-MAESTRO: Multi-Agent LLM Orchestration for Resource-Constrained Federated Learning_](https://arxiv.org/abs/2608.20518), 2026.
- [_Fed-SE: Federated Self-Evolution for Privacy-Constrained Multi-Environment LLM Agents_](https://arxiv.org/abs/2512.08870), 2025.
- [_FederatedSkill: Federated Learning for Agentic Skill Evolution_](https://arxiv.org/abs/2606.03143), 2026.
- [_FedAgentKE: Federated Semantic Knowledge Evolution for Heterogeneous Agents_](https://arxiv.org/abs/2607.21361), 2026.
- [_FedWorld: Scope-Aware Federation of Agent World Models_](https://arxiv.org/abs/2608.01561), 2026.
- [_Privacy-Enhancing Paradigms within Federated Multi-Agent Systems_](https://arxiv.org/abs/2503.08175), 2025.

## Open questions

- What should agents share with each other: weights, adapters, or higher-level knowledge such as skills and memory?
- How does learning hold up when every agent sees very different data?
- How do you keep it private and robust when some agents are faulty or malicious?

I will add notes on each paper as I read them.
