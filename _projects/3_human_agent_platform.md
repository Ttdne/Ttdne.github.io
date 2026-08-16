---
layout: page
title: Human–Agent Collaboration Platform
description: Orchestration architecture for a SOC coworking platform (internal pilot, Viettel Cyber Security)
importance: 1
category: industry
---

Most "AI in the SOC" products put the agent underneath the analyst: the human asks, the tool answers. This pilot starts from a different premise — that analysts and AI agents are **equal partners** on the same queue of work.

I designed the orchestration architecture behind it, supporting:

- **Two-way task assignment** — an analyst can hand a task to an agent, and an agent can hand a task back to an analyst.
- **Peer review** in both directions, so an agent's output is reviewable by a human and a human's triage is checkable by an agent.

Internal pilot at Viettel Cyber Security.
