# <img src="img/logo.png" style="vertical-align: -10px;" :height="40px" width="40px"> SAM2Long
This repository is the official implementation of SAM2Long.
<img align="center" src="img/pipeline.png" style="  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 100%;" />

<p align="center" style="font-size: em; margin-top: 0.5em">

[![License: CC BY-NC 4.0](https://img.shields.io/badge/License-CC_BY--NC_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc/4.0/)<br>
<a href="https://arxiv.org/abs/xxxx"><img src="https://img.shields.io/badge/arXiv-<color>"></a>
<a href="https://mark12ding.github.io/project/SAM2Long/asset/images/paper.pdf"><img src="https://img.shields.io/badge/PDF-red"></a>
<a href="https://mark12ding.github.io/project/SAM2Long/"><img src="https://img.shields.io/badge/Project-Homepage-green"></a>
</p>



>[**SAM2Long: Enhancing SAM 2 for Long Video Segmentation with a Training-Free Memory Tree**](https://arxiv.org/abs/xxxxxx)<br>
> [Shuangrui Ding](https://mark12ding.github.io/), [Rui Qian](https://shvdiwnkozbw.github.io/), [Xiaoyi Dong](https://lightdxy.github.io/), [Pan Zhang](https://panzhang0212.github.io/)<br>
[Yuhang Zang](https://yuhangzang.github.io/), [Yuhang Cao](https://scholar.google.com/citations?user=sJkqsqkAAAAJ), [Yuwei Guo](https://guoyww.github.io/), [Dahua Lin](http://dahua.site/), [Jiaqi Wang](https://myownskyw7.github.io/)<br>
CUHK, Shanghai AI Lab

## 💡 Highlights

### 🔥 Enhanced Capability in Long-Term Video Segmentation

SAM2Long significantly improves upon SAM 2 by addressing **error accumulation** issue, particularly in challenging long-term video scenarios involving object occlusion and reappearance. With SAM2Long, the segmentation process becomes more resilient and accurate over time, maintaining strong performance even as objects are occluded or reappear in the video stream.

<img align="center" src="img/teaser.png" style="  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 100%;" />

### ⚡️ A Simple Training-free Memory Tree

SAM2Long introduces a **training-free** memory tree that effectively reduces the risk of error propagation over time. By maintaining diverse segmentation hypotheses and dynamically pruning less optimal paths as the video progresses, this approach enhances segmentation without the need for additional parameters or further training. It maximizes the potential of SAM 2 to deliver better results in complex video scenarios.

### 😮 Superior Performance Compared to SAM 2

SAM2Long pushes the performance limits of SAM 2 even further across various video object segmentation benchmarks, especially achieving an average improvement of 3 in $\mathcal{J} \& \mathcal{F}$ scores across all 24 head-to-head comparsions on long-term video datasets like SA-V and LVOS.


## 🚀 Main Results

### SAM 2.1 checkpoints
The table below provides a one-to-one comparison between SAM 2 and SAM2Long using the improved SAM 2.1 checkpoints.
|  Method  | Backbone | SA-V val ($\mathcal{J} \& \mathcal{F}$) | SA-V test ($\mathcal{J} \& \mathcal{F}$) | LVOS v2 ($\mathcal{J} \& \mathcal{F}$) |
| :------: | :--------: | :------: | :--------: | :--------: |
|  SAM 2   | Tiny   | 73.5 | 74.6 | 77.8 |
|  SAM2Long| Tiny   |  77.0 | 78.7 | 81.4 |
|  SAM 2   | Small   | 73.0 | 74.6  | 79.7 |
|  SAM2Long| Small  | 77.7 | 78.1 | 83.2 |
|  SAM 2   | Base+   | 75.4 | 74.6 |  80.2 |
|  SAM2Long| Base+   | 78.4 | 78.5 | 82.3 |
|  SAM 2   | Large   | 76.3 | 75.5 | 83.0 |
|  SAM2Long| Large   | 80.8 | 80.8 | 85.2 |

### SAM 2 checkpoints
The table below provides a one-to-one comparison between SAM 2 and SAM2Long using the SAM 2 checkpoints.

|  Method  | Backbone | SA-V val ($\mathcal{J} \& \mathcal{F}$) | SA-V test ($\mathcal{J} \& \mathcal{F}$) | LVOS v2 ($\mathcal{J} \& \mathcal{F}$) |
| :------: | :--------: | :------: | :--------: | :--------: |
|  SAM 2   | Tiny   | 75.1 | 76.3 | 81.6 |
|  SAM2Long| Tiny   | 78.9 | 79.0 | 82.4 |
|  SAM 2   | Small   | 76.9 | 76.9 | 82.1 |
|  SAM2Long| Small  | 79.6 | 80.4 | 84.3 |
|  SAM 2   | Base+   | 78.0 | 77.7 | 83.1 |
|  SAM2Long| Base+   | 80.5 | 80.8 | 85.2 |
|  SAM 2   | Large   | 78.6 | 79.6 | 84.0 |
|  SAM2Long| Large   | 81.1 | 81.2 | 85.3 |

## 🛠️ Usage

### Installation
Please follow the instruction of [official SAM 2 repo](https://github.com/facebookresearch/sam2?tab=readme-ov-file#installation).

### Download Checkpoints
All the model checkpoints can be downloaded by running:
```
bash
cd checkpoints && \
./download_ckpts.sh && \
cd ..
```

### Inference
The inference instruction is in [INFERENCE.md](tools/README.md).

### Evaluation

The evaluation code can be found [here](sav_dataset/README.md). 

To evaluate performance on seen and unseen categories in the LVOS dataset, refer to the evaluation code available [here](https://github.com/LingyiHongfd/lvos-evaluation).

## ☎️ Contact
Shuangrui Ding: mark12ding@gmail.com


## 🔒 License
The majority of this project is released under the CC-BY-NC 4.0 license as found in the LICENSE file. The original SAM 2 model checkpoints and SAM 2 training code are licensed under [Apache 2.0](https://github.com/facebookresearch/sam2/blob/main/LICENSE).


## 👍 Acknowledgements
I would like to thank [Yixuan Wang](https://wangyixuan12.github.io/) for his assistance with dataset preparation and [Haohang Xu](https://scholar.google.com/citations?user=9nqZkmUAAAAJ) for his insightful disscusion.

This project is built upon [SAM 2](https://github.com/facebookresearch/sam2) and the format of this README is inspired by [VideoMAE](https://github.com/MCG-NJU/VideoMAE/blob/main/README.md).

<!-- ## ✒️ Citation
If you find our work helpful for your research, please consider giving a star ⭐ and citation 📝
```bibtex
``` -->

