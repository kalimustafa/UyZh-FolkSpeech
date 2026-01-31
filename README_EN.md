
---

## 2) 英文 `README_EN.md`（同样改成 mustafakali 直链）

```md
<!-- =======================
UyZh-FolkSpeech README (EN)
File: README_EN.md
======================= -->

<div align="center">

# UyZh-FolkSpeech

**A Uyghur–Chinese dataset of proverbs, daily phrases, and common words with four-speaker audio**

[![Code License](https://img.shields.io/badge/Code%20License-Apache%202.0-blue.svg)](LICENSE)
[![Data License](https://img.shields.io/badge/Data%20License-CC%20BY%204.0-green.svg)](DATA_LICENSE)
![Languages](https://img.shields.io/badge/Languages-Uyghur%20%7C%20Chinese-brightgreen)
![Tasks](https://img.shields.io/badge/Tasks-MT%20%7C%20NLP%20%7C%20Speech-informational)
[![HF Dataset](https://img.shields.io/badge/HuggingFace-Dataset-yellow)](https://huggingface.co/datasets/mustafakali/UyZh-FolkSpeech)

[English](README_EN.md) · [中文主页](README.md) · [Dataset](#dataset) · [Files](#files) · [Quickstart](#quickstart) · [Citation](#citation) · [Contact](#contact)

</div>

---

## Overview

**UyZh-FolkSpeech** is a manually curated **Uyghur–Chinese** resource covering:
- **953** short-sentence pairs (proverbs and daily expressions)
- **1,031** common words / short phrases

Each text item is assigned an immutable identifier:
- `UYZH-S-*` for short sentences
- `UYZH-W-*` for words/phrases

For every item, we release recordings from **four native speakers (S01–S04; two male and two female)**, resulting in **7,936** aligned audio clips in total.

All audio is distributed as **M4A (AAC-LC), 48 kHz, mono**, and linked to text records via a manifest for reproducible use.

---

## Dataset

### One-click link (Hugging Face)
- **Hugging Face Dataset**: https://huggingface.co/datasets/mustafakali/UyZh-FolkSpeech

### Statistics
| Item | Count |
|---|---:|
| Total text items | 1,984 |
| Short-sentence pairs | 953 |
| Word / short-phrase entries | 1,031 |
| Speakers per item | 4 (S01–S04) |
| Total audio clips | 7,936 |

### Recommended schema (TSV)
| Field | Type | Description |
|---|---|---|
| `id` | string | Immutable record ID (`UYZH-S-*` / `UYZH-W-*`) |
| `subset` | string | `sentence` / `word_phrase` |
| `uy` | string | Uyghur text (UTF-8) |
| `zh` | string | Chinese text (UTF-8) |
| `source_type` | string | `online` / `field` (if provided) |
| `tags` | string/list | minimal topic tags (if provided) |

---

## Files

```text
UyZh-FolkSpeech/
  README.md
  README_EN.md
  LICENSE
  DATA_LICENSE
  CITATION.cff
  CHANGELOG.md

  data/
    uyzh_bilingual_pairs.tsv
    common_words_1031.tsv
    documents_metadata.csv

  audio/
    S01/
    S02/
    S03/
    S04/
    audio_manifest.tsv

  splits/
    train/
    valid/
    test/
    eval50_ids.txt

  scripts/
    *.py
  configs/
    *.yaml

  paper/
    UyZh-FolkSpeech_2026-01-26.docx
