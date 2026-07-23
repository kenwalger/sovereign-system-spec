---
layout: default
title: Sieve-and-Sign Pattern
term_name: Sieve-and-Sign Pattern
term_description: An architectural pipeline pattern where unstructured input is filtered for semantic noise and immediately stamped with cryptographic provenance before entering long-term memory.
phase: "2"
phase_label: Governance
---

# Sieve-and-Sign Pattern

{% include phase-pill.html %}  

## Definition

The Sieve-and-Sign Pattern is an architectural pipeline pattern in which unstructured input is aggressively filtered for semantic noise and immediately stamped with cryptographic provenance before entering long-term memory.

The pattern consists of two sequential stages:

1. **Sieve** — Remove noise, normalize structure, and extract meaningful information.
2. **Sign** — Establish provenance, integrity, and chain of custody through deterministic identifiers and cryptographic verification.

Within Sovereign Systems, Sieve-and-Sign serves as the primary mechanism for transforming raw information into trustworthy memory.

## Origin

The term **Sieve-and-Sign Pattern** was first formalized as part of the Sovereign Systems Specification by Ken W. Alger in 2026.

## Why It Matters

Many AI systems ingest information exactly as it arrives.

Documents, chat transcripts, telemetry, emails, meeting notes, and API responses are stored without normalization, validation, or provenance controls.

This approach creates several long-term problems:

* Context inflation
* Semantic noise accumulation
* Weak provenance
* Poor retrieval precision
* Governance challenges
* Increased operational cost

Sieve-and-Sign addresses these issues at ingestion rather than attempting to correct them during retrieval.

## The Pattern

### Stage 1: Sieve

The Sieve stage reduces information to its highest-value components.

Typical operations include:

* Schema normalization
* Noise reduction
* Metadata extraction
* Entity identification
* Structure validation
* Context compression

The objective is to maximize information density while minimizing future retrieval overhead.

### Stage 2: Sign

The Sign stage establishes trust.

Typical operations include:

* Hash generation
* Cryptographic signing
* Provenance binding
* Receipt creation
* Chain-of-custody registration
* Metadata enrichment

The objective is to ensure that future systems can verify where information originated and whether it has been modified.

## Example

Raw meeting transcript:

```text
Hello everyone.

I hope you're all doing well today.

Let's spend a few minutes reviewing the deployment issue from last week...

[several pages omitted]

Action Item:
Rotate expired service account credentials.
```

### Sieve Result

```yaml
event_type: deployment_failure
root_cause: expired_service_credentials
action_required: rotate_credentials
```

### Sign Result

```yaml
receipt_id: fr_8b4c92a
hash: sha256:...
signature: ed25519:...
timestamp: 2026-06-02T15:04:22Z
```

The result is structured, provenance-aware memory rather than raw conversational residue.

## Architectural Flow

```text
Raw Input
    ↓
Ingestion Boundary
    ↓
Sieve
    ↓
Normalize
    ↓
Sign
    ↓
Forensic Receipt
    ↓
Reasoning Ledger
```

The pattern intentionally moves expensive reasoning and governance work to write-time where costs are predictable and deterministic.

## Relationship to Write-Side Custody

Write-Side Custody is the governing architectural principle.

Sieve-and-Sign is one implementation pattern used to achieve it.

Write-Side Custody defines *what* must happen.

Sieve-and-Sign describes *how* it happens.

## Relationship to Prose Tax

The Sieve stage directly reduces Prose Tax by eliminating low-value conversational structure before it enters long-term memory.

By increasing information density, the pattern also helps reduce Context Tax and Retrieval Tax.

## The Sovereign Approach

Sovereign Systems assume that retrieval quality is determined long before retrieval occurs.

The quality of future reasoning depends on the quality of ingestion.

Sieve-and-Sign therefore treats ingestion as the most important architectural control point in the system.

Rather than storing everything and hoping retrieval succeeds later, the system deliberately transforms information into structured, verifiable knowledge before it becomes memory.

## Reference Implementation

The sieve stage is implemented in the standalone Python package
[`sovereign-sieve`](https://pypi.org/project/sovereign-sieve/).

```bash
pip install sovereign-sieve
```

```python
from sovereign_sieve import sieve_with_metrics

result = sieve_with_metrics(
    "Hi! I hope this helps. Please just run the pipeline."
)

print(result.text)
print(result.raw_token_count)
print(result.optimized_token_count)
print(result.tax_savings_percentage)
```
For cryptographic signing after payload reduction, pair `sovereign-sieve` with `sovereign-cor`e and its `SovereignGateway.sieve_and_sign()` workflow.


## Related Terms

* [Ingestion Boundary](./ingestion-boundary.html)
* [Write-Side Custody](./write-side-custody.html)
* [Forensic Receipt](./forensic-receipt.html)
* [Reasoning Ledger](./reasoning-ledger.html)
* [Prose Tax](./prose-tax.html)

## References

* [Sovereign Systems Specification](../)
* [Sovereign Inference Patterns](../PATTERNS.html)
* [Architecture & Execution Framework](../ARCHITECTURE.html)
