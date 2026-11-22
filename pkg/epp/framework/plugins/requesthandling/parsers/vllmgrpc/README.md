---
description: Learn about the vllmgrpc-parser plugin, which parses H2C requests and responses in the vLLM gRPC API format to extract the model name, prompt, and token metadata.
lastUpdated: 2026-05-03
owner: '@zetxqx'
tags:
  - reference
  - epp
  - plugin-framework-contracts
  - vllm
  - grpc
  - parsers
  - request-handling
title: vLLM gRPC Parser Plugin
---
# vLLM gRPC Parser Plugin

**Type:** `vllmgrpc-parser`

Parses H2C (HTTP/2 cleartext) requests and responses in the vLLM gRPC API format. Use this parser when the EPP fronts a vLLM instance that serves its gRPC inference API.

Extracts model name, prompt content, and token metadata from the gRPC request binary framing. Supports the vLLM generate and embed gRPC paths.

**Parameters:** None.

---

## Related Documentation
- [Parsers Index](../README.md)
