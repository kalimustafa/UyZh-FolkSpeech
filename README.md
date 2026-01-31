<!-- =======================
UyZh-FolkSpeech README (ZH)
File: README.md
======================= -->

<div align="center">

# UyZh-FolkSpeech

**包含谚语、日常表达与常用词条的维吾尔语–汉语平行数据集（四位说话人录音全覆盖）**

[![Code License](https://img.shields.io/badge/Code%20License-Apache%202.0-blue.svg)](LICENSE)
[![Data License](https://img.shields.io/badge/Data%20License-CC%20BY%204.0-green.svg)](DATA_LICENSE)
![Languages](https://img.shields.io/badge/Languages-Uyghur%20%7C%20Chinese-brightgreen)
![Tasks](https://img.shields.io/badge/Tasks-MT%20%7C%20NLP%20%7C%20Speech-informational)
[![HF Dataset](https://img.shields.io/badge/HuggingFace-Dataset-yellow)](https://huggingface.co/datasets/mustafakali/UyZh-FolkSpeech)
[![HF Org](https://img.shields.io/badge/HuggingFace-Org-yellow)](https://huggingface.co/?activityType=all&feedType=org&entity=kalimustafa)

[中文主页](README.md) · [English](README_EN.md) · [数据集](#数据集) · [文件结构](#文件结构) · [快速开始](#快速开始) · [引用](#引用) · [联系](#联系)

</div>

---

## 项目简介

**UyZh-FolkSpeech** 是一个面向低资源场景的**维吾尔语–汉语**资源，覆盖：
- **953** 条维汉短句对（谚语与日常表达）
- **1,031** 条常用词与短语条目

所有条目均分配不可变 ID：
- 短句对：`UYZH-S-*`
- 词与短语：`UYZH-W-*`

每个条目均提供 **4 位母语说话人录音**（S01–S04，两男两女），用于机器翻译、语音增强 NLP、ASR 与语音到文本翻译等任务的训练与评测。

音频格式统一为 **M4A（AAC-LC），48 kHz，单声道**，并通过清单文件（manifest）实现文本与音频的一一映射，便于复现与下游处理。

---

## 数据集

### 一键直连（Hugging Face）
- **Hugging Face Dataset**：https://huggingface.co/datasets/mustafakali/UyZh-FolkSpeech

### 数据规模
| 项目 | 数量 |
|---|---:|
| 文本条目总数 | 1,984 |
| 短句对（谚语与日常表达） | 953 |
| 常用词与短语条目 | 1,031 |
| 每条目说话人数 | 4（S01–S04） |
| 音频片段总数 | 7,936 |

### 字段设计（TSV 推荐）
| 字段 | 类型 | 说明 |
|---|---|---|
| `id` | string | 不可变记录 ID（`UYZH-S-*` / `UYZH-W-*`） |
| `subset` | string | `sentence` / `word_phrase`（或更细标签） |
| `uy` | string | 维吾尔文文本（UTF-8） |
| `zh` | string | 中文文本（UTF-8） |
| `source_type` | string | `online` / `field`（如已提供） |
| `tags` | string/list | 最小主题标签（如已提供） |

音频清单（`audio_manifest.tsv`）建议至少包含：
- `id`、`speaker`、`path`、`duration`
- `sample_rate`（固定 48000）、`channels`（固定 1）、`codec`（aac-lc）、`bitrate`（或目标比特率）

---

## 文件结构

```text
UyZh-FolkSpeech/
  README.md
  README_EN.md
  LICENSE
  DATA_LICENSE
  CITATION.cff
  CHANGELOG.md

  data/
    uyzh_bilingual_pairs.tsv          # 953 条短句对
    common_words_1031.tsv             # 1,031 词/短语
    documents_metadata.csv            # 元数据（如已提供）

  audio/
    S01/
    S02/
    S03/
    S04/
    audio_manifest.tsv                # 文本 ID 与音频文件映射 + 技术参数

  splits/
    train/


  scripts/
    *.py
  configs/
    *.yaml

  paper/
    UyZh-FolkSpeech_2026-01-26.docx

