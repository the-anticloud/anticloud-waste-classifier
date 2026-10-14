# Educators — WASTE_CLASSIFIER

**Project:** WASTE_CLASSIFIER  
**Category:** WASTE_MANAGEMENT  
**Upstream:** see BENCH.json  
**Pinned commit:** `a61bf27eb1efafcc58af5997d2379f97f67125b2`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `2f5a924de83708605925aea76f3344a74afadfe32863451fe015f51357333c48`  
**Date:** October 2026

## Teaching with WASTE_CLASSIFIER

The project is usable as a worked example of offline-first packaging with a
cryptographic audit chain. It ships with the assurance suite, the evidence
register and the ledger, so students can verify claims rather than take them on
faith.

## Suggested exercises

1. Run `python tools/run_bench.py --out BENCH.json` and read the 16 results.
2. Recompute the SHA3-256 of a row's evidence file and compare to the register.
3. Walk the AIOSS chain from genesis to head `2f5a924de83708605925aea76f3344a74afadfe32863451fe015f51357333c48` and confirm every link.
4. Break one artifact and observe the chain fail to verify.

## Licence for teaching

Apache 2.0 terms apply to academic and teaching use. See `24_ANTICOMMONS_LICENSE`.
