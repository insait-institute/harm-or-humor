# Harm or Humor

## A Multimodal, Multilingual Benchmark for Overt and Covert Harmful Humor

**Ahmed Sharshar\***, **Hosam Elgendy\***, **Yasser Rohaim**, **Saad El Dine Ahmed**, and **Yuxia Wang**  
\* Equal contribution

[Paper](https://arxiv.org/abs/2603.17759) · [Dataset](https://drive.google.com/drive/folders/1H2W9Q43G8wtJy5F-KmOc2WhDDegBzJ5Z?usp=sharing) 

> [!CAUTION]
> **Content warning:** This repository contains or references offensive text, meme imagery, video clips, audio, and other audiovisual material that may involve sexual, violent, discriminatory, religious, disability-related, or historically sensitive themes. Please use the dataset only in appropriate research settings and take suitable precautions for researchers, annotators, and participants who may be exposed to the content.

## Overview

<img width="987" height="623" alt="Screenshot 2026-08-25 at 3 37 02 PM" src="https://github.com/user-attachments/assets/81a48fba-adcb-4eb2-a7ce-f9d533c5ba1a" />


**Harm or Humor** is a manually curated benchmark for evaluating whether AI systems can distinguish safe humor from harmful humor across **text, images/memes, and short videos**. The benchmark covers **English**, **Arabic varieties**, and a visually grounded **Universal** video subset in which the joke does not depend on essential spoken or written language.

Unlike conventional toxicity benchmarks that often reward recognition of surface cues, this benchmark separates harmful jokes into:

- **Explicit harm:** the harmful meaning is directly signaled by overt markers such as slurs, profanity, direct demeaning language, or graphic sexual/violent cues.
- **Implicit harm:** the harmful meaning emerges only after reasoning over sarcasm, irony, innuendo, stereotype framing, multimodal juxtaposition, cultural or contextual knowledge, or punchline reinterpretation.

The benchmark is designed to test whether models understand *why* a joke is harmful rather than merely reacting to isolated words or visual elements.

## Key Contributions

- A unified benchmark spanning **3 modalities**, **2 languages plus language-independent visual content**, and **10,207 examples**.
- A two-stage annotation taxonomy: **Safe vs. Harmful**, followed by **Explicit vs. Implicit** for harmful items.
- Broad Arabic coverage, including Modern Standard Arabic and multiple regional varieties.
- A systematic evaluation of open- and closed-source LLMs, VLMs, and video-language models under a shared safety-classification task.
- Analysis of failures caused by surface-cue overreaction, missed implicit meaning, and mismatched harmfulness thresholds.

## Dataset at a Glance

### Text

| Language | Safe | Implicit Harmful | Explicit Harmful | Total |
|---|---:|---:|---:|---:|
| Arabic | 546 | 274 | 180 | 1,000 |
| English | 917 | 802 | 281 | 2,000 |
| **Total** | **1,463** | **1,076** | **461** | **3,000** |

### Images

| Language | Safe | Implicit Harmful | Explicit Harmful | Total |
|---|---:|---:|---:|---:|
| Arabic | 771 | 681 | 852 | 2,304 |
| English | 2,286 | 1,154 | 261 | 3,701 |
| **Total** | **3,057** | **1,835** | **1,113** | **6,005** |

### Videos

| Language | Safe | Implicit Harmful | Explicit Harmful | Total |
|---|---:|---:|---:|---:|
| Arabic | 25 | 171 | 121 | 317 |
| English | 83 | 403 | 47 | 533 |
| Universal | 57 | 269 | 26 | 352 |
| **Total** | **165** | **843** | **194** | **1,202** |

Across all modalities, the benchmark contains **10,207 samples**: **4,685 Safe**, **3,754 Implicit Harmful**, and **1,768 Explicit Harmful**.

### Arabic Text Variety Composition

The 1,000-item Arabic text subset is labeled by its predominant variety or intended target audience.

| Arabic variety | Count | Percentage |
|---|---:|---:|
| Egyptian | 399 | 39.9% |
| General Arabic | 262 | 26.2% |
| Levantine | 149 | 14.9% |
| Gulf | 105 | 10.5% |
| Modern Standard Arabic (MSA) | 65 | 6.5% |
| Iraqi | 20 | 2.0% |
| **Total** | **1,000** | **100.0%** |

**General Arabic** denotes jokes associated with a broad Arabic-speaking audience rather than one specific regional variety. These categories describe the predominant variety and intended audience; they should not be interpreted as rigid linguistic boundaries.

## Main Findings

The evaluation in the paper reveals several consistent patterns:

- Closed-source systems generally outperform open-source systems across modalities.
- Models perform better on English than on Arabic, particularly for dialect-rich and culturally grounded examples.
- Explicit harmful content is generally easier to detect than implicit harmful content.
- Some open-source vision-language models collapse to predicting **Safe**, producing near-zero harmful recall despite superficially acceptable accuracy on imbalanced splits.
- Video remains particularly challenging because successful classification may require joint temporal, visual, OCR, and audio reasoning.
- Model scale alone does not resolve the problem: culturally grounded reasoning and better safety calibration remain necessary.


## Data Access and Redistribution

The benchmark contains two distinct intellectual-property layers:

1. **The benchmark layer:** the annotation taxonomy, labels, benchmark splits, documentation, and researcher-produced metadata.
2. **Upstream content:** the original text, images, and videos, which remain governed by their original licenses or platform terms.

Availability therefore differs by item:

- Permissively licensed media may be redistributed with its original attribution and license information.
- Some media may be represented only through metadata or source identifiers.
- Media derived from **D-HUMOR** is not redistributed in this repository. Researchers must obtain those files through the D-HUMOR authors' official access process; this repository provides only the corresponding derived annotations and metadata.

Always consult the per-item provenance and license metadata before copying, redistributing, or publishing benchmark content.

## Responsible Use

This dataset is released for **non-commercial academic research**, particularly research on multimodal safety evaluation, harmful-content detection, multilingual robustness, culturally grounded reasoning, and model calibration.

Do not use the benchmark to:

- generate or amplify harmful content;
- harass, demean, profile, or target individuals or communities;
- build systems intended to evade safety mechanisms;
- redistribute upstream media in violation of its original license or platform terms; or
- present benchmark labels as universal moral judgments independent of culture and context.

Researchers should consider exposure risks for people reviewing the data, document safeguards in user studies, and avoid reproducing sensitive examples unnecessarily in publications or demonstrations.


## License

The benchmark's original contributions—including its annotation taxonomy, labels, schema, splits, documentation, and researcher-produced metadata—are released under the **Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International (CC BY-NC-SA 4.0)** license.

This license does **not** replace or override the licenses and terms governing upstream text, images, or videos. Each upstream item remains subject to its original license or platform terms. Consult the accompanying provenance metadata before reuse.

## Citation

Please cite the paper when using the benchmark. The attached manuscript identifies the title and authors but does not provide final proceedings metadata, so update `VENUE`, `YEAR`, and `PAPER_URL` before publishing the repository.

```bibtex
@inproceedings{sharsharYEARharmorhumor,
  title     = {Harm or Humor: A Multimodal, Multilingual Benchmark for Overt and Covert Harmful Humor},
  author    = {Sharshar, Ahmed and Elgendy, Hosam and Rohaim, Yasser and Ahmed, Saad El Dine and Wang, Yuxia},
  booktitle = {emnlp},
  year      = {2026},
  url       = {PAPER_URL}
}
```

## Authors and Contact

For dataset questions, access issues, or removal requests:

- `ahmed.sharshar@mbzuai.ac.ae`
- `hosam.elgendy@mbzuai.ac.ae`

---

This repository is intended to support safer, more culturally grounded evaluation of multimodal AI systems. Please use the data carefully and responsibly.
