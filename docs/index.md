---
title: Unmeshed - Workflow Orchestration for APIs, AI Agents and Batch Jobs
description: Unmeshed is a workflow orchestration platform built by the team behind Netflix Conductor. Run workflows, API orchestration, batch jobs and AI agents on one engine.
---

<div class="um-hero" markdown>
<p class="um-eyebrow">From the creators of Netflix Conductor</p>

# Code, AI, Rules, and People. One Workflow.

[Unmeshed](https://unmeshed.io/) is a workflow orchestration platform for APIs, AI agents, batch jobs and human approvals, all running as one workflow you can watch in real time.

[Explore Unmeshed](https://unmeshed.io/){ .md-button .md-button--primary }
[Read the official docs](https://unmeshed.io/docs/start-here/getting-started){ .md-button }
</div>

## What is Unmeshed?

Most production systems are a chain of steps: call an API, run some code, ask an LLM, wait for a human to approve, call another service. Without an orchestration layer, that logic ends up spread across cron jobs, queues and glue code, and a simple question like "where is this order stuck?" turns into a multi-hour investigation.

[Unmeshed](https://unmeshed.io/) sits between your services and owns the orchestration layer: sequencing, retries, state, human checkpoints and observability. Your workers stay focused on business logic.

It was founded by the team behind **Netflix Conductor**, the open-source workflow engine that became a widely used standard for microservice orchestration. Read more [about Unmeshed](https://unmeshed.io/about).

## Three products, one engine

<div class="grid cards" markdown>

-   :material-sitemap-outline:{ .lg .middle } **Workflows**

    ---

    Durable, multi-step processes with retries, state and sub-second scheduling.

    [:octicons-arrow-right-24: Workflow Orchestration](https://unmeshed.io/products/workflows)

-   :material-api:{ .lg .middle } **API Orchestration**

    ---

    Serve workflows as high-scale API endpoints, without building a separate BFF layer.

    [:octicons-arrow-right-24: API Orchestration](https://unmeshed.io/products/api-orchestration)

-   :material-calendar-clock:{ .lg .middle } **Batch Jobs**

    ---

    Scheduling at second-level granularity, with every run visible and replayable.

    [:octicons-arrow-right-24: Scheduled jobs guide](https://unmeshed.io/docs/use-cases/scheduled-jobs)

-   :material-robot-outline:{ .lg .middle } **AI Agent Orchestration**

    ---

    AI steps, deterministic code, rules and human approvals in one governed workflow.

    [:octicons-arrow-right-24: LLM step](https://unmeshed.io/docs/refs/llm)

</div>

## Core concepts

- **Workflows** are defined in JSON, YAML or code, and versioned.
- **Steps** can be code, LLM calls, decision tables, human tasks or one of 100+ native integrations.
- **Workers** run your business logic and can be written in Java, Go, Python or TypeScript.
- **State and retries** are handled by the engine, so a failed step resumes instead of restarting the whole process.
- **Visibility** is built in: step-level replay, real-time execution state and audit logs for every run.

See the [concepts overview](https://unmeshed.io/docs/concepts/overview) in the official docs for more.

## Example: an AI-assisted approval workflow

1. **Integration step:** an incoming request arrives through a webhook or API call.
2. **Code step:** a worker validates and enriches the payload.
3. **LLM step:** a model classifies the request and drafts a response.
4. **Decision table:** rules route low-risk requests straight through and flag the rest.
5. **Human task:** a reviewer approves or edits the flagged items.
6. **Integration step:** the result is written back to downstream systems.

If any step fails, Unmeshed retries it according to policy and keeps the workflow state, so the run can be replayed step by step instead of debugged from logs.

## Watch: Steal This Workflow

Short walkthroughs of real workflows built on Unmeshed:

- [Ep. 1: Webhook Reconciliation](https://www.youtube.com/shorts/ldGS5CaVGAQ)
- [Ep. 2: Automated Lead Enrichment](https://www.youtube.com/shorts/aNsmn7X-au4)

More on the [Unmeshed YouTube channel](https://www.youtube.com/@unmeshedio).

## Get started

There's a free tier with no credit card required. Sign up at [unmeshed.io](https://unmeshed.io/), then follow the [Getting Started guide](https://unmeshed.io/docs/start-here/getting-started), or jump to the [Quickstart](quickstart.md) on this site.
