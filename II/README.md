# Independent Insurance — BULLET

**Project:** BULLET  
**Category:** ARTILLERY_MANUFACTURING  
**Upstream:** see BENCH.json  
**Pinned commit:** `63c4d67e337017f9d8b298c900e9aabdb69296e7`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `19b7ea0b066aff0fb61d9b75783aa25e62b8a28e1b693cdbe2c998d0168cf944`  
**Date:** October 2026

## Why AI-specific cover matters

Deploying AI in a regulated sector creates liability surfaces that ordinary
technology cover does not reach: inference liability, audit-trail liability,
data-breach liability and IP-infringement liability.

## How this project's architecture reduces insurable risk

| Risk | Cloud AI | BULLET with AIOSS |
|---|---|---|
| Audit-trail loss | high — vendor-controlled logs | low — append-only chain, verifiable offline |
| Data breach in transit | high — data transits external servers | low — no external endpoint |
| Compliance violation | high — cannot satisfy air-gap requirements | low — structural |
| IP liability | moderate | low — pinned provenance chain |

## Evidence package for an insurer

- AIOSS chain verification for head `19b7ea0b066aff0fb61d9b75783aa25e62b8a28e1b693cdbe2c998d0168cf944`
- The 16-check register with per-check evidence hashes
- Framework control mapping in `BENCH.json`

## Contact

lois@0-1.gg
