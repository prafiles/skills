# Backend Prompts

## Django Primary + Replica Handler
Design a resilient Django 6 + psycopg3 + PGBouncer (transaction mode) strategy:  
1. In `DATABASES`, set `DISABLE_SERVER_SIDE_CURSORS = True` and `OPTIONS = {"prepare_threshold": None}` (or confirm PGBouncer 1.21+ prepared-statement support).  
2. Ensure all schema/tenant switching uses `SET LOCAL` inside `atomic()`; avoid session-level `SET` usage.  
3. Keep `CONN_MAX_AGE` tuned 0 to balance Django connection reuse with PGBouncer pooling.  
4. Enforce short-lived transactions; audit code for long-running `atomic()` blocks and streaming queries.  
5. Use historian.platform as host with 5432 for primary replica.
6. Use historian.platform as host with 5433 for readonly replica.
