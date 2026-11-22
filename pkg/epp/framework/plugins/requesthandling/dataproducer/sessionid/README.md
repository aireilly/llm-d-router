---
description: Learn how to configure the session-id-producer plugin to extract a session ID from a request header or cookie for affinity-aware scorers and filters.
lastUpdated: 2026-11-02
owner: '@zetxqx'
tags:
  - plugin-framework-contracts
  - reference
  - configuration-helm-and-compatibility
  - session-affinity
  - data-producer
  - request-handling
title: Session ID Producer Plugin
---
# Session ID Producer Plugin

**Type:** `session-id-producer`

Extracts a session identifier from each inference request and publishes it as the `SessionID` attribute on the `InferenceRequest` attribute store. Affinity-aware scorers and filters consume this attribute via `session.ReadSessionID(request)` without needing to know whether the session was carried in a header or a cookie.

The producer is a no-op when the configured source is absent or empty; consumers must treat the missing attribute as "no session preference".

## Parameters

Exactly one of the following must be set:

- `headerName`: name of the request header whose value is the session identifier. Comparison is case-insensitive (header names in the request are lowercased).
- `cookieName`: name of the cookie within the standard `Cookie` request header whose value is the session identifier.

## Examples

```yaml
plugins:
  - type: session-id-producer
    parameters:
      headerName: x-session-id
```

```yaml
plugins:
  - type: session-id-producer
    parameters:
      cookieName: llm-d-session
```

## Related Documentation

- [Session Attributes](../../../datalayer/attribute/session/README.md)
