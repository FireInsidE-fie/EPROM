---
tags:
  - 
---
TimescaleDB is a **[[PostgreSQL]] extension that optimizes for time-series workloads**.
It is ideal for monitoring systems, IoT telemetry, financial data, and other time-series applications.
# Key Concepts
## Hypertable
The Hypertable is a **PostgreSQL table that TimescaleDB slices into individual *chunks* based on time data**.
This makes such a table perfect for chronological lookups. When trying to query a range of data over for example a day, it allows TimescaleDB to effectively "skip" the rest of the data based on time information.
On top of that, **older chunks can be converted to a columnar compressed format**, saving tremendous space (10x or so).
# Resources
- [Official TimescaleDB Website](https://timescaledb.org)