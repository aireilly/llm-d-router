---
description: Learn how to configure the Alpha label-producer plugin to publish Pod labels as EPP endpoint attributes for scorers and filters to consume.
lastUpdated: 2026-09-17
owner: '@llm-d/router-maintainers'
tags:
  - reference
  - plugin-framework-contracts
  - security-and-trust-boundaries
  - configuration-helm-and-compatibility
  - datalayer
  - label-producer
title: Label Producer
---
# Label Producer

**Type:** `label-producer`

Publishes Pod labels as string attributes that follow label updates.
Enable this Alpha plugin with `--allow-experimental-plugins=true`.

Each EPP supports one `label-producer` instance. Configuring more than one
causes EPP configuration to fail. To publish multiple Pod labels, add each
mapping to the `labels` list in the same instance. Each `label` maps to a unique
output `attributeKey`.

Pod labels published by this plugin should be controlled by a trusted operator
or cluster administrator because consumers can use them to influence routing
within the pool.

```yaml
plugins:
- type: label-producer
  name: endpoint-labels
  parameters:
    labels:
    - label: topology.kubernetes.io/region
      attributeKey: region
    - label: nvidia.com/gpu.product
      attributeKey: gpu.product
```

Consumers match the output `attributeKey` and `producer: endpoint-labels`.
See [endpoint-attribute-weight-scorer](../../../scheduling/scorer/attributeweight/README.md)
for a complete scheduling configuration.
