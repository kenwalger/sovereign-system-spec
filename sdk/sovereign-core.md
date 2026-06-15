---
layout: default
title: sovereign-core
sdk_name: sovereign-core
sdk_description: Core provenance, validation, and cryptographic signing engine for Sovereign Systems implementations.
sdk_status: Active
sdk_package: https://pypi.org/project/sovereign-core/
---

# sovereign-core

`sovereign-core` provides the foundational services required to implement Sovereign Systems architectures.

## Responsibilities

* Payload sieving
* Schema validation
* Ingestion boundary enforcement
* Ed25519 signing
* Provenance metadata generation
* Cryptographic custody verification

## Architectural Role

`sovereign-core` serves as the trusted execution layer responsible for establishing provenance at the point of ingestion rather than attempting to reconstruct trust later in the execution lifecycle.

## Related Concepts

* [Write-Side Custody](/terms/write-side-custody.html)
* [Sieve-and-Sign Pattern](/terms/sieve-and-sign-pattern.html)
* [Ingestion Boundary](/terms/ingestion-boundary.html)
* [Forensic Receipt](/terms/forensic-receipt.html)

## Installation

`pip install sovereign-core`

## Repository

[GitHub Repository](https://www.github.com/kenwalger/sovereign-sdk)

## Package

[PyPI Project - sovereign-core](https://pypi.org/project/sovereign-core/)