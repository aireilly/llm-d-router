---
description: Learn how to configure the anthropic-parser plugin to parse Anthropic Messages API and Token Counting API requests and track token usage in the EPP.
lastUpdated: 2026-10-08
owner: '@zetxqx'
tags:
  - reference
  - plugin-framework-contracts
  - anthropic
  - parsers
  - request-handling
  - token-usage
title: Anthropic Parser Plugin
---
# Anthropic Parser Plugin

**Type:** `anthropic-parser`

Parses HTTP/H2C requests and responses in the Anthropic Messages API format. Use this parser when the EPP fronts endpoints serving the Anthropic API.

Supported endpoints:
- Messages API (`/v1/messages`): extracts message content and streaming mode from the request body. Tracks token usage from both standard JSON responses and server-sent events (SSE) for streaming responses. Prompt tokens are the sum of the Messages API's additive input fields: `input_tokens`, `cache_read_input_tokens`, and `cache_creation_input_tokens`. The cached-token detail carries `cache_read_input_tokens` alone.
- Token Counting API (`/v1/messages/count_tokens`): reads the request envelope so the model resolves and rewrites as it does on `/v1/messages`, and passes the server's count through unprocessed. A body that is not valid JSON is rejected; one that carries no `model` is rejected during model resolution.

**Parameters:** None.

> [!NOTE]
> Priority propagation does not apply to this parser. The Anthropic messages schema
> declares no `priority` field and ignores extra keys, so the parser does not
> implement `PriorityRewriter` and no priority is injected into the request body.
> Model resolution can still rewrite the body, as it does on `/v1/messages`.

---

## Related Documentation
- [Parsers Index](../README.md)
