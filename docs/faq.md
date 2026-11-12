---
title: Unmeshed FAQ
description: Common questions about Unmeshed - comparison with Temporal, Netflix Conductor migration, free tier, self-hosting, SDK languages and AI agents.
---

# FAQ

??? question "How is Unmeshed different from Temporal?"
    Unmeshed keeps orchestration outside your services: workflows are defined in JSON, YAML or code, and workers in any of four languages just handle their own steps. It also ships API orchestration, schedules, LLM steps, human tasks and 100+ integrations out of the box. See the [full Unmeshed vs Temporal comparison](https://unmeshed.io/compare/temporal).

??? question "Can I migrate from Netflix Conductor?"
    Yes. Unmeshed was built by the Conductor team and has a dedicated [Conductor migration guide](https://unmeshed.io/docs/authoring/conductor-migration-guide).

??? question "Is there a free tier?"
    Yes: 2,000 workflow executions a month with unlimited steps per workflow, and no credit card required. See [pricing](https://unmeshed.io/pricing).

??? question "Can I self-host Unmeshed?"
    Yes. You can run Unmeshed in its cloud or your own infrastructure, and self-hosting doesn't require checking in with a license server.

??? question "Which languages can I write workers in?"
    There are official SDKs for [Java](https://unmeshed.io/docs/sdks/java-sdk), [Python](https://unmeshed.io/docs/sdks/python-sdk), [Go](https://unmeshed.io/docs/sdks/go-sdk) and [JavaScript/TypeScript](https://unmeshed.io/docs/sdks/javascript-typescript-sdk). Short Python or JavaScript logic can also run inline as a script step.

??? question "Does Unmeshed support AI agents?"
    Yes. LLM calls run as workflow steps alongside deterministic code, rules and human approvals, so agent workflows get the same retries, audit logs and replay as everything else.
