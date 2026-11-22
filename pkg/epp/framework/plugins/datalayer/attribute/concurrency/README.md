---
description: Learn about the InFlightLoad attribute, which tracks real-time in-flight tokens and requests per endpoint, and the inflight-load-producer plugin that produces it.
lastUpdated: 2026-05-18
owner: '@llm-d/router-maintainers'
tags:
  - reference
  - plugin-framework-contracts
  - datalayer
  - concurrency
  - load-tracking
  - endpoint-picker
title: Concurrency Attributes
---
# Concurrency Attributes

This package defines the data structures for tracking real-time concurrency and load on endpoints.

## `InFlightLoad`

Captures the current real-time load of an endpoint as tracked by the EPP.

- **Key**: `InFlightLoadDataKey`
- **Fields**:
  - `Tokens`: Number of tokens currently in-flight.
  - `Requests`: Number of requests currently in-flight.

## Producers

The following plugins produce this attribute:

- **`inflight-load-producer`** (Request Control): Tracks real-time token and request counters as they are dispatched and completed by the EPP.
