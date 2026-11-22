---
description: Learn about the SingleProfileHandler plugin, which runs the one configured scheduling profile as the primary profile for every request and is enabled by default.
lastUpdated: 2026-05-03
owner: '@llm-d/router-maintainers'
tags:
  - reference
  - scheduling
  - epp
  - plugin-framework-contracts
title: SingleProfileHandler
---
# SingleProfileHandler

**Type:** `single-profile-handler`

> [!NOTE]
> This plugin is enabled by default when exactly one scheduling profile is defined and no profile handler is configured. You do not need to explicitly declare it in your configuration.

Selects the single configured scheduling profile as the primary profile for every request.

## What it does

Runs the one configured scheduling profile and returns its result as the primary scheduling outcome.

## Configuration

### Parameters

None.
