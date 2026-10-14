# Students — WASTE_CLASSIFIER

**Project:** WASTE_CLASSIFIER  
**Category:** WASTE_MANAGEMENT  
**Upstream:** see BENCH.json  
**Pinned commit:** `a61bf27eb1efafcc58af5997d2379f97f67125b2`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `2f5a924de83708605925aea76f3344a74afadfe32863451fe015f51357333c48`  
**Date:** October 2026

## What this project gives you

A complete worked example of offline-first packaging with a cryptographic audit
chain: source pinned at `a61bf27eb1efafcc58af5997d2379f97f67125b2`, a 16-check assurance suite, an evidence register
with per-check hashes, and an AIOSS ledger chain ending at `2f5a924de83708605925aea76f3344a74afadfe32863451fe015f51357333c48`.

## Learn by verifying

```
python tools/run_bench.py --out BENCH.json
```

Then take any row from `ISOLATED_LAB_RESULTS/03_Result_Register.md`, recompute
the SHA3-256 of its evidence file, and confirm it matches. If it does not match,
the record has been altered — that is the whole point of the chain.

## Licence

Apache 2.0 terms apply to study and teaching use.
