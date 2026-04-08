---
name: brand-media-monitor
description: Use when a team needs a reusable brand media monitoring and brand-content-analysis workflow for IVD or healthcare brands, especially when the output must guide brand, content, and media decisions instead of stopping at link collection or light monitoring summaries.
---

# Brand Media Monitor

## Overview

This skill builds a **generic, reusable brand media monitoring system**.

It is designed for:

- self-brand monitoring
- competitor monitoring
- campaign review
- topic-specific media scanning

It is **not** a one-off search skill for a single brand.

The correct usage is:

1. define the monitoring task
2. register channels
3. collect by channel
4. normalize the raw table
5. analyze
6. produce action-ready deliverables

## What Problem It Solves

Most brand teams do not actually have a monitoring system.

They usually have:

- temporary searching
- inconsistent channel scope
- mixed official and external evidence
- screenshots or loose links
- weak reports that end with "no obvious negative news"

This skill solves that by forcing a repeatable structure:

- configurable inputs
- a fixed execution workflow
- standard output fields
- recommendations that can guide next-stage content actions

## Required Inputs

Every run must define:

- brand
- brand keywords
- date range
- topic limiter
- channel list

Optional:

- competitor names
- must-watch event keywords
- must-watch product lines
- platform priority

## Required Outputs

### Output 1: Raw Monitoring Table

Must include:

- publish_date
- title
- link
- platform
- media_name
- channel_type
- reading_count
- reading_count_note
- content_type
- sentiment
- keyword_hit
- notes

### Output 2: Analysis Report

Must answer:

- what the brand published in the chosen window
- which topics dominated
- how official content and media amplification work together
- what the brand activity design and release rhythm look like
- whether any negative or potentially negative signal exists
- which channels are worth continued cooperation
- what content gaps are visible
- what the next-stage content recommendation should be

## Execution Workflow

### Step 1: Define the monitoring task

Do not search yet.

Turn the user request into a structured monitoring spec first.

### Step 2: Build the channel registry

For every channel, define:

- channel name
- official or external
- platform type
- collection method
- reading-count availability
- evidence priority

### Step 3: Collect by channel

Collect strictly within:

- brand scope
- topic limiter
- date range
- approved channels

### Step 4: Normalize into a raw table

Do not invent:

- dates
- links
- reading counts
- sentiment evidence

If missing, keep it explicit.

### Step 5: Analyze

Look at:

- topic concentration
- official vs external amplification
- event rhythm
- sentiment/risk
- channel value
- content gaps
- strategic learnings for brand/content teams

### Step 6: Deliver

Produce:

- raw CSV or Markdown table
- analysis report

Optional:

- competitor comparison memo
- content recommendation memo
- article-ready system story

## Collection Rules

- prefer first-hand official and media pages
- prefer article-level links instead of search snapshots
- keep official channels and external media separate
- for WeChat channels, search via `agent-reach` first instead of plain web search
- after WeChat links are found, parse them with `wechat-article-extractor`
- do not invent reading counts
- if reading count is unavailable, mark `NA` and explain why
- duplicates and reposts should be marked, not hidden
- zero-hit channels must still be recorded
- sparse windows are valid outcomes
- do not broaden the topic just to make the report look fuller

## Analysis Rules

When analyzing, do not stop at volume.

You must distinguish:

- official output
- external pickup
- platform-level amplification
- structural weakness
- topic strategy
- publishing rhythm
- trust-building pattern
- media role split

Important:

- "no negative signal" is not the end of analysis
- a brand can be low-risk but still weak in content structure
- the report is for brand learning, not workflow self-evaluation

## Platform Fit

### OpenClaw

- best for repeated monitoring work
- best for workspace artifact storage
- best when the user wants files, reports, and automations

### Codex

- best for building the reusable system itself
- best for templates, workflows, and report generation

### Claude Code

- good for running a fixed monitoring packet once prompts are already stable
- not ideal for loosely defined monitoring tasks without documentation

## Recommended Skill Routing

- monitoring orchestration:
  - `brand-media-monitor`
- wechat search:
  - `agent-reach`
- web search and site collection:
  - `web-access`
- wechat article extraction:
  - `wechat-article-extractor`
- article conversion after the system is proven:
  - `c-account-manager`
  - `dan-koe-coach-v2`

## Output Paths

Default sample run paths:

- raw table:
  - `examples/<run-id>/raw-table.csv`
- analysis report:
  - `examples/<run-id>/analysis-report.md`
- run configs:
  - `examples/<run-id>/config.yaml`

## References

Read:

- `references/input-template.md`
- `references/output-spec.md`
- `references/analysis-framework.md`
- `references/medical-brand-report-outline.md`
- `references/prompt-playbook.md`
- `references/channel-registry-template.md`
