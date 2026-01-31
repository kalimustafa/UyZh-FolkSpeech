
---

## `README_EN.md`（正式版）

```md
<div align="center">

# UyZh-FolkSpeech

A Uyghur–Chinese dataset of proverbs, daily phrases, and common words with four-speaker audio

[![Code License](https://img.shields.io/badge/Code%20License-Apache%202.0-blue.svg)](LICENSE)
[![Data License](https://img.shields.io/badge/Data%20License-CC%20BY%204.0-green.svg)](DATA_LICENSE)
![Languages](https://img.shields.io/badge/Languages-Uyghur%20%7C%20Chinese-brightgreen)
![Tasks](https://img.shields.io/badge/Tasks-MT%20%7C%20NLP%20%7C%20Speech-informational)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-Dataset-yellow)](https://huggingface.co/datasets/mustafakali/UyZh-FolkSpeech)

[English](README_EN.md) · [中文](README.md) · [Dataset](#dataset) · [Files](#files) · [Usage](#usage) · [Citation](#citation) · [Contact](#contact)

</div>

---

## Overview

UyZh-FolkSpeech is a Uyghur–Chinese resource for low-resource research and language services. It contains 953 aligned short-sentence pairs and 1,031 common word and phrase entries. All records are assigned immutable identifiers. Sentence pairs use `UYZH-S-*` and words or phrases use `UYZH-W-*`.

Each record includes audio from four native speakers, resulting in 7,936 aligned audio clips. Audio is distributed in M4A format (AAC-LC), 48 kHz, mono. A manifest provides one-to-one mapping between record identifiers and audio files.

---

## Dataset

Dataset page:

https://huggingface.co/datasets/mustafakali/UyZh-FolkSpeech

### Statistics

| Item | Count |
|---|---:|
| Total text records | 1,984 |
| Short-sentence pairs | 953 |
| Word and phrase entries | 1,031 |
| Speakers | 4 |
| Total audio clips | 7,936 |

### Fields

| Field | Type | Description |
|---|---|---|
| `id` | string | Immutable record identifier |
| `subset` | string | Subset label |
| `uy` | string | Uyghur text |
| `zh` | string | Chinese text |
| `source_type` | string | Source type |
| `tags` | string/list | Topic tags |

The audio manifest `audio_manifest.tsv` includes record identifiers, speaker IDs, file paths, and essential audio metadata.

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
