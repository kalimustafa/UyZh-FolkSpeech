<!-- =======================
UyZh-FolkSpeech README
Copy to: README.md
======================= -->

<div align="center">

# UyZh-FolkSpeech549

**A Uyghur–Chinese parallel dataset of proverbs and daily phrases (with optional creator-recorded audio)**

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](LICENSE)
![Language](https://img.shields.io/badge/Language-Uyghur%20%7C%20Chinese-brightgreen)
![Task](https://img.shields.io/badge/Task-MT%20%7C%20NLP%20%7C%20Speech-informational)

[中文主页](README.md) • [English](README_EN.md) • [Paper](#citation) • [Dataset](#dataset) • [Quickstart](#quickstart) • [Contact](#contact)

</div>

---

## News
- **2026-01**: Initial release of **UyZh-FolkSpeech549** (549 aligned records; optional audio subset for proverbs).

---

## Overview

**UyZh-FolkSpeech549** is a curated **Uyghur–Chinese parallel short-text dataset** focusing on culturally grounded **proverbs** and practical **daily expressions**.  
It is designed for **machine translation fine-tuning**, **cross-lingual evaluation**, and (optionally) **speech-related tasks** by pairing Uyghur text with creator-recorded audio.

**Key features**
- **549** aligned Uyghur–Chinese records (**273 proverbs + 276 daily phrases**)
- Stable **IDs**, subset labels, metadata fields, and recommended splits
- Optional **273** creator-recorded Uyghur audio clips (for proverb subset) + manifest mapping
- Practical scripts for loading / QA checks / splits / (optional) MT fine-tuning & BLEU evaluation

---

## Dataset

### Statistics
| Item | Count |
|---|---:|
| Total aligned records | 549 |
| Proverbs | 273 |
| Daily phrases | 276 |
| Optional audio clips (proverbs) | 273 |

> If you later expand to “1000 sentences (Uy 500 + Zh 500)”, update the table and release notes accordingly.

### File formats (recommended)
- `TSV/CSV` for main parallel pairs
- `JSONL` for richer metadata & downstream pipelines
- `M4A/WAV` for optional audio subset (proverbs)

### Recommended fields (schema)
- `id`: stable record ID (e.g., `P0001` / `D0001` or numeric)
- `uy`: Uyghur text (UTF-8, RTL-safe)
- `zh`: Chinese text (UTF-8)
- `subset`: `proverb` / `daily_phrase`
- `source_type`: `online` / `field`
- `tags`: minimal topic tags (optional)
- `audio_file`: filename for proverb audio (optional)
- `license_flag`: `public` / `restricted` (if you separate release scope)

---

## Repository Structure

```text
UyZh-FolkSpeech549/
  README.md
  README_EN.md
  LICENSE
  CITATION.cff
  CHANGELOG.md

  data/
    processed/
      uyzh_folkspeech549.tsv
      uyzh_folkspeech549.jsonl
    splits/
      train_ids.txt
      dev_ids.txt
      test_ids.txt

  audio/                      # optional (proverb subset)
    m4a/
      0001.m4a
      ...
    audio_manifest.tsv

  metadata/
    schema.json
    sources.csv
    stats/

  scripts/
    load_data.py
    qc_checks.py
    make_splits.py
    eval_bleu.py              # optional

  paper/
    manuscript.docx
    figures/
    tables/
