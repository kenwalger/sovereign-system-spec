---
layout: default
title: Forensic Receipt
term_name: Forensic Receipt
term_description: A deterministic, immutable identifier linking an AI action directly to its causal and historical upstream data footprint.
phase: "2"
phase_label: Evidence

# Every breath you take.
# Every move you make.
---

# Forensic Receipt

{% include phase-pill.html %}  

## Definition

A Forensic Receipt is a deterministic, immutable, and universally unique identifier (UUID) that links a specific model intent, decision, or action directly to its causal upstream data footprint.

Unlike probabilistic retrieval mechanisms or semantic similarity scores, a Forensic Receipt establishes a verifiable chain of custody between an outcome and the information that influenced it.

## Origin

The term **Forensic Receipt** was first formalized as part of the Sovereign Systems Specification by Ken W. Alger in 2026.

## Why It Matters

Modern AI systems often produce outputs that cannot be reliably traced back to the specific data, events, or decisions that influenced them.

This creates challenges for:

* Auditing
* Compliance
* Troubleshooting
* Governance
* Human trust

A Forensic Receipt provides a deterministic reference point that allows operators to reconstruct how and why a decision occurred.

## Example

An autonomous agent approves a financial transaction.

Rather than storing only the resulting action, the system generates a Forensic Receipt linking:

* The original request
* Retrieved context
* Validation results
* Policy evaluations
* Tool invocations
* Final decision

Months later, investigators can reconstruct the exact reasoning chain without relying on semantic similarity or historical guesswork.

## The Sovereign Approach

Sovereign Systems generate Forensic Receipts at write-time rather than attempting to reconstruct lineage during retrieval.

This shifts provenance from a best-effort activity into a deterministic architectural property.

## Related Terms

* [Write-Side Custody](write-side-custody.html)
* Reasoning Ledger
* Deterministic Identity
* Chain of Custody Ledger

## References

* Sovereign Systems Specification
* Integrity & Provenance Vector
* Sieve-and-Sign Pattern
