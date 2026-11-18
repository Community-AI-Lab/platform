# Platform architecture — initial sketch

This is a design starting point, not a finished architecture.

## Components

- **Contributor interface:** one account, projects and tasks, agreement status, submission history and provisional credit history.
- **Work management:** GitHub Issues and pull requests first. A standalone task board is optional until needed.
- **Submission and review:** accept links to code/research; later support licensed data, evaluation tasks and uploaded results.
- **Contribution ledger:** append-only records linking contributor, task, evidence, reviewer, date and provisional credits. Track model/project association and amendments.
- **GPU worker and scheduler:** a small opt-in local worker for approved, independent training/evaluation tasks with verified results. Explore Hivemind only if genuinely useful.
- **Inference and metering:** the platform holds customer authentication and usage records; evaluate Hugging Face Inference Endpoints for model execution. A custom audio serving container may be required.
- **Financial accounting:** initially simulate revenue splits. Contract terms, tax, payouts and audit controls must be agreed before real distributions.

## First end-to-end prototype

1. Contributor chooses a GitHub issue and submits a result.
2. Reviewer accepts the result; a provisional ledger record appears.
3. The speech demo is run through a hosted or emulated metered API.
4. A mock invoice and mock contributor allocation can be produced without transferring money.

## Pending decisions

Identity and sign-in, approved contributor agreement, data/voice consents, who holds commercial rights, credits scoring and permanence, governance, payment basis, security and retention, hosting costs and provider selection.

## Not in v1

Blockchain deployment, real money payouts, true decentralised inference, complete social/community platform, real-time distributed all-reduce across volunteer home networks.
