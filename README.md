<!-- =======================
UyZh-FolkSpeech README (ZH)
Save as: README.md
======================= -->

<div align="center">

# UyZh-FolkSpeech

**面向低资源场景的维吾尔语–汉语平行短句数据集**

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](LICENSE)
![Language](https://img.shields.io/badge/Language-%E7%BB%B4%E5%90%BE%E5%B0%94%E8%AF%AD%20%7C%20%E6%B1%89%E8%AF%AD-brightgreen)
![Task](https://img.shields.io/badge/Task-%E6%9C%BA%E5%99%A8%E7%BF%BB%E8%AF%91%20%7C%20NLP%20%7C%20%E8%AF%AD%E9%9F%B3-informational)

[中文主页](README.md) • [English](README_EN.md) • [数据集](#数据集) • [快速开始](#快速开始) • [引用](#引用) • [联系](#联系)

</div>

---



---

## 项目简介

**UyZh-FolkSpeech** 是一个面向低资源场景的**维吾尔语–汉语平行短句数据集**，聚焦新疆地区常见的**民间谚语**与**日常口语表达**，面向机器翻译、跨语言检索、对话系统与语音相关任务的训练与评测。

数据通过 **OCR/转写 → 人工校对 → 句级对齐 → 规范化清洗 → 质量检查** 的流水线整理；对于谚语子集，可选提供**创作者录音**与清单映射（manifest），以支持可复现的语音实验与多模态研究。

---

## 数据集

### 数据规模
| 项目 | 数量 |
|---|---:|
| 平行记录总数 | 549 |
| 谚语（proverbs） | 273 |
| 日常表达（daily phrases） | 276 |
| 音频（谚语子集） | 273 |


### 字段设计
每条样本建议包含以下字段（TSV/JSONL 均可）：
- `id`：稳定唯一编号
- `uy`：维吾尔文文本（UTF-8）
- `zh`：中文文本（UTF-8）
- `subset`：`proverb` / `daily_phrase`
- `source_type`：`online` / `field`
- `tags`：最小主题标签
- `audio_file`：音频文件名
- `license_flag`：`public` / `restricted`

---

## 仓库结构

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

  audio/                      # 
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
    eval_bleu.py              #

  paper/
    manuscript.docx
    figures/
    tables/
<!-- =======================
UyZh-FolkSpeech README (ZH)
Save as: README.md
======================= -->

<div align="center">

# UyZh-FolkSpeech

**面向低资源场景的维吾尔语–汉语平行短句数据集（谚语 + 日常表达，可选配套录音）**

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](LICENSE)
![Language](https://img.shields.io/badge/Language-%E7%BB%B4%E5%90%BE%E5%B0%94%E8%AF%AD%20%7C%20%E6%B1%89%E8%AF%AD-brightgreen)
![Task](https://img.shields.io/badge/Task-%E6%9C%BA%E5%99%A8%E7%BF%BB%E8%AF%91%20%7C%20NLP%20%7C%20%E8%AF%AD%E9%9F%B3-informational)

[中文主页](README.md) • [English](README_EN.md) • [数据集](#数据集) • [快速开始](#快速开始) • [引用](#引用) • [联系](#联系)

</div>

---

## 更新日志
- **2026-01**：发布 UyZh-FolkSpeech。

---

## 项目简介

**UyZh-FolkSpeech** 是一个面向低资源场景的**维吾尔语–汉语平行短句数据集**，聚焦新疆地区常见的**民间谚语**与**日常口语表达**，面向机器翻译、跨语言检索、对话系统与（可选）语音相关任务的训练与评测。

数据通过 **OCR/转写 → 人工校对 → 句级对齐 → 规范化清洗 → 质量检查** 的流水线整理；对于谚语子集，可选提供**创作者录音**与清单映射（manifest），以支持可复现的语音实验与多模态研究。

---

## 数据集

### 数据规模
| 项目 | 数量 |
|---|---:|
| 平行记录总数 | 549 |
| 谚语（proverbs） | 273 |
| 日常表达（daily phrases） | 276 |
| 可选音频（谚语子集） | 273 |



### 字段设计
每条样本建议包含以下字段（TSV/JSONL 均可）：
- `id`：稳定唯一编号（如 `P0001`/`D0001` 或纯数字）
- `uy`：维吾尔文文本（UTF-8）
- `zh`：中文文本（UTF-8）
- `subset`：`proverb` / `daily_phrase`
- `source_type`：`online` / `field`
- `tags`：最小主题标签
- `audio_file`：音频文件名
- `license_flag`：`public` / `restricted`
---

## 仓库结构

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

  audio/                      # 可选
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
    eval_bleu.py              # 可选：MT 评测示例

  paper/
    manuscript.docx
    figures/
    tables/
