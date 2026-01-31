<!-- =======================
UyZh-FolkSpeech README (ZH)
File: README.md
======================= -->

<div align="center">

# UyZh-FolkSpeech

**面向低资源场景的维吾尔语–汉语平行短句数据集（谚语与日常表达 + 配套音频）**

[![Code License](https://img.shields.io/badge/Code%20License-Apache%202.0-blue.svg)](LICENSE)
![Languages](https://img.shields.io/badge/Languages-Uyghur%20%7C%20Chinese-brightgreen)
![Tasks](https://img.shields.io/badge/Tasks-MT%20%7C%20NLP%20%7C%20Speech-informational)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-kalimustafa-yellow)](https://huggingface.co/?activityType=all&feedType=org&entity=kalimustafa)

[中文主页](README.md) · [English](README_EN.md) · [数据集](#数据集) · [文件结构](#文件结构) · [快速开始](#快速开始) · [引用](#引用) · [联系](#联系)

</div>

---

## 项目简介

**UyZh-FolkSpeech** 是一个面向低资源场景的**维吾尔语–汉语平行短句数据集**，聚焦新疆地区常见的**民间谚语**与**日常口语表达**，支持机器翻译、跨语言检索、对话系统与语音相关任务的训练与评测。

数据经由统一流程整理：**OCR/转写 → 人工校对 → 句级对齐 → 规范化清洗 → 质量检查**。  
谚语子集提供配套音频，并通过清单文件（manifest）实现**文本与音频的一一映射**，便于复现与下游使用。

本项目由**西北民族大学**创建支持。

---

## 数据集

### 数据规模
| 项目 | 数量 |
|---|---:|
| 平行记录总数 | 1098 |
| 谚语（proverbs） | 546 |
| 日常表达（daily phrases） | 552 |
| 音频（对应谚语） | 546 |

### 字段设计（TSV/JSONL）
| 字段 | 类型 | 说明 |
|---|---|---|
| `id` | string | 稳定唯一编号 |
| `uy` | string | 维吾尔文文本（UTF-8） |
| `zh` | string | 中文文本（UTF-8） |
| `subset` | string | `proverb` / `daily_phrase` |
| `source_type` | string | `online` / `field` |
| `tags` | string/list | 最小主题标签 |
| `audio_file` | string | 音频文件名（与清单映射） |
| `license_flag` | string | `public` / `restricted` |

---

## 文件结构

```text
UyZh-FolkSpeech/
  README.md
  README_EN.md
  LICENSE
  CITATION.cff
  CHANGELOG.md

  data/
    processed/
      uyzh_folkspeech.tsv
      uyzh_folkspeech.jsonl
    splits/
      train_ids.txt
      dev_ids.txt
      test_ids.txt

  audio/
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
    eval_bleu.py

  paper/
    manuscript.docx
    figures/
    tables/




