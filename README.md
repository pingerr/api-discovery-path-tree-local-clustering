# Dataset and Baseline Materials for API‑Discovery‑Based‑on‑Path‑Tree‑Local‑Clustering

Supporting materials for the paper **API Discovery Method Based on Local Clustering in Path Tree**.

> Due to commercial confidentiality restrictions, **the core source‑code implementation of the proposed algorithm is NOT released**.

## Brief Introduction
Runtime traffic‑driven API discovery faces three key difficulties: distinguishing dynamic parameters from fixed business fields, confusing structurally‑similar interfaces, and high computational overhead caused by global clustering.

This paper proposes an API discovery method based on path‑tree local clustering. The path tree is built for hierarchical division of HTTP requests. On leaf‑node local regions, an attribute similarity graph is constructed, and similarity‑constrained density clustering is performed to obtain semantic request clusters. A two‑level generalization mechanism is adopted: rule‑driven pre‑generalization and secondary generalization according to intra‑cluster path‑fragment change rate, to generate final API path templates.

Experiments are conducted on public ATRDF dataset. The proposed method outperforms Speculator, MRG and HRAL in Precision, Recall and F1‑score. Ablation experiments verify the effectiveness of each key component.

## Dataset
We adopt public dataset **ATRDF(API Traffic Research Dataset Framework)**.
- Official address: https://github.com/ArielCyber/Cisco_Ariel_Uni_API_security_challenge
- In this paper, only normal business HTTP requests (108 252 samples) are adopted for evaluation; malicious attack traffic and static resource requests (CSS, JS, images) are discarded, malformed incomplete HTTP transactions are filtered out. Original URL paths are preserved for intra‑cluster path‑fragment change‑rate statistics.

## Baseline Methods
Three traffic‑driven API discovery baselines are compared in our paper. All baselines run with identical input traffic samples, parameters follow original papers or official repository default settings.

1. Speculator
Repository: https://github.com/openclarity/speculator

2. MRG
Paper: https://arxiv.org/abs/2604.19471

3. HRAL
Paper: https://arxiv.org/abs/2607.02442

## Citation
If you refer to materials in this repository, please cite this paper：
> todo
