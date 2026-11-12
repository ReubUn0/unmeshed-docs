---
title: Unmeshed step types reference
description: The main step types available in Unmeshed workflows, from HTTP and worker steps to LLM, parallel, foreach and wait steps.
---

# Step types reference

Unmeshed workflows are built from steps. These are the most commonly used types:

| Step type | Use it for | Docs |
| --- | --- | --- |
| HTTP | Call any REST API with templated inputs | [HTTP step](https://unmeshed.io/docs/refs/step-type-http) |
| Worker | Run your own code through an SDK worker | [Worker step](https://unmeshed.io/docs/refs/step-type-worker) |
| Python / JavaScript | Run short scripts inline, no worker needed | [Python step](https://unmeshed.io/docs/refs/step-type-python) |
| AI LLM | Call a language model as a workflow step | [LLM step](https://unmeshed.io/docs/refs/llm) |
| Switch case | Branch on data from earlier steps | [Switch case](https://unmeshed.io/docs/refs/step-type-switch-case) |
| Parallel | Run branches at the same time | [Parallel step](https://unmeshed.io/docs/refs/step-type-parallel) |
| Foreach | Loop over a list of items | [Foreach step](https://unmeshed.io/docs/refs/step-type-foreach) |
| Wait | Pause for a human approval or external event | [Wait step](https://unmeshed.io/docs/refs/step-type-wait) |
| Sub Process | Reuse another workflow as a step | [Sub Process](https://unmeshed.io/docs/refs/step-type-sub-process) |

Rules can be added with [decision tables](https://unmeshed.io/docs/concepts/decision-table-rules), and failures are handled by configurable [error policies](https://unmeshed.io/docs/concepts/error-policies).

For the full list and every option, see the [step definition reference](https://unmeshed.io/docs/refs/step-definition) in the official docs.
