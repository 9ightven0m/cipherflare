# Dark Web PGP Verifier — Quick Start Guide (2025)

A production-ready PGP verification tool that automatically separates **real .onion sites** from **fakes, phishing, and noise**.

Works perfectly on **Kali Linux + Tor Browser**.

## What It Does

Scores every .onion link from 0–4 using real PGP checks:

| Score | Rating     | Meaning                          |
|-------|------------|----------------------------------|
| 4/4   | Excellent  | Full PGP proof — monitor heavily |
| 3/4   | Good       | Strong authenticity              |
| 2/4   | Fair       | Partial PGP — monitor cautiously |
| 0–1/4 | Poor       | No PGP — discard (fake/noise)    |

Outputs `verified.json` for your dashboard.

## Requirements

- Kali Linux
- Tor Browser (must be open)
- Python 3.11+

## Step-by-Step Setup & Run

```bash
# 1. Create folder
cd ~
mkdir DW-PGP && cd DW-PGP

# 2. Create virtual environment
python3 -m venv pgp-poc-env
source pgp-poc-env/bin/activate

# 3. Install packages
pip install --upgrade pip
pip install python-gnupg requests[socks]

# 4. Open Tor Browser (keep it running)

# 5. Create onions.txt
nano onions.txt
# Paste one .onion per line

# 6. Add script
nano pgp_onion_verifier.py
# Paste the full script here

# 7. Run it
./pgp_onion_verifier.py

# 8. When done
deactivate
