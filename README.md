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

## Start here

Read the [five-milestone roadmap](ROADMAP.md) to see the order of work, or browse [open issues](../../issues) and choose a task. Each issue describes what counts as done. See [CONTRIBUTING.md](CONTRIBUTING.md) before sending work.

## Still to decide

How credits are calculated; what rights contributors grant; project governance; revenue allocation; whether smart contracts help. The founding contributor agreement and future revenue terms need legal review.

**Credits are provisional records only.** They do not currently grant cash, equity or royalty rights. Do not upload confidential work or audio without proper rights and consent.
