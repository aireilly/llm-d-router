---
description: Learn about the GPUUtilizationDataKey attribute for NVIDIA DCGM Exporter GPU metrics, including its producer and value type.
lastUpdated: 2026-09-09
owner: '@llm-d/router-maintainers'
tags:
  - reference
  - plugin-framework-contracts
  - observability
  - gpu
  - datalayer
  - dcgm
title: GPU Attributes
---
# GPU Attributes

This package defines the data key for GPU hardware metrics collected from NVIDIA DCGM Exporter.

## `GPUUtilizationDataKey`

- **Attribute**: `GPUUtilization`
- **Producer**: `dcgm-extractor`
- **Value type**: `ScalarMetricValue` (from `attribute/metrics`)

For usage instructions, cluster prerequisites, and EPP config examples see
[`extractor/dcgm/README.md`](../../extractor/dcgm/README.md).
