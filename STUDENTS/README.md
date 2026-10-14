# Students — BULLET

**Project:** BULLET  
**Category:** ARTILLERY_MANUFACTURING  
**Upstream:** see BENCH.json  
**Pinned commit:** `63c4d67e337017f9d8b298c900e9aabdb69296e7`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `19b7ea0b066aff0fb61d9b75783aa25e62b8a28e1b693cdbe2c998d0168cf944`  
**Date:** October 2026

## What this project gives you

A complete worked example of offline-first packaging with a cryptographic audit
chain: source pinned at `63c4d67e337017f9d8b298c900e9aabdb69296e7`, a 16-check assurance suite, an evidence register
with per-check hashes, and an AIOSS ledger chain ending at `19b7ea0b066aff0fb61d9b75783aa25e62b8a28e1b693cdbe2c998d0168cf944`.

## Learn by verifying

```
python tools/run_bench.py --out BENCH.json
```

Then take any row from `ISOLATED_LAB_RESULTS/03_Result_Register.md`, recompute
the SHA3-256 of its evidence file, and confirm it matches. If it does not match,
the record has been altered — that is the whole point of the chain.

## Licence

Apache 2.0 terms apply to study and teaching use.
