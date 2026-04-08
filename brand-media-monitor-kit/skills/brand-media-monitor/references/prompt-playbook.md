# Prompt Playbook

## Step 1: Scope Definition

### Purpose

Normalize the task before collecting anything.

### Prompt

```text
You are running a brand media monitoring task.

Normalize the task into a structured spec with:
- brand
- brand keywords
- date range
- topic limiter
- official channels
- external channels
- output requirements

Do not collect data yet.
If the monitoring window is sparse, keep the task valid instead of expanding scope automatically.
```

### Best platform

- OpenClaw
- Codex

## Step 2: Channel Registry

### Purpose

Turn a loose media list into a fixed channel map.

### Prompt

```text
Build a channel registry for this monitoring run.

For each channel, label:
- channel name
- channel type
- collection method
- whether reading count is usually available
- whether it is primary evidence or secondary amplification

Separate official channels from external media.
```

### Best platform

- Codex
- OpenClaw

## Step 3: Collection

### Purpose

Collect raw items by channel and time window.

### Prompt

```text
Collect media items for the specified brand, topic, date range, and channels.

Rules:
- only include items relevant to the topic limiter
- keep official and external media separate
- record exact title, URL, date, platform, reading count if available
- if reading count is not public, mark NA and explain in note
- if a channel has zero relevant hits, record zero-hit status
```

### Best platform

- OpenClaw with web tools
- Codex with documented prompts

## Step 4: Normalization

### Purpose

Convert collected items into a standard raw table.

### Prompt

```text
Normalize the collected items into a raw monitoring table.

Required fields:
- publish_date
- title
- link
- platform
- channel_type
- reading_count
- reading_count_note
- content_type
- sentiment
- keyword_hit
- notes

Do not infer missing numeric values.
```

### Best platform

- Codex
- Claude Code

## Step 5: Analysis

### Purpose

Transform table data into brand guidance.

### Prompt

```text
Analyze the monitoring table for:
- topic concentration
- official vs media amplification
- positive / neutral / negative signals
- media worth continuing
- content gaps
- next-stage content recommendations

Important:
- no negative result is still a valid finding
- identify structural weakness even if explicit negative news is absent
```

### Best platform

- Codex
- OpenClaw

## Step 6: Deliverables

### Purpose

Generate two outputs:

- raw table
- analysis report

### Prompt

```text
Generate final deliverables for a brand media monitoring task:

1. raw data table
2. executive analysis report

The report must end with:
- media cooperation recommendations
- next-stage content recommendations
- monitoring caveats
```

### Best platform

- Codex
- OpenClaw
