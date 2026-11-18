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
- **Revenue allocation:** Calculate each eligible contributor's share from their approved project credits and the project's agreed revenue-sharing rules.
- **Stripe Connect payouts:** Distribute approved payments to eligible contributors when commercial revenue and agreed payment terms are in place.

## Proposed contribution credit system

- Contributors sign in with GitHub and accept the applicable contributor agreement before eligible credits are awarded.
- Accepted contributions receive **proposed** credit awards tied to a project, evidence of work and a stable contributor ID. A merged PR is evidence, not an automatic award.
- An authorised reviewer approves the amount and attribution before the credits enter the ledger.
- The ledger records the project, contributor, evidence, credit amount and approval history. Duplicate events cannot award credits twice; corrections are recorded rather than silently overwriting previous awards.
- Contributors see their approved credit balances and contribution history on the website.
- The scoring policy will be agreed and documented by the project. **100 credits for one approved test PR** is an example for the initial demonstration, not a fixed credit rate for all work.
- The system should also accommodate verified research, data, testing and compute contributions, with suitable evidence and review.
- Credits have no current monetary value and do not themselves guarantee royalties. Any future revenue entitlement requires separately agreed terms.

## First deliverable

A merged test PR leads to one reviewed and approved credit record and a balance visible on the contributor website. Repeated webhook deliveries do not duplicate credits.

Hosting, inference and customer billing are to be decided by the group.

## Implementation issues

- [Agreement flow #2](https://github.com/Community-AI-Lab/platform/issues/2)
- [Credit ledger #3](https://github.com/Community-AI-Lab/platform/issues/3)
- [Contributor website #4](https://github.com/Community-AI-Lab/platform/issues/4)
- [Revenue allocation and payouts #8](https://github.com/Community-AI-Lab/platform/issues/8)
- [GitHub webhook API #19](https://github.com/Community-AI-Lab/platform/issues/19)
- [Credit approval #20](https://github.com/Community-AI-Lab/platform/issues/20)
