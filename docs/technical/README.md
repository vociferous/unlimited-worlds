# Technical Documentation

Architecture docs, API specs, and system design references. ADRs live in `progress/decisions/` and are linked here once accepted.

## Index

| Document | Status | Last Updated |
|----------|--------|--------------|
| System Architecture Overview | TODO | — |
| Networking Protocol | TODO | — |
| World Simulation Design | TODO | — |
| Database Schema | TODO | — |
| Server Deployment Architecture | TODO | — |
| Client Architecture | TODO | — |
| Asset Pipeline | TODO | — |
| Security & Anti-Cheat | TODO | — |

## Accepted ADRs

| ADR | Decision | Date |
|-----|----------|------|
| — | None yet | — |

## Scale Targets

These are the non-negotiable requirements all technical decisions are made against:

| Metric | Target |
|--------|--------|
| Concurrent players (global) | 100,000+ |
| Concurrent players per zone | 500+ (dense) |
| World state update rate | 20 ticks/sec |
| Latency (P95, same region) | < 80ms |
| Uptime | 99.9% |
| World persistence | Zero data loss on crash |
