---
name: api-performance-plan
description: Diagnose slow API table views and produce an evidence-based optimization plan focused on database indexes and row-level caching. Use when asked to plan API performance improvements.
---

# API Performance Plan

Inspect the endpoint, table-view filters and ordering, pagination, query patterns, and existing cache behavior. Use available timings and query plans to identify bottlenecks; distinguish measured findings from hypotheses when profiling data is missing.

Prioritize index candidates based on the actual filters, joins, and ordering. Explain the expected read benefit alongside write and storage costs, and check for equivalent existing indexes.

For row-level caching, define keys, tenant and authorization scope, expiration, and invalidation on writes or deletes. Account for filtered-list membership, ordering, and pagination so cached rows do not leave the table view stale or expose another user's data.

Return a prioritized implementation plan with evidence, expected benefit, tradeoffs, and before/after measurement criteria. Keep the task at the planning stage unless the user also requests implementation.
