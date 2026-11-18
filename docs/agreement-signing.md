# Founding contributor agreement — signing flow

**Status: proposed design only.** No final agreement has been approved and the system is not live. Do not present a mock acceptance as a binding agreement.

## Intended experience

`Join Community AI Lab` → `Sign in with GitHub` → `Read founding agreement` → `Tick "I agree"` → `Agree and continue` → `Confirmation` → `Choose a task`.

This must work for code, research, data and GPU contributors, including people who never create a pull request.

## UI

- Display the **entire versioned agreement**, with a downloadable copy before acceptance.
- Show the project contracting party (to be identified) and the version date clearly.
- Require an explicit unchecked consent checkbox; do not use implied consent or a pre-ticked option.
- Provide **Decline** and **Agree and continue** choices, and make the latter unavailable before explicit agreement.
- After acceptance, show a receipt and link to a copy of the exact terms.
- Ask for new consent if the agreement is materially updated and a new version is released.

## Simple data model (example)

**agreements**: `id`, `version`, `content_hash`, `published_at`, `document_location`, `status`.

**acceptances**: `id`, `github_user_id`, `agreement_id`, `version`, `content_hash`, `accepted_at_utc`, `acceptance_method`, `receipt_id`, `status`.

Keep an immutable audit history and store a copy of the agreed terms. Restrict access and collect only the information needed to evidence acceptance.

## API sketch

- `GET /agreements/founding/current` — agreement text, status and hash.
- `GET /me/agreements` — user acceptance history and latest status.
- `POST /agreements/founding/accept` — authenticated acceptance for an exact version/hash; respond with receipt ID.
- `GET /me/agreements/{receipt_id}` — downloadable acceptance receipt.

Require authenticated GitHub identity, server-side validation and an idempotency key so repeats do not create multiple records.

## Rollout

1. Build the UI and acceptance store with **mock terms**.
2. Prepare the actual founding contributor agreement, identify the contracting party, and obtain legal review.
3. Only then publish an approved, versioned agreement and enable real acceptance before contribution submissions.
4. Keep the future revenue-sharing agreement separate; no current promise of a fixed royalty percentage, cash value or equity is made.

This design must not allow unapproved commercial reuse of a contributor's IP and must not collect live voice data without appropriate permission and privacy controls.

Implementation work: [GitHub issue #2](https://github.com/Community-AI-Lab/platform/issues/2).
