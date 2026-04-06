# Supplementary Update for Reviewer Nnk4

Unless otherwise noted, the default setting follows the main paper and supplementary material.

**Incremental extension setup.** Freeze the original ACR backbone, append **64 new trainable atoms** to the dictionary (**6.2%** of the 1024-atom dictionary), and fine-tune only the query projection layer. This updates **0.7% of total parameters** (**172K / 23.3M**) and requires **no index rebuilding**.

## R1: Incremental Dictionary Extension

| Transfer Pair | Domain Gap | Zero-shot Hit@K Drop ↑ | + Incremental Hit@K Drop ↑ | Gain Δ | Train Time |
|---|---:|---:|---:|---:|---:|
| IMDb → Amazon | Low | 0.41 | 0.42 | +0.01 | 44s |
| arXiv → MNLI | Mid | 0.21 | 0.72 | +0.51 | 65s |
| IMDb → BiosBias | High | -0.30 | -0.15 | +0.15 | 26s |

**Figure R1.** Incremental dictionary extension across representative transfer pairs.

![Figure R1. Incremental dictionary extension across representative transfer pairs.](./incremental_extension_heatmap_fixed.png)
