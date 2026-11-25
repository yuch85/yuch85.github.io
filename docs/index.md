---
title: A Linux for legaltech
---

# Vision

Our mission is to build a shared, open, and community-driven foundation for the future of legal technology — a “Linux for legaltech.” We aim to unite lawyers, engineers, researchers, and builders around a common infrastructure layer that empowers everyone, especially small and mid-sized firms who lack access to expensive proprietary tools. This project is not driven by profit; it is driven by the belief that legal AI should be transparent, extensible, and accessible to all, with a core that stays open as a public commons.

*Written on 11 December 2025. That conviction still stands.*

Since then, we've built infrastructure, tooling, products and open source educational materials, in the belief that the fruits of AI should be distributed for the greater good.

# Redlines that stay in Word

Lawyers work in .docx with Track Changes. These tools let AI edit a Word file without breaking it.

- **[superdoc-redlines](https://github.com/yuch85/superdoc-redlines)**: CLI that applies tracked changes and comments to DOCX files with SuperDoc headless mode. Built for AI agents, with contract review skills and a demo of multi-agent review of a 100+ page contract.
- **[office-word-diff](https://github.com/yuch85/office-word-diff)**: Applies word-level diffs to Word through Office.js as granular tracked changes. Falls back from token map to sentence diff to block replace. Apache 2.0. The README calls it experimental.
- **Word AI Redliner** ([architecture](https://yuch85.github.io/word-ai-redliner/), [repo](https://github.com/yuch85/word-ai-redliner)): Word add-in that applies LLM edits as native tracked changes, with prompt management, document summary, and Ollama or vLLM backends.
- **Contract Playbook AI** ([details](ContractAI.md), [repo](https://github.com/yuch85/contract-playbook-ai)): Browser-based playbook generation and contract review against a playbook, with true .docx Track Changes. The first project on this site.

# Sources an AI can check

Tools that tie AI output back to the official record.

- **[sgcite](https://github.com/yuch85/sgcite)**: CLI that checks Singapore case citations against eLitigation. Flags hallucinated authorities, wrong case names, fabricated quotes and paragraph numbers. Output feeds superdoc-redlines.
- **sg-hansard-gateway** ([project page](https://yuch85.github.io/sg-hansard-gateway/), [repo](https://github.com/yuch85/sg-hansard-gateway)): Self-hosted gateway that gives any chat AI plain-HTTP access to Singapore Parliamentary Hansard, with a SHA-256 provenance footer on each transcript.
- **[text-provenance](https://github.com/yuch85/text-provenance)**: Finds which source sentence a piece of text most likely came from, even when paraphrased or partly quoted.

# Learning to use and test legal AI

Free material for lawyers who want to understand the tools.

- **Statistics for Legal Evals** ([course](https://yuch85.github.io/stats-for-legal-evals/), [repo](https://github.com/yuch85/stats-for-legal-evals)): 19-episode podcast on evaluating legal AI with statistics: test sets, intervals, comparisons, calibration, grading and reporting. Slides, audio and video.
- **Security for Legal SaaS** ([series](https://yuch85.github.io/security-for-legal-saas/), [repo](https://github.com/yuch85/security-for-legal-saas)): Podcast series on security for legal software.
- **AI for Lawyers** ([materials](https://yuch85.github.io/ai-for-lawyers/), [repo](https://github.com/yuch85/ai-for-lawyers)): Materials for lawyers who want to get up to speed on AI and legal tech.

# Agents making media, and testing models

Two experiments outside the legal workflow.

- **[alice-music-video](https://github.com/yuch85/alice-music-video)**: AI-native pipeline for generating narrative music videos with open-source models. It orchestrates planning, image generation, motion synthesis, lip sync, timing and final assembly, for reproducible, story-driven workflows.
- **[claude-recall-bench](https://github.com/yuch85/claude-recall-bench)**: Eval harness that tests Claude's verbatim reproduction fidelity across context window sizes, run through Claude Code.
