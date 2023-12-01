
# PM2ECGCN: Parallelized Spatial-Temporal Structures of Multi-Lead ECG with Graph Convolution Network for Multi-Center Cardiac Disease Diagnosis

This codebase is the official implementation of "PM2ECGCN: Parallelized Spatial-Temporal Structures of Multi-Lead ECG with Graph Convolution Network for Multi-Center Cardiac Disease Diagnosis".

## Paper Status

Currently, the paper is under peer-review. **We apologize for the inconvenience as we are unable release all implenmentation now for ensuring the authorships**.

## Introduction

This work presents PM2ECGCN, a graph convolutional network framework with linear inference complexity. It leverages parallelized multi-lead ECG spatial-temporal structures generated independently from multi-center data then trains collectively with domain generalization in feature-sharing manner. PM2ECGCN tackles challenges in modeling multi-lead dependencies, bridging isolated data, managing data heterogeneity, and reducing computation expenses.

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
- **SXMU-2k**: SXMU-2k contains 2,136 annotated ECG recordings with same labels following the SCP-ECG standard identical to PTB-XL. It was collected with approval from Ethics Committee. The data is still under review for public release, but it will be available in less than a year.

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
