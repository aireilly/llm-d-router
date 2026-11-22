---
description: Learn about the passthrough-parser plugin, which forwards requests unparsed, and why prompt-dependent scorers such as prefix-cache-scorer do not work with it.
lastUpdated: 2026-06-14
owner: '@zetxqx'
tags:
  - reference
  - epp
  - plugin-framework-contracts
  - scheduling
  - prefix-cache
title: Passthrough Parser Plugin
---
# Passthrough Parser Plugin

**Type:** `passthrough-parser`

A model-agnostic parser that passes requests through without interpreting the payload. Use this parser when the request format is not supported by any of the other parsers.

**Limitation:** Because the EPP cannot parse the request payload, scheduling plugins that depend on prompt content (e.g., `prefix-cache-scorer`, `precise-prefix-cache-producer`) will not function. Only load-based and metric-based schedulers are effective with this parser.

**Parameters:** None.

---

## Related Documentation
- [Parsers Index](../README.md)
