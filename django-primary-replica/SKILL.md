---
name: django-primary-replica
description: Plan or review Django primary and read-replica connections using psycopg3 and PgBouncer transaction pooling. Use for database routing, pooling, or tenant-schema isolation work in this stack.
---

# Django Primary and Replica

Design a resilient Django 6, psycopg3, and PgBouncer transaction-pooling strategy. Inspect the application's versions, database aliases, routers, and transaction boundaries before proposing changes.

Preserve these configuration requirements from the existing backend setup:

- Set `DISABLE_SERVER_SIDE_CURSORS = True` on database aliases using transaction pooling.
- Set `OPTIONS = {"prepare_threshold": None}` unless prepared-statement support has been verified for the deployed PgBouncer version and configuration. The existing setup identifies PgBouncer 1.21+ as a candidate for that verification; version alone is insufficient.
- Use `SET LOCAL` inside `atomic()` for schema or tenant switching. Avoid session-level `SET` across pooled transactions.
- Use `CONN_MAX_AGE = 0` as the existing baseline; explain any proposed change in the context of Django connection reuse and PgBouncer pooling.
- Keep transactions short. Audit long-running `atomic()` blocks and streaming queries.

The existing environment uses `historian.platform:5432` for the primary and `historian.platform:5433` for the read-only replica. Confirm that these endpoints apply to the target environment before configuring them; do not impose them on other deployments.

Keep writes on the primary. Identify reads that require immediate consistency before sending them to the replica, and account for replica lag and unavailability. State the intended failure behavior instead of silently changing routing.

Deliver the proposed settings and routing policy, the reasons for each change, and a validation plan covering tenant isolation, pooled connections, read-after-write consistency, and replica failure. Apply changes only within the user's requested implementation scope.
