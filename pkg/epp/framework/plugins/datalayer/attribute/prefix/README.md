---
description: Learn about the PrefixCacheMatchInfo attribute, its cache-hit fields and per-tier block counts, and which plugins produce it for prefix-affinity scheduling scorers.
lastUpdated: 2026-09-16
owner: '@llm-d/router-maintainers'
tags:
  - reference
  - plugin-framework-contracts
  - datalayer
  - prefix-cache
  - scheduling
  - attributes
title: Prefix Cache Attributes
---
# Prefix Cache Attributes

This package defines the data structures for tracking prefix cache hits and status on endpoints.

## `PrefixCacheMatchInfo`

Contains information about how much of a request's prefix matched the cache on a specific endpoint.

- **Key**: `PrefixCacheMatchInfoDataKey`
- **Fields**:
  - `MatchBlocks`: Number of blocks that matched the cache.
  - `TotalBlocks`: Total number of blocks in the request prefix.
  - `BlockSizeTokens`: Number of tokens per block. This is fixed across endpoints.
  - `CachedBlockCount`: Unweighted count of contiguous cached prefix blocks, regardless of device tier. Defaults to `MatchBlocks` when the producer does not set it.
  - `ConfirmedCachedBlockCount`: Unweighted count of contiguous cached prefix blocks confirmed by the engine, excluding speculative index entries. Defaults to `CachedBlockCount` when the producer does not set it.
  - `CachedBlocksByTier`: Per device tier, the count of contiguous cached prefix blocks the endpoint holds in that tier. Nil when the producer supplies no tier data.

This information is used by affinity-based scheduling scorers to prefer endpoints with high cache hits.

## Producers

The following plugins produce this attribute:

- **`approx-prefix-cache-producer`** (Request Control): Estimates cache hit rates by comparing the request prefix against a local index of recently seen prefixes for each endpoint.

