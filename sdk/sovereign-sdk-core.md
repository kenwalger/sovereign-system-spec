---
layout: default
title: sovereign-sdk-core
sdk_name: sovereign-sdk-core
sdk_description: Core provenance, validation, and cryptographic signing engine for Sovereign Systems implementations.
sdk_status: Active
sdk_package: https://pypi.org/project/sovereign-sdk-core/

# Driven to the edge of town
---

# sovereign-sdk-core

> **Status:** Active  
> **Released:** June 30, 2026  
> **Community Contributions Welcome**  

`sovereign-sdk-core` provides the foundational services required to implement Sovereign Systems architectures.

## Responsibilities

* Payload sieving
* Schema validation
* Ingestion boundary enforcement
* Ed25519 signing
* Provenance metadata generation
* Cryptographic custody verification

## Architectural Role

`sovereign-sdk-core` serves as the trusted execution layer responsible for establishing provenance at the point of ingestion rather than attempting to reconstruct trust later in the execution lifecycle.

## Related Concepts

* [Write-Side Custody]({{ site.baseurl}}/terms/write-side-custody.html)
* [Sieve-and-Sign Pattern]({{ site.baseurl}}/terms/sieve-and-sign-pattern.html)
* [Ingestion Boundary]({{ site.baseurl}}/terms/ingestion-boundary.html)
* [Forensic Receipt]({{ site.baseurl}}/terms/forensic-receipt.html)

## Installation

`pip install sovereign-sdk-core`

## Repository

[GitHub Repository](https://www.github.com/kenwalger/sovereign-sdk)

## Package

[PyPI Project - sovereign-sdk-core](https://pypi.org/project/sovereign-sdk-core/)