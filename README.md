# Local AI Signal

A curated daily feed for people building and learning at the edge of local and on-device AI.

**[Explore the live feed →](https://local-ai-signal.vercel.app/)**

## Why I built it

Local AI is moving quickly, but the useful signal is fragmented across technical discussions, research papers, GitHub repositories, and individual builders.

Local AI Signal is my attempt to bring the most useful parts together in one place. It is deliberately curated rather than being an exhaustive news feed.

## What you’ll find

- High-signal Hacker News discussions
- Recent research about local and on-device AI
- Active open-source tools and repositories
- Resources and bookmarks worth returning to

## How it works

The feed discovers, normalizes, deduplicates, and ranks material from several sources. Each source has its own relevance and quality checks.

The goal is not to capture everything. It is to make useful work easier to find.

## How I built it

I started with a small question: could I make it easier to follow the technical conversations shaping local AI without checking several places every day?

The first version only collected Hacker News discussions. I searched for terms around local AI, on-device inference, local LLMs, quantization, WebGPU, Apple Silicon, and related topics. I quickly learned that the article title was often less useful than the discussion underneath it, so I began surfacing valuable comments as part of the feed.

From there, I added two more pipelines:

- **GitHub:** find actively maintained local-AI runtimes, frameworks, SDKs, and infrastructure—not every repository that happens to mention “local AI.”
- **Research:** find recent papers about running and optimizing models on personal devices, using OpenAlex and a rolling publication window.

Each pipeline follows the same broad sequence:

1. Search several focused queries.
2. Normalize records from different sources into a common format.
3. Deduplicate them by URL, repository, DOI, or title.
4. Apply source-specific relevance checks.
5. Rank the remaining items by recency, activity, and usefulness.
6. Present them in a simple, single-column feed.

The hardest part was not building the interface. It was defining what counts as signal.

For example, GitHub results need evidence that a project genuinely supports local execution, not just an AI-related description. Research papers need explicit on-device or local-inference relevance. Recent work gets some preference, but foundational work should not disappear merely because it is older.

I have been building the project incrementally with coding agents: first making a narrow version work, then testing the results, inspecting what slipped through, and tightening the retrieval and ranking rules. The code remains private for now, but I will keep sharing the product decisions and lessons here.

## What I’m learning

- Aggregation is easy; useful filtering is the product.
- Different sources need different definitions of quality.
- A small number of strong results is better than a complete but noisy feed.
- Comments and implementation discussions can be more valuable than the original link.
- Curation rules need repeated inspection—they cannot be perfected in one prompt.

## Follow the wider collection

- [Builders and researchers on X](https://x.com/i/lists/2077181126834282532)
- [Local AI tools on GitHub](https://github.com/stars/aginfers/lists/local-ai-tools)
- [Aishwarya Goel on X](https://x.com/aishwarya_08)

## About this repository

This public repository is the home for the project overview and future notes about what I learn while building Local AI Signal. The application code is maintained privately.

## Project status

Local AI Signal is an evolving personal project. I update its sources and curation as I discover better signals.
