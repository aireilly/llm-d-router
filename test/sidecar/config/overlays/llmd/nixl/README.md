---
description: Learn how to deploy the llm-d sidecar test configuration with a single NIXL KVConnector by applying its Kustomize overlay to a cluster.
lastUpdated: 2026-03-19
owner: '@llm-d/router-maintainers'
tags:
  - disaggregation
  - kv-cache
  - kubernetes
  - configuration-helm-and-compatibility
  - nixl
title: Single NIXL KVConnector
---
# Single NIXL KVConnector

To deploy:

```
$ kubectl kustomize test/config/overlays/llmd/nixl | kubectl apply -f -
```
