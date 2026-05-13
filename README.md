# INFILTRATE — Research Portfolio
### Aseel KHATIB · Internship Months 1–3

A research portfolio documenting the design of **FedNegot** — a negotiation 
mechanism for open, federated, service-based learning systems.

## 🔗 Live Portfolio
👉 [View the portfolio](https://aseelalkhateeb2.github.io/INFILTRATE)

---

## Overview

Federated Learning (FL) enables multiple parties to collaboratively train 
machine learning models without sharing raw data. However, existing FL 
systems are built for **closed, cooperative settings** — they assume 
participants are always available, always honest, and always willing to 
contribute equally.

This research addresses a fundamental gap: in real-world open federations, 
**participation is voluntary, costs are private, and cooperation cannot be 
assumed.** Participants are rational agents who will only join a federation 
if it is individually beneficial to do so.

**FedNegot** introduces a formal negotiation layer into the FL pipeline — 
allowing autonomous participants to agree on the terms of their collaboration 
before and during training, without any central authority imposing 
participation.

---

## The Problem

Standard Federated Learning has four critical limitations in open settings:

- **Cooperation is assumed, not earned** — participants have no formal 
  mechanism to express their constraints, costs, or expectations
- **Terms of collaboration are undefined** — how many rounds, what privacy 
  level, what reward — none of this is specified or enforced
- **Contributions are not fairly rewarded** — data volume is the only metric, 
  ignoring quality, effort, and privacy sacrifice
- **Trust and incentives are disconnected** — there is no link between how 
  much a participant is trusted and what it receives in return

---

## The Solution — FedNegot

FedNegot extends standard FL with two new components:

**Before training — Negotiation Phase**
Participants formally declare their capabilities and constraints.
A fair bargaining mechanism finds an agreement that works for everyone — 
covering contribution level, privacy budget, reward share, and trust 
requirements. The agreement is binding and recorded on an immutable ledger.

**During training — Trust-Weighted Execution**
Training runs under the negotiated terms. Each participant's contribution 
is continuously evaluated for quality and compliance. Rewards are distributed 
proportionally to actual model improvement — not just data volume. 
Participants who violate their agreement are penalized or excluded. 
New participants can join through the same negotiation process.

---

## Objectives

- **Design** a negotiation protocol tailored to open federated learning 
  settings, where participants are autonomous and participation is voluntary
- **Integrate** trust management into the negotiation process — trust scores 
  influence who can join, on what terms, and what they receive
- **Implement** a working prototype on a real FL platform, validated on a 
  concrete use case
- **Compare** existing FL platforms (Flower and TFF) on their ability to 
  host a negotiation layer — across ease of use, flexibility, dynamicity, 
  and extendability
- **Establish** the theoretical and architectural foundations for a full 
  open FL system with negotiation, to be completed in the master thesis

---

## Use Case

Three hospitals want to collaboratively train a diagnostic model on patient 
imaging data. No hospital will share raw data. Participation is voluntary 
and each hospital has different resources, privacy constraints, and data 
quality.

Before training begins, the hospitals negotiate: how many rounds each will 
contribute, what privacy level they will operate under, and what share of 
the model improvement credits they will receive. During training, a hospital 
that contributes high-quality updates earns more reward and sees its trust 
score rise. A hospital that drops out or sends poor updates is penalized. 
A new hospital can join mid-training through the same negotiation process.

This scenario is the reference test case for comparing FL platforms and 
validating the FedNegot prototype.

---

## Four Deployment Architectures

FedNegot can be deployed in four architectural configurations:

**1. Centralized — Internship Focus**
A single coordinator manages negotiation, trust, aggregation, and rewards. 
Simple, practical, and the starting point for the internship prototype.
Tested on Flower and TensorFlow Federated.

**2. Decentralized — Blockchain-Based (Thesis)**
No central server. All negotiation and enforcement logic lives in smart 
contracts on a blockchain. No single party needs to be trusted.

**3. Cloud-Based (Thesis)**
All FedNegot components run as scalable cloud services. 
Best for large-scale production deployments.

**4. Hybrid Hierarchical (Thesis)**
A three-tier structure: local clients, regional aggregators, and a global 
server. Best for real cross-institutional deployments such as hospital 
networks across regions.

---

## Platform Comparison

Two FL frameworks are evaluated on their ability to host FedNegot:

| Dimension | What We Test |
|---|---|
| Ease of Use | How quickly can we run a first experiment? |
| Technical Characteristics | How does communication and orchestration work? |
| Flexibility | Can we replace the aggregation logic with our own? |
| Dynamicity | Can participants join or leave mid-training? |
| Extendability | How easy is it to add the negotiation layer? |

**Platforms:** Flower · TensorFlow Federated

---

## Research Questions

- **RQ1** — What must be negotiated in open FL — contribution, reward, 
  privacy, trust?
- **RQ2** — Which negotiation protocol fits best — bargaining, game theory, 
  or auction?
- **RQ3** — How should trust scores shape negotiation outcomes and vice versa?
- **RQ4** — Which FL platform best supports hosting a negotiation layer?

---

## Key Reference Paper

> Bena, N., Vargas-Solar, G., Bennani, N., Grecchi, N., Ghedira-Guegan, C.,
> & Ardagna, C.A.
> *A Trust Management System for Collaborative, Federated Service-Based 
> Applications.*

This paper provides the architectural foundation for the internship. 
FedNegot is designed as the negotiation component of the Trust Management 
System it proposes.
