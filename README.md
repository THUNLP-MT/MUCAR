# MUCAR: Benchmarking Multilingual Cross-Modal Ambiguity Resolution for Multimodal Large Language Models

📖 **Paper:** [MUCAR: Benchmarking Multilingual Cross-Modal Ambiguity Resolution for Multimodal Large Language Models](https://aclanthology.org/2025.emnlp-main.760/)
🏆 **EMNLP 2025**

This repository contains the dataset for the paper **MUCAR: Benchmarking Multilingual Cross-Modal Ambiguity Resolution for Multimodal Large Language Models**.

## Introduction

Multimodal Large Language Models (MLLMs) have demonstrated strong capabilities in understanding image-text pairs with clear meanings. However, resolving inherent ambiguities in natural language and visual contexts remains challenging.

We introduce **MUCAR**, a multilingual cross-modal ambiguity resolution benchmark designed to systematically evaluate the ability of MLLMs to resolve ambiguity through interactions between visual and textual information.

MUCAR contains **1,278 manually curated samples** in **Chinese, English, and Malay**, and covers two major ambiguity settings:

* **Multilingual Ambiguity Resolution**: ambiguous textual expressions are uniquely resolved by corresponding visual contexts.
* **Dual-Ambiguity Resolution**: both the image and textual context are ambiguous individually, while their combination yields a unique interpretation through cross-modal mutual disambiguation.

We evaluate **19 state-of-the-art MLLMs**, including both proprietary and open-source models. Experimental results reveal a substantial gap between current MLLMs and human-level performance in multilingual and cross-modal ambiguity resolution.
![MUCAR Topfig](./fig2.pdf)
## Dataset

The benchmark annotations are provided in [`data-all.json`](./data-all.json).

The image data used in MUCAR can be downloaded from [🤗 Hugging Face](https://huggingface.co/datasets/kevindragon221/MUCAR).
![MUCAR Case](./case.pdf)
![MUCAR Case](./sta2.pdf)
Each instance contains an ambiguous textual expression, the corresponding visual context information, a question, candidate answers, the ground-truth answer, and annotation tags.

The main fields include:

```text
{ "id": 0, "question_id": 1, "image_id": "1-1", "sentence": "I saw the man with a telescope.", "question": "Please translate this sentence into Chinese.", "options": [ "A.我用望远镜看见一个男人。", "B.我看见一个手里拿着望远镜的男人。" ], "answer": "A.我用望远镜看见一个男人。", "tags": { "category": 3, "language": 2 } }
```

For the same ambiguous textual expression, different visual contexts may lead to different interpretations. Therefore, models are required to jointly reason over textual and visual information to determine the correct answer.

## Evaluation

MUCAR evaluates the ability of Multimodal Large Language Models to resolve ambiguity under multilingual and cross-modal settings.

We evaluate **19 representative MLLMs**, covering both proprietary and open-source models.

The experimental results show that even state-of-the-art MLLMs still exhibit significant limitations when resolving ambiguities that require fine-grained interaction between language and vision.

## Citation

If you find MUCAR useful for your research, please cite our paper:

```bibtex
@inproceedings{wang-etal-2025-mucar,
    title = "{MUCAR}: Benchmarking Multilingual Cross-Modal Ambiguity Resolution for Multimodal Large Language Models",
    author = "Wang, Xiaolong and
      Kang, Zhaolu and
      Zhai, Wangyuxuan and
      Lou, Xinyue and
      Lai, Yunghwei and
      Wang, Ziyue and
      Wang, Yawen and
      Huang, Kaiyu and
      Wang, Yile and
      Li, Peng and
      Liu, Yang",
    booktitle = "Proceedings of the 2025 Conference on Empirical Methods in Natural Language Processing",
    year = "2025",
    address = "Suzhou, China",
    publisher = "Association for Computational Linguistics",
    pages = "15026--15048",
    doi = "10.18653/v1/2025.emnlp-main.760"
}
```
