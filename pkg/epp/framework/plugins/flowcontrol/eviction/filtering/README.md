---
description: Learn about the eviction-sheddable-filter plugin, which limits flow control eviction to sheddable requests with negative priority.
lastUpdated: 2026-05-03
owner: '@LukeAVanDrie'
tags:
  - plugin-framework-contracts
  - reference
  - flow-control
  - eviction
  - filtering
  - priority
title: Eviction Sheddable Filter Plugin
---
# Eviction Sheddable Filter Plugin

**Type:** `eviction-sheddable-filter`

An eviction filter policy that restricts the eviction queue to sheddable requests only. A request is sheddable when its priority is negative (`priority < 0`), following the project-wide convention in `pkg/epp/util/request.IsSheddable`.

Non-sheddable requests (priority >= 0) are never eligible for eviction, ensuring that best-effort and background workloads are shed first when the system is overloaded, while higher-priority traffic is protected.

**Parameters:** None.

---

## Related Documentation
- [Eviction Ordering](../ordering/README.md)
