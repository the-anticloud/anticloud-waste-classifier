# Build and Test

**Project:** `WASTE_CLASSIFIER`
**Upstream:** https://github.com/nicedoc/waste-classifier
**License:** MIT

## Quick Start

```bash
git clone https://github.com/nicedoc/waste-classifier
cd waste-classifier
pip install -r requirements-anticloud.txt
python anticloud_main.py --offline --pax-local
```

## Anticloud Improvements Applied

1. PAX L5 Narrow L2 General 27B local waste classification from images — edge deployment
2. AIOSS tamper-evident waste tracking chain (EPA manifest audit-ready)
3. AES-256 encryption for all collection route and manifest data
4. Single-binary fleet management system deployable on vehicle tablets
5. Zero-cloud: all AI sorting, routing, and reporting runs locally
6. GPU/CPU equalizer: vision classification on embedded GPU or CPU
7. Open EPA e-Manifest integration replacing proprietary waste tracking software
8. Offline circular economy optimization: material recovery routing without internet

## Benchmark Targets

| Metric | Target |
| --- | --- |
| Latency | Primary inference task: <5s on CPU, <1s on GPU |
| Throughput | Batch processing: >100 items/hour on single CPU server |
| Memory | <8GB RAM for standard deployment |
| Accuracy | Task-specific accuracy within 5% of cloud-API baseline |

## Build Status

Not yet measured. Run verified build and record actual figures above.
