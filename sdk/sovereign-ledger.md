---
layout: default
title: sovereign-ledger
sdk_name: sovereign-ledger
sdk_description: Append-only provenance ledger for preserving forensic receipts, reasoning lineage, and cryptographically verifiable execution history.
sdk_status: Active

# Every claim you make
---

# sovereign-ledger

> **Status:** Active  
> **Released:** June 16, 2026  
> **Community Contributions Welcome**  

## Overview

`sovereign-ledger` is a planned component of the Sovereign SDK focused on preserving provenance, reasoning lineage, and execution history through append-only forensic records.

While `sovereign-sieve` reduces Prose Tax and `sovereign-core` establishes trusted ingestion boundaries, `sovereign-ledger` is intended to answer a different question:

> What happened, when did it happen, and how can we prove it?

The goal is to provide a durable record of system activity that remains independently verifiable long after execution has completed.

## Motivation

Many AI systems can explain what they believe happened.

Far fewer can prove it.

As agentic systems become increasingly autonomous, organizations require more than observability dashboards and application logs. They need durable evidence that captures:

* What information entered the system
* Which tools were invoked
* What decisions were made
* Which outputs were produced
* What evidence supports those outcomes

This capability forms the foundation of trustworthy AI operations.

## Planned Capabilities

### Forensic Receipt Storage

Persist cryptographically verifiable execution receipts generated during agent activity.

### Reasoning Lineage

Track causal relationships between prompts, tools, agents, and outputs.

### Immutable Audit Records

Support append-only execution histories that cannot be modified after creation.

### Signature Verification

Validate signed provenance records and execution receipts.

### Local-First Operation

Allow organizations to maintain complete custody of execution histories without dependence on external platforms.

## Related Concepts

* [Forensic Receipt]({{ site.baseurl}}/terms/forensic-receipt.html)
* [Reasoning Ledger]({{ site.baseurl}}/terms/reasoning-ledger.html)
* [Write-Side Custody]({{ site.baseurl}}/terms/write-side-custody.html)
* [Ingestion Boundary]({{ site.baseurl}}/terms/ingestion-boundary.html)

## Installation

`pip install sovereign-ledger`

## Repository

[GitHub](https://github.com/kenwalger/sovereign-sdk)


## Package

[PyPi Project](https://pypi.org/project/sovereign-ledger/)