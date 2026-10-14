# Educators — BULLET

**Project:** BULLET  
**Category:** ARTILLERY_MANUFACTURING  
**Upstream:** see BENCH.json  
**Pinned commit:** `63c4d67e337017f9d8b298c900e9aabdb69296e7`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `19b7ea0b066aff0fb61d9b75783aa25e62b8a28e1b693cdbe2c998d0168cf944`  
**Date:** October 2026

## Teaching with BULLET

The project is usable as a worked example of offline-first packaging with a
cryptographic audit chain. It ships with the assurance suite, the evidence
register and the ledger, so students can verify claims rather than take them on
faith.

## Suggested exercises

1. Run `python tools/run_bench.py --out BENCH.json` and read the 16 results.
2. Recompute the SHA3-256 of a row's evidence file and compare to the register.
3. Walk the AIOSS chain from genesis to head `19b7ea0b066aff0fb61d9b75783aa25e62b8a28e1b693cdbe2c998d0168cf944` and confirm every link.
4. Break one artifact and observe the chain fail to verify.

## Licence for teaching

Apache 2.0 terms apply to academic and teaching use. See `24_ANTICOMMONS_LICENSE`.
