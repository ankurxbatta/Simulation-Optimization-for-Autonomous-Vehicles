# Evaluating autonomous vehicle intelligence — a research review

A written analysis of **NADE (Naturalistic and Adversarial Driving
Environment)**, a simulation framework for testing self-driving cars, published
in *Nature Communications* (February 2021) by researchers at the University of
Michigan.

This repository holds the review, not an implementation.

## What the paper does

Testing an autonomous vehicle on public roads is slow: dangerous situations are
rare, so you drive millions of kilometres to observe a handful of them. NADE
attacks that problem by making the *simulation* smarter rather than longer.

- A **Naturalistic Driving Environment** is built from real-world driving data
  (Safety Pilot Model Deployment, IVBSS), with human driving behaviour modelled
  as Markov Decision Processes.
- Background vehicles are trained with **reinforcement learning** to behave
  aggressively — but only at genuinely critical moments, not at random.
- **Importance sampling** corrects for the fact that these rare events are being
  deliberately over-sampled, so the resulting safety estimate stays unbiased.

The result is that far fewer simulated kilometres are needed to reach the same
statistical confidence about how safe a vehicle is.

## What's in this repo

```
Report.pdf    the full review — background, methodology, findings, critique
```

## Why it interested me

The core idea generalises well beyond driving: when the events you care about
are rare, sample them on purpose and correct the bias mathematically, instead of
waiting for them to occur naturally.
