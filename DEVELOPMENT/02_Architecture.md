# Technical Architecture — WASTE_CLASSIFIER

**Upstream:** [https://github.com/nicedoc/waste-classifier](https://github.com/nicedoc/waste-classifier)
**License:** MIT
**Category:** WASTE_MANAGEMENT
**Anticloud Integration:** PAX L5 Narrow L2 General 27B + AIOSS + Offline-First

## Upstream Description

Waste image classification with deep learning

## Anticloud Architectural Changes

1. PAX L5 Narrow L2 General 27B local waste classification from images — edge deployment
2. AIOSS tamper-evident waste tracking chain (EPA manifest audit-ready)
3. AES-256 encryption for all collection route and manifest data
4. Single-binary fleet management system deployable on vehicle tablets
5. Zero-cloud: all AI sorting, routing, and reporting runs locally
6. GPU/CPU equalizer: vision classification on embedded GPU or CPU
7. Open EPA e-Manifest integration replacing proprietary waste tracking software
8. Offline circular economy optimization: material recovery routing without internet

## Integration Points

- **PAX Inference Socket:** Local HTTP endpoint at `127.0.0.1:11434/v1/chat` — same OpenAI-compatible API, zero cloud
- **AIOSS Hook:** Every write operation calls `aioss_append(event, payload)` before commit
- **Encryption Layer:** All file I/O routed through `anticloud_crypto.encrypt_at_rest()`
- **Single Binary Build:** `pyinstaller anticloud_waste_classifier.spec` or `go build -o waste_classifier`

## Deployment Modes

| Mode | Hardware | Notes |
| --- | --- | --- |
| Edge CPU | Raspberry Pi 4 / Intel NUC | Full feature set, PAX on CPU |
| Desktop GPU | RTX 3060 / A10 | PAX GPU inference, <1s latency |
| Server | 2× A100 | Full batch throughput |
| Air-gapped | Any x86/ARM | Zero network dependency |