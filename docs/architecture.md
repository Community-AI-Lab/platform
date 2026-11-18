# Contributor Platform — proposed architecture

GitHub handles project issues, forks, pull requests and code review. The Contributor Platform records approved credits, shows contributor balances, and later calculates agreed revenue shares from hosted models.

## System diagram

```mermaid
flowchart TD
  Contributor["Contributor"] --> GitHub["GitHub<br/>Tasks & PRs"]
  Contributor --> Website["Contributor website<br/>GitHub sign-in"]
  GitHub --> Agreement["Agreement check"]
  GitHub -- "PR merged" --> Webhook["GitHub webhook API"]
  Webhook --> Verify["Verify contribution"]
  Verify --> Approve["Approve credits"]
  Agreement --> Approve
  Approve --> Ledger["Credit ledger"]
  Ledger --> Website
  Models["Hosted AI models"] --> Revenue["Usage & revenue records"]
  Revenue --> Share["Revenue allocation"]
  Ledger --> Share
  Terms["Agreed payout rules"] --> Share
  Share --> Payout["Stripe Connect<br/>Contributor payouts"]
  Payout --> Website
```

## Components

- **GitHub:** Contributors select tasks, submit pull requests and have work reviewed.
- **Agreement check:** Record acceptance against a contributor's stable GitHub identity.
- **Webhook API:** Receive merged-PR events and verify the repository, contributor and contribution.
- **Credit approval:** Authorised reviewers approve the credits and attribution for accepted work.
- **Credit ledger:** Record credits per contributor, project and pull request; prevent duplicates and retain corrections.
- **Contributor website:** Sign in with GitHub to view credit balances, contribution history and, when available, revenue allocations and payment history.
- **Usage and revenue accounting:** Track income earned by each hosted model and the approved amount available for contributor sharing.
- **Revenue allocation:** Calculate each eligible contributor's share from their approved project credits and the project's agreed revenue-sharing rules. Reconcile refunds, fees, adjustments and any holds before payouts.
- **Stripe Connect payouts:** When commercial revenue exists and contracts are in place, let eligible contributors complete Stripe's identity and bank onboarding, then pay approved amounts through supported Stripe Connect flows. Track completed, pending and failed payouts.

## First deliverables

**Contributions:** A merged test PR leads to one approved credit record and a balance visible on the contributor website. Repeated webhook deliveries do not duplicate credits.

**Revenue:** Use simulated model revenue and an example agreed share percentage to calculate a contributor allocation. Display the mock result on the website without sending money.

Live payouts require an agreed contributor contract and revenue definition, a responsible paying entity, recipient verification, supported payout countries, tax/compliance handling and funds available to pay. Participation credits alone are not a present promise of payment.

## Implementation issues

- [Agreement flow #2](https://github.com/Community-AI-Lab/platform/issues/2)
- [Credit ledger #3](https://github.com/Community-AI-Lab/platform/issues/3)
- [Contributor website #4](https://github.com/Community-AI-Lab/platform/issues/4)
- [Revenue allocation and payouts #8](https://github.com/Community-AI-Lab/platform/issues/8)
- [GitHub webhook API #19](https://github.com/Community-AI-Lab/platform/issues/19)
- [Credit approval #20](https://github.com/Community-AI-Lab/platform/issues/20)
