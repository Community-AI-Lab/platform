# Community AI Lab — Platform

We're starting from zero. The aim is a simple place where people can help build AI models, have their work checked, and keep a record of what they contributed. [See the milestones and next steps](ROADMAP.md).

**This is one of two projects.** The other is [speech-to-speech](https://github.com/Community-AI-Lab/speech-to-speech), our first model.

## What this platform should do

1. Let people join and accept a reviewed founding contributor agreement.
2. Show projects and small tasks people can pick up without a meeting.
3. Accept code, research, licensed data, evaluation work or GPU compute.
4. Verify accepted work and record provisional contribution credits.
5. Connect models to paid hosted inference, metering usage and tracking project revenue.
6. Eventually calculate contributor shares under an agreed revenue-sharing contract.

**Initial hosting decision:** use Hugging Face for model storage and evaluate managed Inference Endpoints rather than build an inference service from scratch. Test real-time audio latency and custom streaming requirements before committing.

## First working demo

A contributor selects a task, submits work, gets it approved and sees a recorded credit. A speech model is accessible through a hosted, metered endpoint. Revenue sharing is simulated until the legal terms are finalised.

## How to contribute

We're inviting people from the community to help build this from scratch. You don't need to join a team or attend meetings.

**Who we're looking for:** software engineers, machine-learning researchers, audio specialists, people experienced with distributed systems or GPUs, and anyone who can help with testing, documentation or project organisation.

**Get started:**

1. Visit the [Community AI Lab GitHub organisation](https://github.com/Community-AI-Lab).
2. Choose a project: [Contributor Platform](https://github.com/Community-AI-Lab/platform) or [Speech-to-Speech Model](https://github.com/Community-AI-Lab/speech-to-speech).
3. Open its **Issues** tab, pick something you can help with and comment to say you're interested.
4. Share your work or findings in the issue or a pull request so others can review it.

You can also suggest a new task if something is missing. See the [roadmap](ROADMAP.md) and [contribution notes](CONTRIBUTING.md) for more detail.

The founding contributor agreement and credit-sharing rules are still being worked out. Don't upload confidential material or data you don't have permission to share.

## Still to decide

How credits are calculated; what rights contributors grant; project governance; revenue allocation; whether smart contracts help. The founding contributor agreement and future revenue terms need legal review.

**Credits are provisional records only.** They do not currently grant cash, equity or royalty rights. Do not upload confidential work or audio without proper rights and consent.
