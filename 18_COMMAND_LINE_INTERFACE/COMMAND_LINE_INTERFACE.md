# Command Line Interface — WASTE_CLASSIFIER

**Upstream:** https://github.com/nicedoc/waste-classifier

## Anticloud CLI

```bash
# Install
pip install anticloud-waste-classifier

# Run offline with PAX inference
anticloud-waste-classifier --offline --pax-local

# Run with AIOSS logging
anticloud-waste-classifier --aioss-log ./ledger.jsonl

# Single binary (after build)
./waste_classifier --config config.yaml
```

## Options

| Flag | Description |
| --- | --- |
| `--offline` | Disable all network calls |
| `--pax-local` | Use local PAX inference at 127.0.0.1:11434 |
| `--aioss-log PATH` | Write AIOSS audit chain to PATH |
| `--encrypt` | Enable AES-256 at rest for output files |
| `--gpu` | Force GPU inference |
| `--cpu` | Force CPU inference |
| `--config PATH` | Load configuration from YAML file |
