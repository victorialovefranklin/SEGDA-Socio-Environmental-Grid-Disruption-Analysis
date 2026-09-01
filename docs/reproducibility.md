# Reproducibility

## 1. Create an environment

```bash
python -m venv .venv
```

Activate the environment and install:

```bash
python -m pip install -r requirements.txt
```

## 2. Prepare the data

Place the required inputs in one directory. Set the environment variable `SEGDA_DATA_DIR` to that directory.

## 3. Run

```bash
python src/segda.py
```

You may optionally set `SEGDA_OUTPUT_DIR` to control where generated outputs are written.

## 4. Validation

The script contains expected locked-result guardrails and writes provenance, QA, tables, validation products, figures, and an export bundle. A public release should preserve the distinction between source inputs, derived outputs, and expected-result guardrails.

## Security/privacy audit

The uploaded script was checked for obvious API-key/password/token strings and hard-coded personal user paths. None were found. The author's name appears in the script header, which is appropriate for attribution.
