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
[![HuggingFace](https://img.shields.io/badge/HuggingFace-Dataset-yellow)](https://huggingface.co/datasets/mustafakali/UyZh-FolkSpeech)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-Org-yellow)](https://huggingface.co/?activityType=all&feedType=org&entity=kalimustafa)

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

For every item, we release **four native-speaker recordings (S01–S04; two male and two female)**, yielding **7,936** aligned audio clips in total.

All audio is distributed as **M4A (AAC-LC), 48 kHz, mono**, with a target bitrate of ~64 kbps, and is linked to text records via a manifest that includes required technical metadata.

The dataset supports machine translation, speech-enabled NLP, ASR, and speech-to-text translation under low-resource conditions.

---

## Dataset

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
| `subset` | string | sentence / word_phrase (or finer tags if you use them) |
| `uy` | string | Uyghur text (UTF-8) |
| `zh` | string | Chinese text (UTF-8) |
| `has_audio` | bool/int | audio availability (expected: true for all items in this release) |
| `source_type` | string | collection channel flag (if provided) |
| `tags` | string/list | minimal topic tags |

---

## Files

The released package contains bilingual TSV files, metadata, a complete audio set, an audio manifest, recommended splits, and scripts/configs for reproducible evaluation.

```text
UyZh-FolkSpeech/
  README.md
  README_EN.md
  LICENSE
  DATA_LICENSE
  CITATION.cff
  CHANGELOG.md

  data/
    uyzh_bilingual_pairs.tsv          # 953 sentence pairs
    common_words_1031.tsv             # 1,031 word/phrase entries
    documents_metadata.csv            # high-level metadata

  audio/
    S01/                              # speaker-organized M4A clips
    S02/
    S03/
    S04/
    audio_manifest.tsv                # id, speaker, path, duration, sr=48000, codec=aac-lc, ch=1, bitrate

  splits/
    train/
    valid/
    test/
    eval50_ids.txt                    # fixed eval subset for reproducible reporting

  scripts/
    *.py
  configs/
    *.yaml

  lora_adapters/                      # LoRA weights used in the paper demo (if you choose to publish)
  paper/
    UyZh-FolkSpeech_2026-01-26.docx
