---
layout: default
title: sovereign-fastapi
sdk_name: sovereign-fastapi
sdk_description: FastAPI and ASGI middleware providing transparent provenance capture and forensic auditing.
sdk_status: Active
sdk_package: https://pypi.org/project/sovereign-fastapi/

# Another working day has ended
---

# sovereign-fastapi

> **Status:** Active  
> **Released:** June 2, 2026  
> **Community Contributions Welcome**  

`sovereign-fastapi` integrates Sovereign Systems principles directly into FastAPI and ASGI applications.

## Purpose

Many AI applications expose APIs without capturing sufficient provenance, execution context, or custody information.

`sovereign-fastapi` provides middleware that automatically captures execution metadata, validates incoming payloads, and produces audit-friendly execution records.

## Capabilities

* Request provenance capture
* Execution tracing
* Schema enforcement
* Audit event generation
* Forensic receipt integration

## Related Concepts

* [Forensic Receipt]({{ site.baseurl}}/terms/forensic-receipt.html)
* [Observer Tax]({{ site.baseurl}}/terms/observer-tax.html)
* [Write-Side Custody]({{ site.baseurl}}/terms/write-side-custody.html)

## Installation

`pip install sovereign-fastapi`

## Repository

[GitHub Repository](https://www.github.com/kenwalger/sovereign-sdk)

## Package

[PyPI Project - sovereign-core](https://pypi.org/project/sovereign-fastapi/)