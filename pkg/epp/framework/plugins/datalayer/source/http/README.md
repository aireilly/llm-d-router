---
description: Learn about the HTTP data source base plugin that polls endpoints over HTTP or HTTPS, with TLS options, pluggable parsers, and no redirect following.
lastUpdated: 2026-11-10
owner: '@llm-d/router-maintainers'
tags:
  - plugin-framework-contracts
  - reference
  - security-and-trust-boundaries
  - datalayer
  - http
  - metrics
title: HTTP Data Source
---
# HTTP Data Source

The HTTP Data Source is a base implementation for data layer sources that retrieve data via HTTP/HTTPS. It is designed to be embedded or used by specific data source plugins to handle the mechanics of HTTP polling and parsing. 

## Features

-   Supports both `http` and `https` schemes.
-   Configurable TLS certificate verification (skip verification).
-   Pluggable response parsers.
-   Directly polls endpoints based on their addressable metadata.
-   Does not follow HTTP redirects. A redirect response fails the poll, so a polled endpoint cannot point the request at another address.

## Usage in Other Plugins

The `metrics-data-source` uses `HTTPDataSource` as its underlying implementation, providing it with a Prometheus-specific parser.
