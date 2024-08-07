# Notice of PM2ECGCN

## Latest Information Updates

We sincerely appreciate your interest in our work and apologize for the delay schedule. *The review process for data disclosure has encountered numerous obstacles due to our partners’ data collation and sharing plan, as well as recent policy changes by local regulatory authorities.* Since we used patient data, we cannot fully ensure that the work released do not involve concerns raised by the reviewers and we must respect the concerns of our partners. Unfortunately, I have no influence on the review process and, like anyone, can only wait and see. We are truly sorry for any inconvenience this may cause.

**We hope the review process for publicly available will proceed, allowing to release this work.**

## Important Notice  

This work has been accepted by ESWA (Unfortunately, the hyperlink used to jump to this link is broken in published version. You can follow the project state in this repository...) This project's dataset (SXMU-2k) and models are currently undergoing ethical approval processes.The methodology proposed in this work has been discussed in detail in the paper, if you are in a hurry you can reproduce directly. Feel free to reach out with any questions you may have.

For the SXMU-2k dataset, we have permission to use it, but at this stage, we are unable to distribute it in compliance. Therefore, if the dataset is essential for your external validation, we can, under your request and authorization, use your method to test on this dataset and report the experimental results to you. We are willing to ensure your requests for intellectual property protection are met.

## Introduction

This work presents PM2ECGCN, a graph convolutional network framework with linear inference complexity. It leverages parallelized multi-lead ECG spatial-temporal structures generated independently from multi-center data then trains collectively with domain generalization in feature-sharing manner. PM2ECGCN tackles challenges in modeling multi-lead dependencies, bridging isolated data, managing data heterogeneity, and reducing computation expenses.
![FigureONE](https://image-oss-danielwangow.oss-cn-shanghai.aliyuncs.com/PM2ECGCN_1_ESWA.png)

## Requirements

- python == 3.7.12
- tensorflow == 2.20
- numpy == 1.19.2
- pandas == 1.1.4
- scikit_learn == 0.23.2

## Data Preparation

**Datasets**: The empirical evaluations are conducted with two public datasets and one external validation dataset.

- [**PTBXL**](https://physionet.org/content/ptb-xl/1.0.1/): PTB-XL is the largest public dataset with 21,837 clinical 12-lead ECG recordings from 18,885 patients, 10 seconds in length at 100 Hz, which covers diverse pathologies.
- [**ICBEB-2018**](http://2018.icbeb.org/Challenge.html): ICBEB comprise 6,877 ECG recordings of 6-60 seconds duration.
- **SXMU-2k**: SXMU-2k contains 2,136 annotated ECG recordings with same labels following the SCP-ECG standard identical to PTB-XL. It was collected with approval from Ethics Committee. The data are still under review for public release.

**Preprocess for Simulation**: we construct sub-datasets by randomly allocating public dataset with different volumes and label distributions to mimic real-world multi-center scenarios under various configurations.

## Benchmarking

**1. Baselines:** To validate PM2ECGCN’s performance, we compare with several state-of-the-art approaches:

- [**ResNet101**](https://github.com/helme/ecg_ptbxl_benchmarking): Widely used convolutional backbone for ECG diagnosis models due to strong image recognition and adaptation capability.
- [**Xresnet101**](https://github.com/helme/ecg_ptbxl_benchmarking): ResNet101 adaptation with enhancements, showing strong 12-lead ECG analysis on PTB-XL dataset.
- [**Mousavi et al.**](https://github.com/likith012/IMLE-Net): Combines CNN and long short-term memory (LSTM) units for automatic heartbeat classification, achieving significant outperformance.
- [**ECGNet**](https://github.com/likith012/IMLE-Net): End-to-end framework using robust deep neural network (DNN) for ECG feature extraction and classification, outperforming prior arts.
- [**IMLE-Net**](https://github.com/likith012/IMLE-Net): Leverages 12-lead ECG multi-channel information and learns patterns with beats, rhythm, and channel-level attention mechanism using CNN-LSTM architecture.

**2. Ablations:**

- Performance analysis of simulated centers.
- Distance measurement for physical cardiac graph.
- Module of domain generalization.
- Number of leads and their combinations.

## License

This source code is released under the MIT license, includde [here](LICENSE).
