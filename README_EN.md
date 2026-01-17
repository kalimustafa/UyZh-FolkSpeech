

<div align="center">

# UyZh-FolkSpeech

**A Uyghur–Chinese parallel short-text dataset for low-resource scenarios (proverbs + daily phrases, optional creator-recorded audio)**

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](LICENSE)
![Language](https://img.shields.io/badge/Language-Uyghur%20%7C%20Chinese-brightgreen)
![Task](https://img.shields.io/badge/Task-MT%20%7C%20NLP%20%7C%20Speech-informational)

[English](README_EN.md) • [中文主页](README.md) • [Dataset](#dataset) •Citation](#citation) • [Contact](#contact)

</div>




## Overview

**UyZh-FolkSpeech** is a **Uyghur–Chinese parallel short-text dataset** curated for low-resource research and real-world language services.  
It focuses on culturally grounded **proverbs** and practical **daily spoken expressions**, supporting **machine translation**, **cross-lingual evaluation**, dialogue applications, and (optionally) **speech-related tasks**.

The dataset is built through an end-to-end pipeline:  
**OCR/transcription → manual correction → sentence-level alignment → normalization/cleaning → quality control**.  
For the proverb subset, we optionally provide **creator-recorded audio** and a mapping manifest for reproducible speech experiments and multimodal research.

---

## Dataset

### Statistics (edit to match your final release)
| Item | Count |
|---|---:|
| Total aligned records | 1098 |
| Proverbs | 546 |
| Daily phrases | 552 |
| Optional audio clips (proverbs) | 546 |


### Recommended schema (fields)
Each record is recommended to include the following fields (TSV/JSONL are both acceptable):
- `id`: stable unique identifier (e.g., `P0001`/`D0001` or numeric IDs)
- `uy`: Uyghur text (UTF-8)
- `zh`: Chinese text (UTF-8)
- `subset`: `proverb` / `daily_phrase`
- `source_type`: `online` / `field`
- `tags`: minimal topic tags (optional)
- `audio_file`: audio filename (optional; proverb subset only)
- `license_flag`: `public` / `restricted` 
