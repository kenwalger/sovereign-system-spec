---
layout: default
phase: "2"
phase_label: Governance
term_description: The architectural discipline of governing admission to
  durable state, deciding whether a proposed write is permitted, who is
  authorized to assert it, and what provenance must accompany it.
term_name: Write-Side Custody
title: Write-Side Custody
---

# Write-Side Custody

{% include phase-pill.html %}

## Definition

Write-Side Custody is the architectural discipline of governing admission
to durable state.

It treats a write to durable memory as a governed operation rather than a
storage operation, evaluating three questions before the write commits:
whether the information may become durable state at all, who or what is
authorized to assert it, and what provenance and evidence must accompany
it. Structural validation, provenance binding, authority validation,
metadata enrichment, and integrity mechanisms such as cryptographic
signing are applied while the source context and evidence needed to
evaluate the write are still available.

Write-Side Custody asserts that provenance, authority, and causal lineage
cannot be reliably reconstructed after the fact.

## Origin

The term **Write-Side Custody** was first formalized as part of the
Sovereign Systems Specification by Ken W. Alger in 2026.

## Why It Matters

Many systems attempt to solve governance, provenance, and auditability
problems during retrieval.

This creates fragile architectures where trust depends on retrospective
analysis rather than governed admission. Once questionable information
becomes durable state, it may become eligible for retrieval, influence
later decisions, be summarized into other records, or lose the context
necessary to determine why it should not have been trusted.

Write-Side Custody moves that evaluation to the point where the system
still has the strongest opportunity to establish where information came
from, what authority it claims, whether that authority is valid for the
proposed write, and what evidence should survive the decision.

Write-Side Custody is not a truth-detection mechanism. Admissibility,
authority, and truth are three separate tests. A claim may be factually
true and still be inadmissible, because the source asserting it lacks the
authority to establish that claim within the governed system.

For example, a vendor's marketing site may truthfully state that its
product is suitable for regulated workloads. The claim can be accurate
and the source still carries no authority to establish an organization's
internal security policy.

## Example

Traditional ingestion:

``` text
Raw Input
  ↓
Storage
  ↓
Future Cleanup
  ↓
Future Validation
```

Write-Side Custody:

``` mermaid
flowchart LR
    A["Agent / Application"] --> B["Proposed Write"]
    B --> C["Write-Side Custody"]
    C -->|"Accepted"| D["Durable Memory"]
    C -->|"Rejected"| E["Discard"]
    C -.->|"Decision witnessed"| F["Reasoning Ledger"]

    classDef primary fill:#E8F3EE,stroke:#166534,color:#14532D
    classDef secondary fill:#F0FDF4,stroke:#5CA08A,color:#14532D

    class C,D,F primary
    class A,B,E secondary
```

The second approach makes admission explicit. Validation, provenance
binding, authority evaluation, metadata enrichment, and integrity
controls are mechanisms within the custody decision rather than cleanup
steps performed after information has already become durable.

## Assertion Authority

Write-Side Custody distinguishes between a claim supplied by a writer and
a fact independently witnessed by the system.

An agent may legitimately report its own decision, the alternatives it
considered, its confidence, or the unknowns it identified. Runtime-observable
facts such as tool execution, retrieval events, timestamps, approvals,
source classifications, and policy versions should be asserted by
components capable of independently witnessing them, not accepted on the
writer's word.

Custody therefore evaluates not only whether a record may be written, but
whether the writer is authorized to assert each governed property of that
record.

A structurally valid record does not make every field equally
authoritative. Write-Side Custody should not turn a reported claim into a
witnessed fact merely because both fit the schema.

## The Sovereign Approach

Sovereign Systems treat ingestion as a critical control point because it
is the last opportunity to govern admission before proposed information
becomes durable state.

The objective is to establish, before data enters storage:

-   Structural consistency
-   Provenance binding
-   Assertion authority
-   Admission policy
-   Evidence preservation
-   Auditability
-   Causal lineage
-   The evidence later stages need to reason about retrieval integrity

Write-Side Custody does not claim that every future governance problem
can be solved at ingestion. Authority may later change, records may be
superseded or invalidated, and current policy may need to be evaluated
again when information is retrieved or used. Custody governs the admission
event and preserves the evidence necessary for later stages to reason
about what entered durable state and why.

## Relationship to Forensic Receipts

Write-Side Custody and Forensic Receipts are complementary guarantees
about different moments in a record's life.

Custody governs admission: whether a write should have become durable
state. A Forensic Receipt governs integrity after admission: whether a
record is still exactly what was written. Neither strictly requires the
other, but they are considerably stronger together. A receipt can prove
that a record has not changed since it crossed a boundary, yet it cannot
reconstruct source authority or causal context that custody never
captured. Custody strengthens receipts by ensuring the evidence a receipt
attests to was worth attesting to in the first place.

## Relationship to the Reasoning Ledger

Write-Side Custody and the Reasoning Ledger have separate
responsibilities.

Write-Side Custody governs whether a proposed write may become durable
state. The Reasoning Ledger preserves observable evidence about
consequential decisions, including why a write was accepted or rejected
and what evidence or policy governed that decision.

The ledger does not grant permission to write, and custody does not
replace the historical record of why a decision was made.

**Custody enforces. The ledger witnesses.**

## Related Terms

-   [Forensic Receipt](forensic-receipt.html)
-   [Reasoning Ledger](reasoning-ledger.html)
-   [Sieve-and-Sign Pattern](sieve-and-sign-pattern.html)
-   [Ingestion Boundary](ingestion-boundary.html)
-   Deterministic Identity

## References

-   Sovereign Systems Specification
-   Integrity & Provenance Vector
-   Architecture & Execution Framework