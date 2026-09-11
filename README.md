# lingshu-bench

Performance benchmarks and load profiles for LingShu GPU pool.

## Layout

- `loadgen/` — concurrent task submitter (QPS / payload / op-mix configurable)
- `profiles/` — canned load profiles:
  - `inference-burst` (1000 RPS spike)
  - `inference-steady` (100 RPS, 24h soak)
  - `training-mixed` (10 long-running + 1000 short)
  - `chaos` (combined with failure injection)
- `bench/` — JMH-style microbenchmarks:
  - NettyPacket codec throughput
  - RequestPromise sync wait latency
  - Load balancer sort latency
  - MySQL state write throughput
- `reports/` — baseline numbers per cluster size (3 / 10 / 30 nodes)

Out of MVP scope — no deployment-grade load testing infra yet.
