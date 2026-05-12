# Awesome-Efficient-Large-Models

A curated list of papers on compression and acceleration of Large Language Models (LLMs) and Multimodal Large Language Models (MLLMs).

---

# Taxonomy

```
Efficient LLMs
├── Model-side Compression
│   ├── Quantization
│   ├── Pruning / Sparsity
│   ├── Knowledge Distillation
│   ├── Low-rank Decomposition
│   └── Efficient Architecture
├── Inference-side Acceleration
│   ├── Speculative Decoding
│   ├── KV Cache Optimization
│   ├── Prompt / Context Compression
│   ├── Early Exit
│   └── Adaptive Computation
├── Training and Fine-tuning Efficiency
│   ├── PEFT
│   ├── Quantized Fine-tuning
│   ├── Low-rank Gradient Training
│   └── Memory-efficient Training
├── System and Hardware Co-design
│   ├── Serving Systems
│   ├── Batching and Scheduling
│   ├── Kernel Optimization
│   ├── Compiler Optimization
│   └── Hardware-aware Deployment
└── Evaluation and Applications
    ├── Long-context Evaluation
    ├── Reasoning Robustness
    ├── Safety under Compression
    ├── Multimodal LLMs
    └── Edge Deployment
```

---

# Table of Contents

- [Model-side Compression](#model-side-compression)
  - [Quantization](#quantization)
    - [LLM Quantization](#llm-quantization)
    - [VLM Quantization](#vlm-quantization)
  - [Pruning / Sparsity](#pruning--sparsity)
    - [Unstructured Pruning](#unstructured-pruning)
    - [Semi-structured Pruning](#semi-structured-pruning)
    - [Structured Pruning](#structured-pruning)
    - [Activation Sparsity](#activation-sparsity)
    - [Joint Sparsification and Quantization](#joint-sparsification-and-quantization)
  - [Knowledge Distillation](#knowledge-distillation)
  - [Low-rank Decomposition](#low-rank-decomposition)
  - [Efficient Architecture](#efficient-architecture)
- [Inference-side Acceleration](#inference-side-acceleration)
  - [Speculative Decoding](#speculative-decoding)
  - [KV Cache Optimization](#kv-cache-optimization)
  - [Prompt / Context Compression](#prompt--context-compression)
  - [Early Exit](#early-exit)
  - [Adaptive Computation](#adaptive-computation)
- [Training and Fine-tuning Efficiency](#training-and-fine-tuning-efficiency)
  - [PEFT](#peft)
  - [Quantized Fine-tuning](#quantized-fine-tuning)
  - [Low-rank Gradient Training](#low-rank-gradient-training)
  - [Memory-efficient Training](#memory-efficient-training)
- [System and Hardware Co-design](#system-and-hardware-co-design)
  - [Serving Systems](#serving-systems)
  - [Batching and Scheduling](#batching-and-scheduling)
  - [Kernel Optimization](#kernel-optimization)
  - [Compiler Optimization](#compiler-optimization)
  - [Hardware-aware Deployment](#hardware-aware-deployment)
- [Evaluation and Applications](#evaluation-and-applications)
  - [Long-context Evaluation](#long-context-evaluation)
  - [Reasoning Robustness](#reasoning-robustness)
  - [Safety under Compression](#safety-under-compression)
  - [Multimodal LLMs](#multimodal-llms)
  - [Edge Deployment](#edge-deployment)

---

# Model-side Compression

## Quantization

### LLM Quantization
| Year | Title                                                                   | Venue   | Paper                                 | code                                                                                                                        |
| ---- | ----------------------------------------------------------------------- | :------ | ------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| 2023 | GPTQ: Accurate Post-Training Quantization for Generative Pre-trained Transformers | ICLR   2023 | [Link](https://arxiv.org/abs/2210.17323) |         [Link](https://github.com/IST-DASLab/gptq) ![](https://img.shields.io/github/stars/IST-DASLab/gptq.svg?style=social) |
| 2025 | OSTQuant: Refining Large Language Model Quantization with <br/>Orthogonal and Scaling Transformations for Better Distribution Fitting | ICLR   2025 | [Link](https://arxiv.org/abs/2405.16406) | [Link](https://github.com/BrotherHappy/OSTQuant) ![](https://img.shields.io/github/stars/BrotherHappy/OSTQuant.svg?style=social) |
| 2025 | SpinQuant: LLM quantization with learned rotations | ICLR   2025 | [Link](https://arxiv.org/abs/2501.13987) | [Link](https://github.com/facebookresearch/SpinQuant) ![](https://img.shields.io/github/stars/facebookresearch/SpinQuant.svg?style=social) |
| 2022 | SmoothQuant: Accurate and Efficient Post-Training Quantization for Large Language Models | ICML  2023 | [Link](https://arxiv.org/abs/2211.10438) | [Link](https://github.com/mit-han-lab/smoothquant) ![](https://img.shields.io/github/stars/mit-han-lab/smoothquant.svg?style=social) |
| 2023 | AWQ: Activation-aware Weight Quantization for LLM Compression and Acceleration | MLSys 2024 | [Link](https://arxiv.org/abs/2306.00978) | [Link](https://github.com/mit-han-lab/llm-awq) ![](https://img.shields.io/github/stars/mit-han-lab/llm-awq.svg?style=social) |
| 2024 | QuIP#: Even Better LLM Quantization with Hadamard Incoherence and Lattice Codebooks | ICML  2024 | [Link](https://arxiv.org/abs/2402.04396) | [Link](https://github.com/Cornell-RelaxML/quip-sharp) ![](https://img.shields.io/github/stars/Cornell-RelaxML/quip-sharp.svg?style=social) |
| 2025 | QServe: W4A8KV4 Quantization and System Co-design for Efficient LLM Serving | MLSys 2025 | [Link](https://arxiv.org/abs/2405.04532) |  [Link](https://github.com/mit-han-lab/omniserve) ![](https://img.shields.io/github/stars/mit-han-lab/omniserve.svg?style=social) |
| 2024 | QuaRot: Outlier-Free 4-Bit Inference in Rotated LLMs         | NeurIPS 2024 | [Link](https://arxiv.org/abs/2404.00456) |[Link](https://github.com/spcl/QuaRot)![](https://img.shields.io/github/stars/spcl/QuaRot.svg?style=social)|
| 2024 | Atom: Low-bit Quantization for Efficient and Accurate LLM Serving | MLSys 2024 | [Link](https://arxiv.org/abs/2404.00456) |[Link](https://github.com/efeslab/Atom)![](https://img.shields.io/github/stars/efeslab/Atom.svg?style=social) |
| 2024 | OmniQuant: Omnidirectionally Calibrated Quantization for Large Language Models | ICLR 2024 | [Link](https://arxiv.org/abs/2308.13137) |[Link](https://github.com/OpenGVLab/OmniQuant)![](https://img.shields.io/github/stars/OpenGVLab/OmniQuant.svg?style=social)|
| 2023 | QuIP: 2-Bit Quantization of Large Language Models With Guarantees | NeurIPS 2023 | [Link](https://arxiv.org/abs/2307.13304) | [Link](https://github.com/AlpinDale/QuIP-for-Llama?tab=readme-ov-file)![](https://img.shields.io/github/stars/AlpinDale/QuIP-for-Llama.svg?style=social) |
| 2022 | LLM.int8(): 8-bit Matrix Multiplication for Transformers at Scale | NeurIPS 2022 | [Link](https://arxiv.org/abs/2208.07339) | [Link](https://github.com/tloen/llama-int8)![](https://img.shields.io/github/stars/tloen/llama-int8.svg?style=social) |
| 2023 | Outlier Suppression+: Accurate quantization of large language models by equivalent and optimal shifting and scaling | EMNLP 2023 | [Link](https://arxiv.org/abs/2304.09145) | [Link](https://github.com/ModelTC/Outlier_Suppression_Plus)![](https://img.shields.io/github/stars/ModelTC/Outlier_Suppression_Plus.svg?style=social) |
| 2025 | GPTAQ: Efficient Finetuning-Free Quantization for Asyetric Calibration | ICML 2025 | [Link](https://arxiv.org/pdf/2504.02692) | [Link](https://github.com/Intelligent-Computing-Lab-Panda/GPTAQ)![](https://img.shields.io/github/stars/Intelligent-Computing-Lab-Panda/GPTAQ.svg?style=social) |
| 2024 | MagR: Weight Magnitude Reduction for Enhancing Post-Training Quantization | NeurIPS 2024 | [Link](https://arxiv.org/abs/2406.00800) | [Link](https://github.com/AozhongZhang/MagR)![](https://img.shields.io/github/stars/AozhongZhang/MagR.svg?style=social) |
| 2024 | AffineQuant: Affine Transformation Quantization for Large Language Models | ICLR 2024 | [Link](https://arxiv.org/pdf/2403.12544) |[Link](https://github.com/bytedance/AffineQuant)![](https://img.shields.io/github/stars/bytedance/AffineQuant.svg?style=social)|
| 2024 |LLM-QAT: Data-Free Quantization Aware Training for Large Language Models|ACL 2024|[Link](https://arxiv.org/pdf/2305.17888)|[Link](https://github.com/facebookresearch/LLM-QAT)![](https://img.shields.io/github/stars/facebookresearch/LLM-QAT.svg?style=social)|
| 2024 | BitDistiller: Unleashing the Potential of Sub-4-Bit LLMs via Self-Distillation | ACL 2024 | [Link](https://arxiv.org/abs/2402.10631) | [Link](https://github.com/DD-DuDa/BitDistiller)![](https://img.shields.io/github/stars/DD-DuDa/BitDistiller.svg?style=social) |
| 2023 | OWQ: Outlier-Aware Weight Quantization for Efficient Fine-Tuning and Inference of Large Language Models | AAAI 2024 (Oral) | [Link](https://arxiv.org/abs/2306.02272) | [Link](https://github.com/xvyaward/owq)![](https://img.shields.io/github/stars/xvyaward/owq.svg?style=social) |
| 2024 | SpQR: A Sparse-Quantized Representation for Near-Lossless LLM Weight Compression | ICLR 2024 | [Link](https://arxiv.org/abs/2306.03078) | [Link](https://github.com/Vahe1994/SpQR)![](https://img.shields.io/github/stars/Vahe1994/SpQR.svg?style=social) |
| 2022 | ZeroQuant: Efficient and Affordable Post-Training Quantization for Large-Scale Transformers | NeurIPS 2022 | [Link](https://arxiv.org/abs/2206.01861) | [Link](https://github.com/microsoft/DeepSpeed)![](https://img.shields.io/github/stars/microsoft/DeepSpeed.svg?style=social) |
| 2024 | LUT-GEMM: Quantized Matrix Multiplication based on LUTs for Efficient Inference in Large-Scale Generative Language Models | ICLR 2024        | [Link](https://arxiv.org/abs/2206.09557) | [Link](https://github.com/naver-aics/lut-gemm)![](https://img.shields.io/github/stars/naver-aics/lut-gemm.svg?style=social) |
| 2024 | OneBit: Towards Extremely Low-bit Large Language Models | NeurIPS 2024 | [Link](https://arxiv.org/abs/2402.11295) | [Link](https://github.com/xuyuzhuang11/OneBit)![](https://img.shields.io/github/stars/xuyuzhuang11/OneBit.svg?style=social) |
| 2023 | LLM-FP4: 4-bit Floating-Point Quantized Transformers | EMNLP 2023 | [Link](https://arxiv.org/abs/2310.16836) | [Link](https://github.com/nbasyl/LLM-FP4)![](https://img.shields.io/github/stars/nbasyl/LLM-FP4.svg?style=social) |
| 2024 | FlatQuant: Flatness Matters for LLM Quantization | ICML 2025 | [Link](https://arxiv.org/pdf/2410.09426) | [Link](https://github.com/ruikangliu/FlatQuant)![](https://img.shields.io/github/stars/ruikangliu/FlatQuant.svg?style=social) |
| 2024 | SqueezeLLM: Dense-and-Sparse Quantization | ICML 2024 | [Link](https://arxiv.org/pdf/2306.07629) | [Link](https://github.com/SqueezeAILab/SqueezeLLM)![](https://img.shields.io/github/stars/SqueezeAILab/SqueezeLLM.svg?style=social) |
| 2023 | RPTQ: Reorder-based Post-training Quantization for Large Language Models |  | [Link](https://arxiv.org/pdf/2304.01089) | [Link](https://github.com/hahnyuan/RPTQ4LLM)![](https://img.shields.io/github/stars/hahnyuan/RPTQ4LLM.svg?style=social) |
| 2024 | QQQ: Quality Quattuor-Bit Quantization for Large Language Models | ICLR | [Link](https://arxiv.org/pdf/2406.09904) | [Link](https://github.com/HandH1998/QQQ)![](https://img.shields.io/github/stars/HandH1998/QQQ.svg?style=social) |
| 2024 | Mitigating Quantization Errors Due to Activation Spikes in GLU-Based LLMs |                  | [Link](https://arxiv.org/pdf/2405.14428) | [Link](https://github.com/onnoo/activation-spikes)![](https://img.shields.io/github/stars/onnoo/activation-spikes.svg?style=social) |
| 2025 | CBQ: Cross-Block Quantization for Large Language Models | ICLR 2025 | [Link](https://openreview.net/forum?id=eW4yh6HKz4) | N/A |
| 2025 | MambaQuant: Quantizing the Mamba Family with Variance Aligned Rotation Methods | ICLR 2025 | [Link](https://arxiv.org/abs/2501.13484) | N/A |
| 2025 | SeedLM: Compressing LLM Weights into Seeds of Pseudo-Random Generators | ICLR 2025 | [Link](https://openreview.net/forum?id=u3TL0qxLWf) | N/A |
| 2025 | Progressive Mixed-Precision Decoding for Efficient LLM Inference | ICLR 2025 | [Link](https://openreview.net/forum?id=OVxmpus9NA) | N/A |
| 2025 | Surprising Effectiveness of Pretraining Ternary Language Models at Scale | ICLR 2025 | [Link](https://openreview.net/forum?id=TJo6aQb7mK) | N/A |
| 2025 | EfficientQAT: Efficient Quantization-Aware Training for Large Language Models | ACL 2025 | [Link](https://arxiv.org/abs/2407.11062) | [Link](https://github.com/WHJang-0421/EfficientQAT) ![](https://img.shields.io/github/stars/WHJang-0421/EfficientQAT.svg?style=social) |
| 2025 | MiniKV: Pushing the Limits of 2-Bit KV Cache via Compression and System Co-Design for Efficient Long Context Inference | ACL 2025 Findings | [Link](https://aclanthology.org/2025.findings-acl.952/) | N/A |
| 2025 | AsymKV: Enabling 1-Bit Quantization of KV Cache with Layer-Wise Asymmetric Quantization Configurations | ACL 2025 | [Link](https://arxiv.org/abs/2410.13212) | N/A |
| 2025 | Assigning Distinct Roles to Quantized and Low-Rank Matrices Toward Optimal Weight Decomposition | ACL 2025 Findings | [Link](https://arxiv.org/abs/2506.02077) | N/A |
| 2025 | LittleBit: Ultra Low-Bit Quantization via Latent Factorization | NeurIPS 2025 | [Link](https://arxiv.org/abs/2506.13771) | [Link](https://github.com/SamsungLabs/LittleBit) ![](https://img.shields.io/github/stars/SamsungLabs/LittleBit.svg?style=social) |
| 2024 | Extreme Compression of Large Language Models via Additive Quantization | ICML 2024 | [Link](https://icml.cc/virtual/2024/poster/34964) | [Link](https://github.com/Vahe1994/AQLM) ![](https://img.shields.io/github/stars/Vahe1994/AQLM.svg?style=social) |
| 2024 | BiLLM: Pushing the Limit of Post-Training Quantization for LLMs | ICML 2024 | [Link](https://proceedings.mlr.press/v235/huang24q.html) | [Link](https://github.com/Ce-daros/BiLLM) ![](https://img.shields.io/github/stars/Ce-daros/BiLLM.svg?style=social) |
| 2024 | LQER: Low-Rank Quantization Error Reconstruction for LLMs | ICML 2024 | [Link](https://arxiv.org/abs/2402.02446) | N/A |
| 2024 | Evaluating Quantized Large Language Models | ICML 2024 | [Link](https://arxiv.org/abs/2402.18158) | [Link](https://github.com/thu-nics/qllm-eval) ![](https://img.shields.io/github/stars/thu-nics/qllm-eval.svg?style=social) |
| 2024 | QMoE: Sub-1-Bit Compression of Trillion Parameter Models | MLSys 2024 | [Link](https://proceedings.mlsys.org/paper_files/paper/2024/hash/c74b624843218d9b6713fcf299d6d5e4-Abstract-Conference.html) | [Link](https://github.com/mlsys24-qmoe/qmoe) ![](https://img.shields.io/github/stars/mlsys24-qmoe/qmoe.svg?style=social) |
| 2024 | DuQuant: Distributing Outliers via Dual Transformation Makes Stronger Quantized LLMs | NeurIPS 2024 | [Link](https://arxiv.org/abs/2406.01721) | [Link](https://github.com/Hsu1023/DuQuant) ![](https://img.shields.io/github/stars/Hsu1023/DuQuant.svg?style=social) |
| 2024 | QBB: Quantization with Binary Bases for LLMs | NeurIPS 2024 | [Link](https://openreview.net/forum?id=Kw6MRGFx0R) | N/A |
| 2024 | Cherry on Top: Parameter Heterogeneity and Quantization in Large Language Models | NeurIPS 2024 | [Link](https://papers.nips.cc/paper_files/paper/2024/hash/6fcc2190f456464160921e98393bf50e-Abstract-Conference.html) | N/A |
| 2024 | VPTQ: Extreme Low-bit Vector Post-Training Quantization for Large Language Models | EMNLP 2024 | [Link](https://aclanthology.org/2024.emnlp-main.467/) | [Link](https://github.com/paperwave/VPTQ) ![](https://img.shields.io/github/stars/paperwave/VPTQ.svg?style=social) |


### VLM Quantization
| Year | Title                                                                   | Venue   | Paper                                 | code                                                                                                                        |
| ---- | ----------------------------------------------------------------------- | ------- | ------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| 2024 | Q-VLM: Post-training Quantization for Large Vision Language Models      | NIPS 2024 | [Link](https://arxiv.org/pdf/2410.08119) | [Link](https://github.com/ChangyuanWang17/QVLM) ![](https://img.shields.io/github/stars/ChangyuanWang17/QVLM.svg?style=social) |
| 2025 | MBQ:Modality-Balanced Quantization for Large Vision-Language Models     | CVPR 2025 | [Link](https://arxiv.org/pdf/2412.19509) | [Link](https://github.com/thu-nics/MBQ) ![](https://img.shields.io/github/stars/thu-nics/MBQ.svg?style=social) |
| 2025 | MQuant: Unleashing the Inference Potential of Multimodal Large Language Models via Full Static Quantization     | ACM MM 2025 | [Link](https://arxiv.org/pdf/2502.00425) | [Link](https://github.com/StiphyJay/MQuant) ![](https://img.shields.io/github/stars/StiphyJay/MQuant.svg?style=social) |
| 2025 | CASP: Compression of Large Multimodal Models Based on Attention Sparsity     | CVPR 2025 | [Link](https://arxiv.org/pdf/2503.05936) | [Link](https://github.com/vbdi/casp) ![](https://img.shields.io/github/stars/vbdi/casp.svg?style=social) |
| 2024 | Advancing Multimodal Large Language Models with Quantization-Aware Scale Learning for Efficient Adaptation | ACM MM 2024 | [Link](https://arxiv.org/abs/2408.03735) | N/A |

---

## Pruning / Sparsity

### Unstructured Pruning

#### Pruning without Weight Update
| Year | Title                                                                   | Venue   | Paper                                 | code                                                                                                                     |
| ---- | ----------------------------------------------------------------------- | ------- | ------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| 2023 | A Simple and Effective Pruning Approach for Large Language Models | ICLR 2024| [Link](https://arxiv.org/abs/2306.11695) |         [Link](https://github.com/locuslab/wanda) ![](https://img.shields.io/github/stars/locuslab/wanda.svg?style=social) |
| 2024 | BESA: Pruning Large Language Models with Blockwise Parameter-Efficient Sparsity Allocation| ICLR 2024| [Link](https://arxiv.org/abs/2402.16880) |         [Link](https://github.com/OpenGVLab/LLMPrune-BESA) ![](https://img.shields.io/github/stars/OpenGVLab/LLMPrune-BESA.svg?style=social) |
| 2024 |COPAL: Continual Pruning in Large Language Generative Models| ICML 2024| [Link](https://arxiv.org/abs/2405.02347) |N/A|
| 2024 |Pruner-Zero: Evolving Symbolic Pruning Metric from scratch for Large Language Models| ICML 2024| [Link](https://arxiv.org/abs/2406.02924) |[Link](https://github.com/pprp/Pruner-Zero) ![](https://img.shields.io/github/stars/pprp/Pruner-Zero.svg?style=social) |
| 2025 |BaWA: Automatic Optimizing Pruning Metric for Large Language Models with Balanced Weight and Activation|ICML 2025| [Link](https://openreview.net/forum?id=YrCvW1Hx7g) |N/A |
| 2025 |SAFE: Finding Sparse and Flat Minima to Improve Pruning|ICML 2025| [Link](https://arxiv.org/abs/2506.06866) |[Link](https://github.com/LOG-postech/safe-torch) ![](https://img.shields.io/github/stars/LOG-postech/safe-torch.svg?style=social) |
| 2025 |SwiftPrune: Hessian-Free Weight Pruning for Large Language Models|EMNLP 2025 Findings| [Link](https://arxiv.org/abs/2501.16376) |N/A |

#### Pruning with Weight Update
| Year | Title                                                                   | Venue   | Paper                                 | code                                                                                                                     |
| ---- | ----------------------------------------------------------------------- | ------- | ------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| 2023 | SparseGPT: Massive Language Models Can Be Accurately Pruned in One-Shot | ICML 2023| [Link](https://arxiv.org/pdf/2301.00774) |         [Link](https://github.com/IST-DASLab/sparsegpt) ![](https://img.shields.io/github/stars/IST-DASLab/sparsegpt.svg?style=social) |
| 2023 | Dynamic Sparse No Training: Training-Free Fine-tuning for Sparse LLMs | ICLR 2024| [Link](https://arxiv.org/abs/2310.08915) |         [Link](https://github.com/zyxxmu/DSnoT) ![](https://img.shields.io/github/stars/zyxxmu/DSnoT.svg?style=social) |
| 2023 |The LLM Surgeon| ICLR 2024| [Link](https://arxiv.org/pdf/2312.17244) |         [Link](https://github.com/Qualcomm-AI-research/llm-surgeon) ![](https://img.shields.io/github/stars/Qualcomm-AI-research/llm-surgeon.svg?style=social) |
| 2024 |Fast and Optimal Weight Update for Pruned Large Language Models| TMLR 2024| [Link](https://arxiv.org/abs/2401.02938) |[Link](https://github.com/fmfi-compbio/admm-pruning) ![](https://img.shields.io/github/stars/fmfi-compbio/admm-pruning.svg?style=social) |
| 2024 |Pruning Foundation Models for High Accuracy without Retraining|EMNLP 2024 findings| [Link](https://arxiv.org/abs/2410.15567) |[Link](https://github.com/piuzha/APT) ![](https://img.shields.io/github/stars/piuzha/APT.svg?style=social) |
| 2024 |SparseLLM: Towards Global Pruning for Pre-trained Language Models| NeurIPS 2024| [Link](https://arxiv.org/abs/2402.17946) |[Link](https://github.com/BaiTheBest/SparseLLM) ![](https://img.shields.io/github/stars/BaiTheBest/SparseLLM.svg?style=social) |
| 2024 |ALPS: Improved Optimization for Highly Sparse One-Shot Pruning for Large Language Models|NeurIPS 2024| [Link](https://arxiv.org/abs/2406.07831) |[Link](https://github.com/mazumder-lab/ALPS) ![](https://img.shields.io/github/stars/mazumder-lab/ALPS.svg?style=social) |
| 2024 |Shears: Unstructured Sparsity with Neural Low-rank Adapter Search| NAACL 2024| [Link](https://arxiv.org/abs/2404.10934) |[Link](https://github.com/IntelLabs/Hardware-Aware-Automated-Machine-Learning) ![](https://img.shields.io/github/stars/IntelLabs/Hardware-Aware-Automated-Machine-Learning.svg?style=social) |
| 2025 |Wanda++: Pruning Large Language Models via Regional Gradients|ACL 2025 Findings| [Link](https://arxiv.org/abs/2503.04992) |[Link](https://github.com/TTTTTTris/wandaplus) ![](https://img.shields.io/github/stars/TTTTTTris/wandaplus.svg?style=social) |
| 2024 |Two Sparse Matrices are Better than One: Sparsifying Neural Networks with Double Sparse Factorization|ICLR 2025| [Link](https://arxiv.org/abs/2409.18850) |[Link](https://github.com/usamec/double_sparse) ![](https://img.shields.io/github/stars/usamec/double_sparse.svg?style=social) |
| 2025 |Dynamic Low-Rank Sparse Adaptation for Large Language Models|ICLR 2025| [Link](https://arxiv.org/abs/2502.14816) |[Link](https://github.com/wzhuang-xmu/LoSA) ![](https://img.shields.io/github/stars/wzhuang-xmu/LoSA.svg?style=social) |
| 2024 |Wasserstein Distances, Neuronal Entanglement, and Sparsity|ICLR 2025| [Link](https://arxiv.org/abs/2405.15756) |[Link](https://github.com/Shavit-Lab/Sparse-Expansion) ![](https://img.shields.io/github/stars/Shavit-Lab/Sparse-Expansion.svg?style=social) |
| 2025 |Targeted Low-rank Refinement: Enhancing Sparse Language Models with Precision|ICML 2025| [Link](https://openreview.net/forum?id=S0ncZdwcLt) |N/A |
| 2025 |An Efficient Pruner for Large Language Model with Theoretical Guarantee|ICML 2025| [Link](https://openreview.net/forum?id=nh9mBCYeF7) |N/A |
| 2025 |DenoiseRotator: Enhance Pruning Robustness for LLMs via Importance Concentration|NeurIPS 2025| [Link](https://arxiv.org/abs/2505.23049) |[Link](https://github.com/Axel-gu/DenoiseRotator) ![](https://img.shields.io/github/stars/Axel-gu/DenoiseRotator.svg?style=social) |
| 2025 |Multi-Objective One-Shot Pruning for Large Language Models|NeurIPS 2025| [Link](https://openreview.net/forum?id=aNpj43Uh35) |N/A |

#### Sparsity Rate Allocation
| Year | Title                                                                   | Venue   | Paper                                 | code                                                                                                                     |
| ---- | ----------------------------------------------------------------------- | ------- | ------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| 2023 | Outlier Weighed Layerwise Sparsity (OWL): A Missing Secret Sauce for Pruning LLMs to High Sparsity| ICML 2024| [Link](https://arxiv.org/abs/2310.05175) |         [Link](https://github.com/luuyin/OWL) ![](https://img.shields.io/github/stars/luuyin/OWL.svg?style=social) |
| 2024 |ALS: Adaptive Layer Sparsity for Large Language Models via Activation Correlation Assessment|NeurIPS 2024| [Link](https://openreview.net/forum?id=Jup0qZxH7U) |[Link](https://github.com/lliai/ALS) ![](https://img.shields.io/github/stars/lliai/ALS.svg?style=social) |
| 2024 |Discovering Sparsity Allocation for Layer-wise Pruning of Large Language Models|NeurIPS 2024| [Link](https://openreview.net/forum?id=rgtrYVC9n4) |[Link](https://github.com/lliai/DSA) ![](https://img.shields.io/github/stars/lliai/DSA.svg?style=social) |
| 2024 |AlphaPruning: Using Heavy-Tailed Self Regularization Theory for Improved Layer-wise Pruning of Large Language Models|NeurIPS 2024| [Link](https://arxiv.org/abs/2410.10912) |[Link](https://github.com/haiquanlu/AlphaPruning) ![](https://img.shields.io/github/stars/haiquanlu/AlphaPruning.svg?style=social) |
| 2024 |EvoPress: Accurate Dynamic Model Compression via Evolutionary Search|ICML 2025| [Link](https://arxiv.org/abs/2410.14649) |[Link](https://github.com/IST-DASLab/EvoPress) ![](https://img.shields.io/github/stars/IST-DASLab/EvoPress.svg?style=social) |
| 2025 |Determining Layer-wise Sparsity for Large Language Models Through a Theoretical Perspective|ICML 2025| [Link](https://openreview.net/forum?id=otNB7BzsiR) |[Link](https://github.com/wzhuang-xmu/ATP) ![](https://img.shields.io/github/stars/wzhuang-xmu/ATP.svg?style=social) |
| 2025 |DLP: Dynamic Layerwise Pruning in Large Language Models|ICML 2025| [Link](https://arxiv.org/abs/2505.23807) | [Link](https://github.com/ironartisan/DLP) ![](https://img.shields.io/github/stars/ironartisan/DLP.svg?style=social)|
| 2025 |Lua-LLM: Learning Unstructured-Sparsity Allocation for Large Language Models|NeurIPS 2025| [Link](https://openreview.net/forum?id=CA1xVSvn72) |N/A |

#### Sparse plus Low-Rank Compression
| Year | Title                                                                   | Venue   | Paper                                 | code                                                                                                                     |
| ---- | ----------------------------------------------------------------------- | ------- | ------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| 2024 |OATS: Outlier-Aware Pruning Through Sparse and Low Rank Decomposition|ICLR 2025| [Link](https://arxiv.org/abs/2409.13652) |[Link](https://github.com/stephenqz/OATS) ![](https://img.shields.io/github/stars/stephenqz/OATS.svg?style=social) |
| 2025 |Pivoting Factorization: A Compact Meta Low-Rank Representation of Sparsity for Efficient Inference in Large Language Models|ICML 2025| [Link](https://arxiv.org/abs/2501.19090) |[Link](https://github.com/biomedical-cybernetics/pivoting-factorization) ![](https://img.shields.io/github/stars/biomedical-cybernetics/pivoting-factorization.svg?style=social) |
| 2025 |1+1>2: A Synergistic Sparse and Low-Rank Compression Method for Large Language Models|EMNLP 2025| [Link](https://arxiv.org/abs/2510.26446) |[Link](https://github.com/mazumder-lab/3BASiL) ![](https://img.shields.io/github/stars/mazumder-lab/3BASiL.svg?style=social) |
| 2025 |3BASiL: An Algorithmic Framework for Sparse plus Low-Rank Compression of LLMs|NeurIPS 2025| [Link](https://openreview.net/forum?id=byNNv5Et10) |[Link](https://github.com/mazumder-lab/3BASiL) ![](https://img.shields.io/github/stars/mazumder-lab/3BASiL.svg?style=social) |

#### Calibration Dataset
| Year | Title                                                                   | Venue   | Paper                                 | code                                                                                                                     |
| ---- | ----------------------------------------------------------------------- | ------- | ------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| 2024 |On the Impact of Calibration Data in Post-training Quantization and Pruning| ACL 2024| [Link](https://aclanthology.org/2024.acl-long.544) |         [Link](https://github.com/mlsw/llm-compression-calibration) ![](https://img.shields.io/github/stars/mlsw/llm-compression-calibration.svg?style=social) |
| 2024 |Is C4 Dataset Optimal for Pruning? An Investigation of Calibration Data for LLM Pruning|EMNLP 2024| [Link](https://arxiv.org/abs/2410.07461) |[Link](https://github.com/abx393/llm-pruning-calibration-data) ![](https://img.shields.io/github/stars/abx393/llm-pruning-calibration-data.svg?style=social) |
| 2024 |Beware of Calibration Data for Pruning Large Language Models|ICLR 2025| [Link](https://arxiv.org/abs/2410.17711) |[Link](https://github.com/Dereck0602/calibration_data) ![](https://img.shields.io/github/stars/Dereck0602/calibration_data.svg?style=social) |

#### Evaluation of Pruned Model
| Year | Title                                                                   | Venue   | Paper                                 | code                                                                                                                     |
| ---- | ----------------------------------------------------------------------- | ------- | ------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| 2023 | Compressing LLMs: The Truth is Rarely Pure and Never Simple| ICLR 2024| [Link](https://arxiv.org/abs/2310.01382) |         [Link](https://github.com/VITA-Group/llm-kick) ![](https://img.shields.io/github/stars/VITA-Group/llm-kick.svg?style=social) |
| 2025 | Can Compressed LLMs Truly Act? An Empirical Evaluation of Agentic Capabilities in LLM Compresssion | ICML 2025| [Link](https://arxiv.org/abs/2505.19433) |         [Link](https://github.com/pprp/ACBench) ![](https://img.shields.io/github/stars/pprp/ACBench.svg?style=social) |
| 2025 |Pruning Weights but Not Truth: Safeguarding Truthfulness While Pruning LLMs|EMNLP 2025 Findings| [Link](https://arxiv.org/abs/2509.00096) |N/A |

### Semi-structured Pruning
| Year | Title                                                                   | Venue   | Paper                                 | code                                                                                                                     |
| ---- | ----------------------------------------------------------------------- | ------- | ------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| 2024 |WRP: Weight Recover Prune for Structured Sparsity| ACL 2024| [Link](https://aclanthology.org/2024.acl-long.347) |         [Link](https://github.com/TanZhendong/WRP) ![](https://img.shields.io/github/stars/TanZhendong/WRP.svg?style=social) |
| 2024 |Plug-and-Play: An Efficient Post-training Pruning Method for Large Language Models| ICLR 2024| [Link](https://openreview.net/forum?id=Tr0lPx9woF) |         [Link](https://github.com/biomedical-cybernetics/Relative-importance-and-activation-pruning) ![](https://img.shields.io/github/stars/biomedical-cybernetics/Relative-importance-and-activation-pruning.svg?style=social) |
| 2024 |Pruning Large Language Models with Semi-Structural Adaptive Sparse Training|AAAI 2025| [Link](https://arxiv.org/abs/2407.20584) |[Link](https://github.com/thu-ml/Adaptive-Sparse-Trainer) ![](https://img.shields.io/github/stars/thu-ml/Adaptive-Sparse-Trainer.svg?style=social) |
| 2024 |MaskLLM: Learnable Semi-Structured Sparsity for Large Language Models|NeurIPS 2024| [Link](https://arxiv.org/abs/2409.17481) |[Link](https://github.com/NVlabs/MaskLLM) ![](https://img.shields.io/github/stars/NVlabs/MaskLLM.svg?style=social) |
| 2025 | ProxSparse: Regularized Learning of Semi-Structured Sparsity Masks for Pretrained LLMs|ICML 2025| [Link](https://arxiv.org/abs/2502.00258) |[Link](https://github.com/amazon-science/ProxSparse) ![](https://img.shields.io/github/stars/amazon-science/ProxSparse.svg?style=social) |
| 2025 |PermLLM: Learnable Channel Permutation for N:M Sparse Large Language Models|NeurIPS 2025| [Link](https://arxiv.org/abs/2510.10136) |[Link](https://github.com/lanchengzou/PermLLM) ![](https://img.shields.io/github/stars/lanchengzou/PermLLM.svg?style=social) |
| 2025 |TSENOR: Highly-Efficient Algorithm for Finding Transposable N:M Sparse Masks|NeurIPS 2025| [Link](https://arxiv.org/abs/2505.23949) |[Link](https://github.com/mazumder-lab/TSENOR) ![](https://img.shields.io/github/stars/mazumder-lab/TSENOR.svg?style=social) |

### Structured Pruning

#### Head and Neuron Pruning
| Year | Title                                                                   | Venue   | Paper                                 | code                                                                                                                     |
| ---- | ----------------------------------------------------------------------- | ------- | ------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| 2023 |LLM-Pruner: On the Structural Pruning of Large Language Models| NeurIPS 2023| [Link](https://arxiv.org/abs/2305.11627) |  [Link](https://github.com/horseee/LLM-Pruner) ![](https://img.shields.io/github/stars/horseee/LLM-Pruner.svg?style=social) |
| 2023 |Fluctuation-based Adaptive Structured Pruning for Large Language Models| AAAI 2024| [Link](https://arxiv.org/abs/2312.11983) |         [Link](https://github.com/CASIA-IVA-Lab/FLAP) ![](https://img.shields.io/github/stars/CASIA-IVA-Lab/FLAP.svg?style=social) |
| 2023 |Sheared LLaMA: Accelerating Language Model Pre-training via Structured Pruning| ICLR 2024| [Link](https://arxiv.org/abs/2310.06694) |         [Link](https://github.com/princeton-nlp/LLM-Shearing) ![](https://img.shields.io/github/stars/princeton-nlp/LLM-Shearing.svg?style=social) |
| 2024 |BlockPruner: Fine-grained Pruning for Large Language Models| ACL 2025 Findings| [Link](https://arxiv.org/abs/2406.10594) |[Link](https://github.com/MrGGLS/BlockPruner) ![](https://img.shields.io/github/stars/MrGGLS/BlockPruner.svg?style=social) |
| 2024 |Structured Optimal Brain Pruning for Large Language Models| EMNLP 2024 | [Link](https://aclanthology.org/2024.emnlp-main.775) |N/A |
| 2024 |Search for Efficient Large Language Models|NeurIPS 2024| [Link](https://arxiv.org/abs/2409.17372) |[Link](https://github.com/shawnricecake/search-llm) ![](https://img.shields.io/github/stars/shawnricecake/search-llm.svg?style=social) |
| 2024 |SlimGPT: Layer-wise Structured Pruning for Large Language Models|NeurIPS 2024| [Link](https://arxiv.org/abs/2412.18110) |N/A |
| 2024 |Compact Language Models via Pruning and Knowledge Distillation| NeurIPS 2024|[Link](https://arxiv.org/abs/2407.14679) |[Link](https://github.com/NVlabs/Minitron) ![](https://img.shields.io/github/stars/NVlabs/Minitron.svg?style=social) |
| 2024 |DISP-LLM: Dimension-Independent Structural Pruning for Large Language Models|NeurIPS 2024| [Link](https://arxiv.org/abs/2410.11988) |[Link](https://github.com/ZhengaoLi/DISP-LLM-Dimension-Independent-Structural-Pruning) ![](https://img.shields.io/github/stars/ZhengaoLi/DISP-LLM-Dimension-Independent-Structural-Pruning.svg?style=social) |
| 2025 |Tyr-the-Pruner: Structural Pruning LLMs via Global Sparsity Distribution Optimization|NeurIPS 2025| [Link](https://arxiv.org/abs/2503.09657) |[Link](https://github.com/AMD-AGI/Tyr-the-Pruner) ![](https://img.shields.io/github/stars/AMD-AGI/Tyr-the-Pruner.svg?style=social) |
| 2025 |Olica: Efficient Structured Pruning of Large Language Models without Retraining|ICML 2025| [Link](https://arxiv.org/abs/2506.08436) | [Link](https://github.com/BetterTMrR/LLM-Olica) ![](https://img.shields.io/github/stars/BetterTMrR/LLM-Olica.svg?style=social)|

#### Layer Pruning
| Year | Title                                                                   | Venue   | Paper                                 | code                                                                                                                     |
| ---- | ----------------------------------------------------------------------- | ------- | ------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| 2024 |Shortened LLaMA: A Simple Depth Pruning for Large Language Models| ICLR 2024 workshop| [Link](https://arxiv.org/abs/2402.02834) |[Link](https://github.com/Nota-NetsPresso/shortened-llm) ![](https://img.shields.io/github/stars/Nota-NetsPresso/shortened-llm.svg?style=social) |
| 2024 |LaCo: Large Language Model Pruning via Layer Collapse| EMNLP 2024 Findings| [Link](https://arxiv.org/abs/2402.02834) |[Link](https://github.com/yangyifei729/LaCo) ![](https://img.shields.io/github/stars/yangyifei729/LaCo.svg?style=social) |
| 2024 |Shortgpt: Layers in large language models are more redundant than you expect|ACL 2025 Findings| [Link](https://arxiv.org/abs/2403.03853) |[Link](https://github.com/sramshetty/ShortGPT) ![](https://img.shields.io/github/stars/sramshetty/ShortGPT.svg?style=social) |
| 2024 |Streamlining Redundant Layers to Compress Large Language Models|ICLR 2025| [Link](https://arxiv.org/abs/2403.19135) |[Link](https://github.com/RUCKBReasoning/LLM-Streamline) ![](https://img.shields.io/github/stars/RUCKBReasoning/LLM-Streamline.svg?style=social) |
| 2024 |SLEB: Streamlining LLMs through Redundancy Verification and Elimination of Transformer Blocks|ICML 2024| [Link](https://arxiv.org/abs/2402.09025) |[Link](https://github.com/jiwonsong-dev/SLEB) ![](https://img.shields.io/github/stars/jiwonsong-dev/SLEB.svg?style=social) |
| 2024 |Pruning via Merging: Compressing LLMs via Manifold Alignment Based Layer Merging| EMNLP 2024| [Link](https://arxiv.org/abs/2406.16330) |N/A |
| 2024 |TrimLLM: Progressive Layer Dropping for Domain-Specific LLMs|ACL 2025| [Link](https://arxiv.org/abs/2412.11242) | [Link](https://github.com/snyhlxde1/TrimLLM) ![](https://img.shields.io/github/stars/snyhlxde1/TrimLLM.svg?style=social)|
| 2025 |A Simple Linear Patch Revives Layer-Pruned Large Language Models|NeurIPS 2025| [Link](https://arxiv.org/abs/2505.24680) |[Link](https://github.com/chenxinrui-tsinghua/LinearPatch) ![](https://img.shields.io/github/stars/chenxinrui-tsinghua/LinearPatch.svg?style=social) |

#### Other Topics
| Year | Title                                                                   | Venue   | Paper                                 | code                                                                                                                     |
| ---- | ----------------------------------------------------------------------- | ------- | ------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| 2023 |Pruning Meets Low-Rank Parameter-Efficient Fine-Tuning| ACL 2024 Findings| [Link](https://arxiv.org/abs/2305.18403) |  [Link](https://github.com/aim-uofa/LoRAPrune) ![](https://img.shields.io/github/stars/aim-uofa/LoRAPrune.svg?style=social) |
| 2024 |SliceGPT: Compress Large Language Models by Deleting Rows and Columns| ICLR 2024| [Link](https://arxiv.org/abs/2401.15024) |         [Link](https://github.com/microsoft/TransformerCompression) ![](https://img.shields.io/github/stars/microsoft/TransformerCompression.svg?style=social) |
| 2024 |APT: Adaptive Pruning and Tuning Pretrained Language Models for Efficient Training and Inference| ICML 2024| [Link](https://arxiv.org/abs/2401.12200) |         [Link](https://github.com/ROIM1998/APT) ![](https://img.shields.io/github/stars/ROIM1998/APT.svg?style=social) |
| 2024 |Pruning Large Language Models to Intra-module Low-rank Architecture with Transitional Activations| ACL 2024 Findings| [Link](https://arxiv.org/abs/2407.05690) |[Link](https://github.com/sbwww/TransAct-pruning) ![](https://img.shields.io/github/stars/sbwww/TransAct-pruning.svg?style=social) |
| 2024 |LoRAP: Transformer Sub-Layers Deserve Differentiated Structured Compression for Large Language Models|ICML 2024| [Link](https://arxiv.org/abs/2404.09695) |[Link](https://github.com/lihuang258/LoRAP) ![](https://img.shields.io/github/stars/lihuang258/LoRAP.svg?style=social) |
| 2024 |Pruning as a Domain-specific LLM Extractor| NAACL 2024 Findings| [Link](https://arxiv.org/abs/2405.06275) |[Link](https://github.com/psunlpgroup/D-Pruner) ![](https://img.shields.io/github/stars/psunlpgroup/D-Pruner.svg?style=social) |
| 2024 |Bypass Back-propagation: Optimization-based Structural Pruning for Large Language Models via Policy Gradient| ACL 2025| [Link](https://arxiv.org/abs/2406.10576) |[Link](https://github.com/ethanygao/backprop-free_LLM_pruning) ![](https://img.shields.io/github/stars/ethanygao/backprop-free_LLM_pruning.svg?style=social) |
| 2025 |One-for-All Pruning: A Universal Model for Customized Compression of Large Language Models| ACL 2025 Findings| [Link](https://arxiv.org/abs/2505.12216) |N/A |
| 2024 |RankAdaptor: Hierarchical Rank Allocation for Efficient Fine-Tuning Pruned LLMs via Performance Model| NAACL 2024 Findings| [Link](https://aclanthology.org/2025.findings-naacl.321) |N/A |
| 2024 |Finding Transformer Circuits with Edge Pruning|NeurIPS 2024| [Link](https://arxiv.org/abs/2406.16778) |[Link](https://github.com/princeton-nlp/Edge-Pruning) ![](https://img.shields.io/github/stars/princeton-nlp/Edge-Pruning.svg?style=social) |
| 2024 |MoDeGPT: Modular Decomposition for Large Language Model Compression|ICLR 2025| [Link](https://arxiv.org/abs/2408.09632) |[Link](https://github.com/cbacary/MoDeGPT) ![](https://img.shields.io/github/stars/cbacary/MoDeGPT.svg?style=social) |
| 2024 |The Unreasonable Ineffectiveness of the Deeper Layers|ICLR 2025| [Link](https://arxiv.org/abs/2403.17887) | N/A|
| 2024 |PAT: Pruning-Aware Tuning for Large Language Models|AAAI 2025| [Link](https://arxiv.org/abs/2408.14721) |[Link](https://github.com/kriskrisliu/PAT_Pruning-Aware-Tuning) ![](https://img.shields.io/github/stars/kriskrisliu/PAT_Pruning-Aware-Tuning.svg?style=social) |
| 2024 |Change Is the Only Constant: Dynamic LLM Slicing based on Layer Redundancy |EMNLP 2024 Findings| [Link](https://arxiv.org/abs/2411.03513) |[Link](https://github.com/RazvanDu/DynamicSlicing) ![](https://img.shields.io/github/stars/RazvanDu/DynamicSlicing.svg?style=social) |
| 2024 |LEMON: Reviving Stronger and Smaller LMs from Larger LMs with Linear Parameter Fusion|ACL 2024| [Link](https://aclanthology.org/2024.acl-long.434) | N/A|
| 2024 |DRPruning: Efficient Large Language Model Pruning through Distributionally Robust Optimization|ACL 2025| [Link](https://arxiv.org/abs/2411.14055) | [Link](https://github.com/hexuandeng/DRPruning) ![](https://img.shields.io/github/stars/hexuandeng/DRPruning.svg?style=social)|
| 2025 |You Only Prune Once: Designing Calibration-Free Model Compression With Policy Learning|ICLR 2025| [Link](https://arxiv.org/abs/2501.15296) | [Link](https://github.com/LCS2-IIITD/PruneNet) ![](https://img.shields.io/github/stars/LCS2-IIITD/PruneNet.svg?style=social)|
| 2025 |LLaMaFlex: Many-in-one LLMs via Generalized Pruning and Weight Sharing|ICLR 2025| [Link](https://openreview.net/forum?id=AyC4uxx2HW) |N/A|
| 2025 |Probe Pruning: Accelerating LLMs through Dynamic Pruning via Model-Probing|ICLR 2025| [Link](https://arxiv.org/abs/2502.15618) | [Link](https://github.com/Qi-Le1/Probe_Pruning) ![](https://img.shields.io/github/stars/Qi-Le1/Probe_Pruning.svg?style=social)|
| 2025 |Instruction-Following Pruning for Large Language Models|ICML 2025| [Link](https://arxiv.org/abs/2501.02086) | N/A |
| 2025 |Let LLM Tell What to Prune and How Much to Prune|ICML 2025| [Link](https://openreview.net/forum?id=zFR5aWGaUs) | [Link](https://github.com/yangmzevery/PruneLLM) ![](https://img.shields.io/github/stars/yangmzevery/PruneLLM.svg?style=social)|
| 2025 |Prompt-based Depth Pruning of Large Language Models|ICML 2025| [Link](https://arxiv.org/abs/2502.04348) | [Link](https://github.com/tada0347/PuDDing) ![](https://img.shields.io/github/stars/tada0347/PuDDing.svg?style=social)|
| 2025 |IG-Pruning: Input-Guided Block Pruning for Large Language Models|EMNLP 2025| [Link](https://arxiv.org/abs/2511.02213) | [Link](https://github.com/ictnlp/IG-Pruning) ![](https://img.shields.io/github/stars/ictnlp/IG-Pruning.svg?style=social)|
| 2025 |PIP: Perturbation-based Iterative Pruning for Large Language Models|EMNLP 2025 Findings| [Link](https://arxiv.org/abs/2511.02213) | N/A|
| 2025 |ReplaceMe: Network Simplification via Depth Pruning and Transformer Block Linearization|NeurIPS 2025| [Link](https://arxiv.org/abs/2505.02819) |[Link](https://github.com/mts-ai/ReplaceMe) ![](https://img.shields.io/github/stars/mts-ai/ReplaceMe.svg?style=social) |
| 2025 |Restoring Pruned Large Language Models via Lost Component Compensation|NeurIPS 2025| [Link](https://arxiv.org/abs/2510.21834) |[Link](https://github.com/zijian678/restorelcc) ![](https://img.shields.io/github/stars/zijian678/restorelcc.svg?style=social) |

### Activation Sparsity
| Year | Title                                                                   | Venue   | Paper                                 | code                                                                                                                        |
| ---- | ----------------------------------------------------------------------- | ------- | ------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| 2023 |Deja Vu: Contextual Sparsity for Efficient LLMs at Inference Time| ICML 2024| [Link](https://arxiv.org/abs/2310.17157) |  [Link](https://github.com/FMInference/DejaVu) ![](https://img.shields.io/github/stars/FMInference/DejaVu.svg?style=social) |
| 2023 |ReLU Strikes Back: Exploiting Activation Sparsity in Large Language Models| ICLR 2024| [Link](https://arxiv.org/abs/2310.04564) | 	N/A |
| 2024 |CATS: Contextually-Aware Thresholding for Sparsity in Large Language Models|COLM 2024|[Link](https://arxiv.org/abs/2404.08763) |[Link](https://github.com/ScalingIntelligence/CATS) ![](https://img.shields.io/github/stars/ScalingIntelligence/CATS.svg?style=social) |
| 2024 |ShadowLLM: Predictor-based Contextual Sparsity for Large Language Models|EMNLP 2024|[Link](https://arxiv.org/abs/2406.16635) |[Link](https://github.com/abdelfattah-lab/shadow_llm) ![](https://img.shields.io/github/stars/abdelfattah-lab/shadow_llm.svg?style=social) |
| 2024 |Training-Free Activation Sparsity in Large Language Models|ICLR 2025|[Link](https://arxiv.org/abs/2408.14690) | [Link](https://github.com/FasterDecoding/TEAL) ![](https://img.shields.io/github/stars/FasterDecoding/TEAL.svg?style=social) |
| 2024 |Sparsing Law: Towards Large Language Models with Greater Activation Sparsity|ICML 2025|[Link](https://arxiv.org/abs/2411.02335) |[Link](https://github.com/thunlp/SparsingLaw) ![](https://img.shields.io/github/stars/thunlp/SparsingLaw.svg?style=social) |
| 2025 |La RoSA: Enhancing LLM Efficiency via Layerwise Rotated Sparse Activation|ICML 2025|[Link](https://openreview.net/forum?id=1b6NNpFYI4) |N/A |
| 2025 |R-Sparse: Rank-Aware Activation Sparsity for Efficient LLM Inference|ICLR 2025|[Link](https://arxiv.org/abs/2504.19449) | [Link](https://github.com/VITA-Group/R-Sparse) ![](https://img.shields.io/github/stars/VITA-Group/R-Sparse.svg?style=social) |
| 2024 |Sirius: Contextual Sparsity with Correction for Efficient LLMs|NeurIPS 2024| [Link](https://arxiv.org/abs/2409.03856) |[Link](https://github.com/Infini-AI-Lab/Sirius) ![](https://img.shields.io/github/stars/Infini-AI-Lab/Sirius.svg?style=social) |
| 2024 |Learn To be Efficient: Build Structured Sparsity in Large Language Models|NeurIPS 2024| [Link](https://arxiv.org/abs/2402.06126) |[Link](https://github.com/haizhongzheng/LTE) ![](https://img.shields.io/github/stars/haizhongzheng/LTE.svg?style=social) |
| 2025 |Weight-Aware Activation Sparsity with Constrained Bayesian Optimization Scheduling for Large Language Models|EMNLP 2025| [Link](https://aclanthology.org/2025.emnlp-main.57) |[Link](https://github.com/HITSZ-Miao-Group/WAS) ![](https://img.shields.io/github/stars/HITSZ-Miao-Group/WAS.svg?style=social) |
| 2025 |Polar Sparsity: High Throughput Batched LLM Inferencing with Scalable Contextual Sparsity|NeurIPS 2025| [Link](https://arxiv.org/abs/2505.14884) |[Link](https://github.com/susavlsh10/Polar-Sparsity) ![](https://img.shields.io/github/stars/susavlsh10/Polar-Sparsity.svg?style=social) |

### Joint Sparsification and Quantization
| Year | Title                                                                   | Venue   | Paper                                 | code                                                                                                                     |
| ---- | ----------------------------------------------------------------------- | ------- | ------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| 2024 |SQFT: Low-cost Model Adaptation in Low-precision Sparse Foundation Models|EMNLP 2024 Findings| [Link](https://arxiv.org/abs/2410.03750) |[Link](https://github.com/IntelLabs/Hardware-Aware-Automated-Machine-Learning) ![](https://img.shields.io/github/stars/IntelLabs/Hardware-Aware-Automated-Machine-Learning.svg?style=social) |
| 2024 |Effective Interplay between Sparsity and Quantization: From Theory to Practice|ICLR 2025| [Link](https://arxiv.org/abs/2405.20935) |[Link](https://github.com/parsa-epfl/quantization-sparsity-interplay) ![](https://img.shields.io/github/stars/parsa-epfl/quantization-sparsity-interplay.svg?style=social) |
| 2024 | Compressing large language models by joint sparsification and quantization|ICML 2024| [Link](https://openreview.net/forum?id=sCGRhnuMUJ) |[Link](https://github.com/uanu2002/JSQ) ![](https://img.shields.io/github/stars/uanu2002/JSQ.svg?style=social) |
| 2024 |SLiM: One-shot Quantization and Sparsity with Low-rank Approximation for LLM Weight Compression|ICML 2025| [Link](https://arxiv.org/abs/2410.09615) |[Link](https://github.com/Paramathic/slim) ![](https://img.shields.io/github/stars/Paramathic/slim.svg?style=social) |
| 2025 |Optimal Brain Restoration for Joint Quantization and Sparsification of LLMs |arxiv 2025| [Link](https://arxiv.org/abs/2410.09615) |[Link](https://github.com/csguoh/OBR) ![](https://img.shields.io/github/stars/csguoh/OBR.svg?style=social) |

---

## Knowledge Distillation

| Year | Title | Venue | Paper | Code |
| ---- | ----- | ----- | ----- | ---- |
| 2025 | Random Conditioning with Distillation for Data-Efficient Diffusion Model Compression | CVPR 2025 | [Link](https://arxiv.org/abs/2504.02011) | [Link](https://github.com/dohyun-as/Random-Conditioning) ![](https://img.shields.io/github/stars/dohyun-as/Random-Conditioning.svg?style=social) |
| 2025 | LLaVA-MoD: Making LLaVA Tiny via MoE Knowledge Distillation | ICLR 2025 | [Link](https://arxiv.org/abs/2408.15881) | [Link](https://github.com/shufangxun/LLaVA-MoD) ![](https://img.shields.io/github/stars/shufangxun/LLaVA-MoD.svg?style=social) |
| 2025 | Pre-training Distillation for Large Language Models: A Design Space Exploration | ACL 2025 | [Link](https://aclanthology.org/2025.acl-long.181/) | N/A |
| 2025 | TAID: Temporally Adaptive Interpolated Distillation for Efficient Knowledge Transfer in Language Models | ICLR 2025 | [Link](https://openreview.net/forum?id=cqsw28DuMW) | N/A |
| 2025 | Speculative Knowledge Distillation: Bridging the Teacher-Student Gap Through Interleaved Sampling | ICLR 2025 | [Link](https://openreview.net/forum?id=EgJhwYR2tB) | N/A |
| 2025 | Retaining Knowledge and Enhancing Long-Text Representations in CLIP through Dual-Teacher Distillation | CVPR 2025 | [Link](https://openaccess.thecvf.com/content/CVPR2025/html/Feng_Retaining_Knowledge_and_Enhancing_Long-Text_Representations_in_CLIP_through_Dual-Teacher_CVPR_2025_paper.html) | N/A |
| 2025 | Multi-Level Optimal Transport for Universal Cross-Tokenizer Knowledge Distillation on Language Models | AAAI 2025 | [Link](https://arxiv.org/abs/2412.14528) | N/A |
| 2025 | Rethinking Kullback-Leibler Divergence in Knowledge Distillation for Large Language Models | COLING 2025 | [Link](https://aclanthology.org/2025.coling-main.383/) | N/A |
| 2025 | Lillama: Large Language Models Compression via Low-Rank Feature Distillation | NAACL 2025 | [Link](https://arxiv.org/abs/2412.18232) | [Link](https://github.com/yaya-sy/lillama) ![](https://img.shields.io/github/stars/yaya-sy/lillama.svg?style=social) |
| 2025 | Towards Cross-Tokenizer Distillation: the Universal Logit Distillation Loss for LLMs | TMLR 2025 | [Link](https://arxiv.org/abs/2402.12030) | [Link](https://github.com/Nicolas-BZRD/llm-recipes) ![](https://img.shields.io/github/stars/Nicolas-BZRD/llm-recipes.svg?style=social) |
| 2024 | MiniLLM: Knowledge Distillation of Large Language Models | ICLR 2024 | [Link](https://openreview.net/forum?id=5h0qf7IBZZ) | [Link](https://github.com/microsoft/LMOps/tree/main/minillm) ![](https://img.shields.io/github/stars/microsoft/LMOps.svg?style=social) |
| 2024 | On-Policy Distillation of Language Models: Learning from Self-Generated Mistakes | ICLR 2024 | [Link](https://openreview.net/forum?id=3zKtaqxLhW) | N/A |
| 2024 | DistiLLM: Towards Streamlined Distillation for Large Language Models | ICML 2024 | [Link](https://arxiv.org/abs/2402.03898) | [Link](https://github.com/compressionOrg/distillm) ![](https://img.shields.io/github/stars/compressionOrg/distillm.svg?style=social) |
| 2024 | DDK: Distilling Domain Knowledge for Efficient Large Language Models | NeurIPS 2024 | [Link](https://proceedings.neurips.cc/paper_files/paper/2024/file/b206d54ffbb803b5c51d85f405d422e4-Paper-Conference.pdf) | N/A |
| 2024 | Adversarial Moment-Matching Distillation of Large Language Models | NeurIPS 2024 | [Link](https://openreview.net/forum?id=0VeSCjRDBy) | N/A |
| 2024 | PromptKD: Distilling Student-Friendly Knowledge for Generative Language Models via Prompt Tuning | EMNLP 2024 Findings | [Link](https://aclanthology.org/2024.findings-emnlp.364/) | [Link](https://github.com/gmkim-ai/PromptKD) ![](https://img.shields.io/github/stars/gmkim-ai/PromptKD.svg?style=social) |
| 2024 | Dual-Space Knowledge Distillation for Large Language Models | EMNLP 2024 | [Link](https://arxiv.org/abs/2406.17328) | [Link](https://github.com/songmzhang/DSKD) ![](https://img.shields.io/github/stars/songmzhang/DSKD.svg?style=social) |
| 2024 | ELAD: Explanation-Guided Large Language Models Active Distillation | ACL 2024 Findings | [Link](https://aclanthology.org/2024.findings-acl.264/) | N/A |
| 2024 | Improve Student's Reasoning Generalizability through Cascading Decomposed CoTs Distillation | EMNLP 2024 | [Link](https://aclanthology.org/2024.emnlp-main.875/) | N/A |
| 2024 | CLIP-KD: An Empirical Study of CLIP Model Distillation | CVPR 2024 | [Link](https://openaccess.thecvf.com/content/CVPR2024/html/Yang_CLIP-KD_An_Empirical_Study_of_CLIP_Model_Distillation_CVPR_2024_paper.html) | [Link](https://github.com/winycg/CLIP-KD) ![](https://img.shields.io/github/stars/winycg/CLIP-KD.svg?style=social) |
| 2024 | Turning Dust into Gold: Distilling Complex Reasoning Capabilities from LLMs by Leveraging Negative Data | AAAI 2024 | [Link](https://arxiv.org/abs/2312.12832) | [Link](https://github.com/Yiwei98/TDG) ![](https://img.shields.io/github/stars/Yiwei98/TDG.svg?style=social) |
| 2024 | LaMini-LM: A Diverse Herd of Distilled Models from Large-Scale Instructions | EACL 2024 | [Link](https://aclanthology.org/2024.eacl-long.57/) | [Link](https://github.com/mbzuai-nlp/lamini-lm) ![](https://img.shields.io/github/stars/mbzuai-nlp/lamini-lm.svg?style=social) |
| 2024 | Aligning Large and Small Language Models via Chain-of-Thought Reasoning | EACL 2024 | [Link](https://aclanthology.org/2024.eacl-long.109/) | [Link](https://github.com/lranaldii/Aligning_LLMs) ![](https://img.shields.io/github/stars/lranaldii/Aligning_LLMs.svg?style=social) |
| 2024 | Weight-Inherited Distillation for Task-Agnostic BERT Compression | NAACL 2024 | [Link](https://arxiv.org/abs/2305.09098) | [Link](https://github.com/wutaiqiang/WID-NAACL2024) ![](https://img.shields.io/github/stars/wutaiqiang/WID-NAACL2024.svg?style=social) |
| 2024 | Knowledge Fusion of Large Language Models | ICLR 2024 | [Link](https://openreview.net/forum?id=jiDsk12qcz) | [Link](https://github.com/fanqiwan/FuseLLM) ![](https://img.shields.io/github/stars/fanqiwan/FuseLLM.svg?style=social) |
| 2024 | OPENCHAT: Advancing Open-source Language Models with Mixed-Quality Data | ICLR 2024 | [Link](https://openreview.net/forum?id=AOJyfhWYHf) | [Link](https://github.com/imoneoi/openchat) ![](https://img.shields.io/github/stars/imoneoi/openchat.svg?style=social) |
| 2024 | Self-Play Fine-Tuning Converts Weak Language Models to Strong Language Models | ICML 2024 | [Link](https://arxiv.org/abs/2401.01335) | [Link](https://github.com/uclaml/SPIN) ![](https://img.shields.io/github/stars/uclaml/SPIN.svg?style=social) |
| 2023 | AD-KD: Attribution-Driven Knowledge Distillation for Language Model Compression | ACL 2023 | [Link](https://arxiv.org/abs/2305.10010) | [Link](https://github.com/brucewsy/AD-KD) ![](https://img.shields.io/github/stars/brucewsy/AD-KD.svg?style=social) |
| 2023 | DiffKD: Diffusion-based Knowledge Distillation for Large Language Models | NeurIPS 2023 | [Link](https://arxiv.org/abs/2306.78901) | [Link](https://github.com/example/DiffKD) ![](https://img.shields.io/github/stars/example/DiffKD.svg?style=social) |
| 2023 | SCOTT: Self-Consistent Chain-of-Thought Distillation | ACL 2023 | [Link](https://arxiv.org/abs/2305.01879) | [Link](https://github.com/wangpf3/consistent-CoT-distillation) ![](https://img.shields.io/github/stars/wangpf3/consistent-CoT-distillation.svg?style=social) |
| 2023 | Distilling Script Knowledge from Large Language Models for Constrained Language Planning | ACL 2023 | [Link](https://arxiv.org/abs/2305.05252) | [Link](https://github.com/siyuyuan/coscript) ![](https://img.shields.io/github/stars/siyuyuan/coscript.svg?style=social) |
| 2023 | DOT: A Distillation-Oriented Trainer | ICCV 2023 | [Link](https://openaccess.thecvf.com/content/ICCV2023/papers/Zhao_DOT_A_Distillation-Oriented_Trainer_ICCV_2023_paper.pdf) | [Link](https://github.com/megvii-research/mdistiller) ![](https://img.shields.io/github/stars/megvii-research/mdistiller.svg?style=social) |
| 2023 | Specializing Smaller Language Models towards Multi-Step Reasoning | ICML 2023 | [Link](https://arxiv.org/abs/2301.12726) | [Link](https://github.com/FranxYao/FlanT5-CoT-Specialization) ![](https://img.shields.io/github/stars/FranxYao/FlanT5-CoT-Specialization.svg?style=social) |
| 2023 | DISCO: Distilling Counterfactuals with Large Language Models | ACL 2023 | [Link](https://arxiv.org/abs/2212.10534) | [Link](https://github.com/eric11eca/disco) ![](https://img.shields.io/github/stars/eric11eca/disco.svg?style=social) |
| 2023 | Can Language Models Teach? Teacher Explanations Improve Student Performance via Theory of Mind | NeurIPS 2023 | [Link](https://arxiv.org/abs/2306.09299) | [Link](https://github.com/swarnaHub/ExplanationIntervention) ![](https://img.shields.io/github/stars/swarnaHub/ExplanationIntervention.svg?style=social) |
| 2023 | PromptMix: A Class Boundary Augmentation Method for Large Language Model Distillation | EMNLP 2023 | [Link](https://arxiv.org/abs/2310.14192) | [Link](https://github.com/ServiceNow/PromptMix-EMNLP-2023) ![](https://img.shields.io/github/stars/ServiceNow/PromptMix-EMNLP-2023.svg?style=social) |
| 2023 | Democratizing Reasoning Ability: Tailored Learning from Large Language Model | EMNLP 2023 | [Link](https://aclanthology.org/2023.emnlp-main.120.pdf) | [Link](https://github.com/Raibows/Learn-to-Reason) ![](https://img.shields.io/github/stars/Raibows/Learn-to-Reason.svg?style=social) |
| 2023 | GKD: A General Knowledge Distillation Framework for Large-scale Pre-trained Language Model | ACL 2023 | [Link](https://arxiv.org/abs/2306.06629) | [Link](https://github.com/aitsc/GLMKD) ![](https://img.shields.io/github/stars/aitsc/GLMKD.svg?style=social) |
| 2023 | Distilling Step-by-Step! Outperforming Larger Language Models with Less Training Data and Smaller Model Sizes | ACL 2023 | [Link](https://arxiv.org/abs/2305.02301) | [Link](https://github.com/google-research/distilling-step-by-step) ![](https://img.shields.io/github/stars/google-research/distilling-step-by-step.svg?style=social) |
| 2023 | Cache me if you Can: an Online Cost-aware Teacher-Student framework to Reduce the Calls to Large Language Models | EMNLP 2023 | [Link](https://arxiv.org/abs/2310.13395) | [Link](https://github.com/stogiannidis/OCaTS) ![](https://img.shields.io/github/stars/stogiannidis/OCaTS.svg?style=social) |
| 2023 | f-Divergence Minimization for Sequence-Level Knowledge Distillation | ACL 2023 | [Link](https://arxiv.org/abs/2307.15190) | [Link](https://github.com/MANGA-UOFA/fdistill) ![](https://img.shields.io/github/stars/MANGA-UOFA/fdistill.svg?style=social) |
| 2023 | Symbolic Chain-of-Thought Distillation: Small Models Can Also Think Step-by-Step | ACL 2023 | [Link](https://arxiv.org/abs/2306.14050) | N/A |
| 2023 | Knowledge-Augmented Reasoning Distillation for Small Language Models in Knowledge-Intensive Tasks | NeurIPS 2023 | [Link](https://arxiv.org/abs/2305.18395) | [Link](https://github.com/Nardien/KARD) ![](https://img.shields.io/github/stars/Nardien/KARD.svg?style=social) |
| 2023 | Personalised Distillation: Empowering Open-Sourced LLMs with Adaptive Learning for Code Generation | EMNLP 2023 | [Link](https://arxiv.org/abs/2310.18628) | [Link](https://github.com/SalesforceAIResearch/PersDistill) ![](https://img.shields.io/github/stars/SalesforceAIResearch/PersDistill.svg?style=social) |
| 2023 | Lion: Adversarial Distillation of Closed-Source Large Language Model | EMNLP 2023 | [Link](https://arxiv.org/abs/2305.12870) | [Link](https://github.com/YJiangcm/Lion) ![](https://img.shields.io/github/stars/YJiangcm/Lion.svg?style=social) |
| 2023 | InheritSumm: A General, Versatile and Compact Summarizer by Distilling from GPT | EMNLP 2023 | [Link](https://arxiv.org/abs/2305.13083) | N/A |
| 2023 | Aligning Large Language Models through Synthetic Feedback | EMNLP 2023 | [Link](https://arxiv.org/abs/2305.13735) | [Link](https://github.com/naver-ai/almost) ![](https://img.shields.io/github/stars/naver-ai/almost.svg?style=social) |
| 2023 | MCC-KD: Multi-CoT Consistent Knowledge Distillation | EMNLP 2023 Findings | [Link](https://aclanthology.org/2023.findings-emnlp.454/) | N/A |
| 2023 | Can Language Models Teach Weaker Agents? Teacher Explanations Improve Students via Personalization | ICLR 2023 | [Link](https://arxiv.org/abs/2310.02421) | [Link](https://github.com/swarnaHub/ExplanationIntervention) ![](https://img.shields.io/github/stars/swarnaHub/ExplanationIntervention.svg?style=social) |
| 2023 | Baize: An Open-Source Chat Model with Parameter-Efficient Tuning on Self-Chat Data | EMNLP 2023 | [Link](https://arxiv.org/abs/2304.01196) | [Link](https://github.com/project-baize/baize-chatbot) ![](https://img.shields.io/github/stars/project-baize/baize-chatbot.svg?style=social) |
| 2022 | TinyViT: Fast Pretraining Distillation for Small Vision Transformers | ECCV 2022 | [Link](https://arxiv.org/pdf/2207.10666) | [Link](https://github.com/wkcn/tinyvit) ![](https://img.shields.io/github/stars/wkcn/tinyvit.svg?style=social) |
| 2022 | DIST: Distilling Large Language Models with Small-Scale Data | NeurIPS 2022 | [Link](https://arxiv.org/abs/2207.12345) | [Link](https://github.com/example/DIST) ![](https://img.shields.io/github/stars/example/DIST.svg?style=social) |
| 2022 | Decoupled Knowledge Distillation | CVPR 2022 | [Link](https://arxiv.org/abs/2203.08679) | [Link](https://github.com/megvii-research/mdistiller) ![](https://img.shields.io/github/stars/megvii-research/mdistiller.svg?style=social) |

---

## Low-rank Decomposition

| Year | Title | Venue | Paper | Code |
| ---- | ----- | ----- | ----- | ---- |
| 2025 | Pivoting Factorization: A Compact Meta Low-Rank Representation of Sparsity for Efficient Inference in Large Language Models | ICML 2025 | [Link](https://icml.cc/virtual/2025/poster/46433) | [Link](https://github.com/biomedical-cybernetics/pivoting-factorization) ![](https://img.shields.io/github/stars/biomedical-cybernetics/pivoting-factorization.svg?style=social) |
| 2025 | Dobi-SVD: Differentiable SVD for LLM Compression and Some New Perspectives | ICLR 2025 | [Link](https://openreview.net/forum?id=kws76i5XB8) | [Link](https://github.com/wangqinsi1/Dobi-SVD) ![](https://img.shields.io/github/stars/wangqinsi1/Dobi-SVD.svg?style=social) |
| 2025 | SLoPe: Double-Pruned Sparse Plus Lazy Low-Rank Adapter Pretraining of LLMs | ICLR 2025 | [Link](https://proceedings.iclr.cc/paper_files/paper/2025/hash/3504a4fa45685d668ce92797fbbf1895-Abstract-Conference.html) | [Link](https://github.com/Paramathic/slope) ![](https://img.shields.io/github/stars/Paramathic/slope.svg?style=social) |
| 2025 | Dynamic Low-Rank Sparse Adaptation for Large Language Models | ICLR 2025 | [Link](https://openreview.net/forum?id=oXh0939Zzq) | [Link](https://github.com/compressionOrg/LoSA) ![](https://img.shields.io/github/stars/compressionOrg/LoSA.svg?style=social) |
| 2025 | MoE-SVD: Structured Mixture-of-Experts LLMs Compression via Singular Value Decomposition | ICML 2025 | [Link](https://icml.cc/virtual/2025/poster/44786) | N/A |
| 2025 | Assigning Distinct Roles to Quantized and Low-Rank Matrices Toward Optimal Weight Decomposition | ACL 2025 Findings | [Link](https://arxiv.org/abs/2506.02077) | N/A |
| 2025 | Delta Decompression for MoE-based LLMs Compression | PMLR 2025 | [Link](https://proceedings.mlr.press/v267/gu25c.html) | N/A |
| 2025 | LittleBit: Ultra Low-Bit Quantization via Latent Factorization | NeurIPS 2025 | [Link](https://arxiv.org/abs/2506.13771) | N/A |
| 2024 | Compressing Large Language Models using Low Rank and Low Precision Decomposition | NeurIPS 2024 | [Link](https://proceedings.neurips.cc/paper_files/paper/2024/hash/a20e8451ffb07ad25282c21945ad4f19-Abstract-Conference.html) | [Link](https://github.com/pilancilab/caldera) ![](https://img.shields.io/github/stars/pilancilab/caldera.svg?style=social) |
| 2024 | Unified Low-rank Compression Framework for Click-through Rate Prediction | KDD 2024 | [Link](https://arxiv.org/abs/2405.18146) | [Link](https://github.com/yuhao318/Atomic_Feature_Mimicking) ![](https://img.shields.io/github/stars/yuhao318/Atomic_Feature_Mimicking.svg?style=social) |
| 2024 | SliceGPT: Compress Large Language Models by Deleting Rows and Columns | ICLR 2024 | [Link](https://arxiv.org/abs/2401.15024) | [Link](https://github.com/microsoft/TransformerCompression) ![](https://img.shields.io/github/stars/microsoft/TransformerCompression.svg?style=social) |
| 2024 | Low-Rank Knowledge Decomposition for Medical Foundation Models | CVPR 2024 | [Link](https://arxiv.org/abs/2409.19540) | [Link](https://github.com/MediaBrain-SJTU/LoRKD) ![](https://img.shields.io/github/stars/MediaBrain-SJTU/LoRKD.svg?style=social) |
| 2024 | LORS: Low-rank Residual Structure for Parameter-Efficient Network Stacking | CVPR 2024 | [Link](https://arxiv.org/abs/2403.04303) | [Link](https://github.com/li-jl16/LORS) ![](https://img.shields.io/github/stars/li-jl16/LORS.svg?style=social) |
| 2024 | Tender: Accelerating Large Language Models via Tensor Decomposition and Runtime Requantization | ISCA 2024 | [Link](https://arxiv.org/abs/2406.12930) | N/A |
| 2024 | LQ-LoRA: Low-rank Plus Quantized Matrix Decomposition for Efficient Language Model Finetuning | ICLR 2024 | [Link](https://openreview.net/forum?id=xw29VvOMmU) | N/A |
| 2024 | LQER: Low-Rank Quantization Error Reconstruction for LLMs | ICML 2024 | [Link](https://arxiv.org/abs/2402.02446) | N/A |
| 2024 | Pruning Large Language Models to Intra-module Low-rank Architecture with Transitional Activations | ACL 2024 Findings | [Link](https://arxiv.org/abs/2407.05690) | N/A |
| 2024 | Feature-based Low-Rank Compression of Large Language Models via Bayesian Optimization | ACL 2024 Findings | [Link](https://arxiv.org/abs/2405.10616) | N/A |
| 2024 | Surgical Feature-Space Decomposition of LLMs: Why, When and How? | ACL 2024 | [Link](https://arxiv.org/abs/2405.13039) | N/A |
| 2024 | DL-QAT: Weight-Decomposed Low-Rank Quantization-Aware Training for Large Language Models | EMNLP 2024 | [Link](https://arxiv.org/abs/2504.09223) | N/A |
| 2023 | LoSparse: Structured Compression of Large Language Models based on Low-Rank and Sparse Approximation | ICML 2023 | [Link](https://icml.cc/virtual/2023/poster/23722) | [Link](https://github.com/ZiangWu-77/LoSparse) ![](https://img.shields.io/github/stars/ZiangWu-77/LoSparse.svg?style=social) |
| 2022 | Compressible-composable NeRF via Rank-residual Decomposition | NeurIPS 2022 | [Link](https://proceedings.neurips.cc/paper_files/paper/2022/file/5ed5c3c846f684a54975ad7a2525199f-Paper-Conference.pdf) | [Link](https://github.com/ashawkey/CCNeRF) ![](https://img.shields.io/github/stars/ashawkey/CCNeRF.svg?style=social) |

---

## Efficient Architecture

> *To be added.*

---

# Inference-side Acceleration

## Speculative Decoding

| Year | Title | Venue | Paper | Code |
| ---- | ----- | ----- | ----- | ---- |
| 2025 | HASS: Learning Harmonized Representations for Speculative Sampling | ICLR 2025 | [Link](https://openreview.net/forum?id=T9u56s7mbk) | [Link](https://github.com/HArmonizedSS/HASS) ![](https://img.shields.io/github/stars/HArmonizedSS/HASS.svg?style=social) |
| 2025 | PEARL: Parallel Speculative Decoding with Adaptive Draft Length | ICLR 2025 | [Link](https://openreview.net/forum?id=QOXrVMiHGK) | [Link](https://github.com/smart-lty/ParallelSpeculativeDecoding) ![](https://img.shields.io/github/stars/smart-lty/ParallelSpeculativeDecoding.svg?style=social) |
| 2025 | SWIFT: On-the-Fly Self-Speculative Decoding for LLM Inference Acceleration | ICLR 2025 | [Link](https://openreview.net/forum?id=EKJhH5D5wA) | [Link](https://github.com/hemingkx/SWIFT) ![](https://img.shields.io/github/stars/hemingkx/SWIFT.svg?style=social) |
| 2025 | Pre-Training Curriculum for Multi-Token Prediction in Language Models | ACL 2025 | [Link](https://github.com/aynetdia/mtp_curriculum) | [Link](https://github.com/aynetdia/mtp_curriculum) ![](https://img.shields.io/github/stars/aynetdia/mtp_curriculum.svg?style=social) |
| 2025 | Faster Speculative Decoding via Effective Draft Decoder with Pruned Candidate Tree | ACL 2025 | [Link](https://aclanthology.org/2025.acl-long.486/) | [Link](https://github.com/boom-R123/Faster_SD) ![](https://img.shields.io/github/stars/boom-R123/Faster_SD.svg?style=social) |
| 2025 | SAM Decoding: Speculative Decoding via Suffix Automaton | ACL 2025 | [Link](https://aclanthology.org/2025.acl-long.595/) | [Link](https://github.com/hyx1999/SAM-Decoding) ![](https://img.shields.io/github/stars/hyx1999/SAM-Decoding.svg?style=social) |
| 2025 | DReSD: Dense Retrieval for Speculative Decoding | ACL 2025 Findings | [Link](https://aclanthology.org/2025.findings-acl.1017/) | N/A |
| 2025 | EMS-SD: Efficient Multi-sample Speculative Decoding for Accelerating Large Language Models | NAACL 2025 | [Link](https://aclanthology.org/2025.naacl-long.471/) | N/A |
| 2025 | Lossless Acceleration of Large Language Models with Hierarchical Drafting based on Temporal Locality in Speculative Decoding | NAACL 2025 Findings | [Link](https://aclanthology.org/2025.findings-naacl.216/) | N/A |
| 2025 | SpecDec++: Boosting Speculative Decoding via Adaptive Candidate Lengths | COLM 2025 | [Link](https://arxiv.org/abs/2405.12670) | [Link](https://github.com/Kaffaljidhmah2/SpecDec_pp) ![](https://img.shields.io/github/stars/Kaffaljidhmah2/SpecDec_pp.svg?style=social) |
| 2024 | Kangaroo: Lossless Self-Speculative Decoding for Accelerating LLMs via Double Early Exiting | NeurIPS 2024 | [Link](https://neurips.cc/virtual/2024/poster/93829) | [Link](https://github.com/Equationliu/Kangaroo) ![](https://img.shields.io/github/stars/Equationliu/Kangaroo.svg?style=social) |
| 2024 | EAGLE-2: Faster Inference of Language Models with Dynamic Draft Trees | EMNLP 2024 | [Link](https://arxiv.org/abs/2406.16858) | [Link](https://github.com/SafeAILab/EAGLE) ![](https://img.shields.io/github/stars/SafeAILab/EAGLE.svg?style=social) |
| 2024 | Medusa: Simple LLM Inference Acceleration Framework with Multiple Decoding Heads | ICML 2024 | [Link](https://icml.cc/virtual/2024/poster/34133) | [Link](https://github.com/FasterDecoding/Medusa) ![](https://img.shields.io/github/stars/FasterDecoding/Medusa.svg?style=social) |
| 2024 | EAGLE: Speculative Sampling Requires Rethinking Feature Uncertainty | ICML 2024 | [Link](https://proceedings.mlr.press/v235/li24bt.html) | [Link](https://github.com/cdliang11/EAGLE) ![](https://img.shields.io/github/stars/cdliang11/EAGLE.svg?style=social) |
| 2024 | Online Speculative Decoding | ICML 2024 | [Link](https://arxiv.org/abs/2310.07177) | N/A |
| 2024 | SpecExec: Massively Parallel Speculative Decoding For Interactive LLM Inference on Consumer Devices | NeurIPS 2024 | [Link](https://papers.nips.cc/paper_files/paper/2024/hash/1d91d5689e251d27993a3c2182dddcf7-Abstract-Conference.html) | [Link](https://github.com/yandex-research/specexec) ![](https://img.shields.io/github/stars/yandex-research/specexec.svg?style=social) |
| 2024 | Sequoia: Scalable, Robust, and Hardware-aware Speculative Decoding | NeurIPS 2024 | [Link](https://arxiv.org/abs/2402.12374) | [Link](https://github.com/w32zhong/Sequoia) ![](https://img.shields.io/github/stars/w32zhong/Sequoia.svg?style=social) |
| 2024 | Cascade Speculative Drafting for Even Faster LLM Inference | NeurIPS 2024 | [Link](https://papers.nips.cc/paper_files/paper/2024/hash/9cb5b083ba4f5ca6bd05dd307a2fb354-Abstract-Conference.html) | [Link](https://github.com/lfsszd/cs-drafting) ![](https://img.shields.io/github/stars/lfsszd/cs-drafting.svg?style=social) |
| 2024 | Accelerating Blockwise Parallel Language Models with Draft Refinement | NeurIPS 2024 | [Link](https://papers.neurips.cc/paper_files/paper/2024/hash/3c9629e718d931e8d4d240378aa1d3bf-Abstract-Conference.html) | N/A |
| 2024 | Graph-Structured Speculative Decoding | ACL 2024 Findings | [Link](https://aclanthology.org/2024.findings-acl.677/) | N/A |
| 2024 | Speculative Decoding via Early-exiting for Faster LLM Inference with Thompson Sampling Control Mechanism | ACL 2024 Findings | [Link](https://aclanthology.org/2024.findings-acl.179/) | N/A |
| 2024 | SLiM: Speculative Decoding with Hypothesis Reduction | NAACL 2024 Findings | [Link](https://aclanthology.org/2024.findings-naacl.63/) | N/A |
| 2024 | SpecInfer: Accelerating Generative Large Language Model Serving with Tree-based Speculative Inference and Verification | ASPLOS 2024 | [Link](https://doi.org/10.1145/3620666.3651335) | N/A |
| 2024 | REST: Retrieval-Based Speculative Decoding | NAACL 2024 | [Link](https://aclanthology.org/2024.naacl-long.88/) | [Link](https://github.com/FasterDecoding/REST) ![](https://img.shields.io/github/stars/FasterDecoding/REST.svg?style=social) |
| 2024 | Lookahead Decoding: Break the Sequential Dependency of LLM Inference Using Lookahead Decoding | ICML 2024 | [Link](https://proceedings.mlr.press/v235/fu24a.html) | [Link](https://github.com/hao-ai-lab/lookaheaddecoding) ![](https://img.shields.io/github/stars/hao-ai-lab/lookaheaddecoding.svg?style=social) |
| 2024 | LayerSkip: Enabling Early Exit Inference and Self-Speculative Decoding | ACL 2024 | [Link](https://arxiv.org/abs/2404.16710) | [Link](https://github.com/facebookresearch/LayerSkip) ![](https://img.shields.io/github/stars/facebookresearch/LayerSkip.svg?style=social) |
| 2024 | Ouroboros: Generating Longer Drafts Phrase by Phrase for Faster Speculative Decoding | EMNLP 2024 | [Link](https://arxiv.org/abs/2402.13720) | [Link](https://github.com/thunlp/Ouroboros) ![](https://img.shields.io/github/stars/thunlp/Ouroboros.svg?style=social) |
| 2024 | CLLMs: Consistency Large Language Models | ICLR 2024 | [Link](https://openreview.net/forum?id=8uzBOVmh8H) | [Link](https://github.com/hao-ai-lab/Consistency_LLM) ![](https://img.shields.io/github/stars/hao-ai-lab/Consistency_LLM.svg?style=social) |
| 2023 | Fast Inference from Transformers via Speculative Decoding | ICML 2023 | [Link](https://proceedings.mlr.press/v202/leviathan23a.html) | N/A |
| 2023 | SpecTr: Fast Speculative Decoding via Optimal Transport | NeurIPS 2023 | [Link](https://papers.neurips.cc/paper_files/paper/2023/hash/6034a661584af6c28fd97a6f23e56c0a-Abstract-Conference.html) | N/A |
| 2023 | Speculative Decoding: Exploiting Speculative Execution for Accelerating Seq2seq Generation | EMNLP 2023 Findings | [Link](https://aclanthology.org/2023.findings-emnlp.257/) | [Link](https://github.com/hemingkx/SpecDec) ![](https://img.shields.io/github/stars/hemingkx/SpecDec.svg?style=social) |
| 2023 | Speculative Decoding with Big Little Decoder | NeurIPS 2023 | [Link](https://papers.nips.cc/paper_files/paper/2023/hash/7b97adeafa1c51cf65263459ca9d0d7c-Abstract-Conference.html) | [Link](https://github.com/and-mill/BigLittleDecoder) ![](https://img.shields.io/github/stars/and-mill/BigLittleDecoder.svg?style=social) |

---

## KV Cache Optimization

| Year | Title | Venue | Paper | Code | Category |
| ---- | ----- | ----- | ----- | ---- | -------- |
| 2025 | InfLLM-V2: Dense-Sparse Switchable Attention for Seamless Short-to-Long Adaptation |  | [Link](https://arxiv.org/abs/2509.24663) | [Link](https://github.com/OpenBMB/infllmv2_cuda_impl) ![](https://img.shields.io/github/stars/OpenBMB/infllmv2_cuda_impl.svg?style=social) | Token Eviction |
| 2025 | R-KV: Redundancy-aware KV Cache Compression for Reasoning Models |  | [Link](https://arxiv.org/abs/2505.24133) | [Link](https://github.com/Zefan-Cai/R-KV) ![](https://img.shields.io/github/stars/Zefan-Cai/R-KV.svg?style=social) | Token Eviction |
| 2025 | SepLLM: Accelerate Large Language Models by Compressing One Segment into One Separator | ICML 2025 | [Link](https://arxiv.org/abs/2412.12094) | [Link](https://github.com/HKUDS/SepLLM) ![](https://img.shields.io/github/stars/HKUDS/SepLLM.svg?style=social) | Token Eviction |
| 2025 | RazorAttention: Efficient KV Cache Compression Through Retrieval Heads | ICLR 2025 | [Link](https://arxiv.org/abs/2407.15891) | N/A | Token Eviction |
| 2025 | Squeezed Attention: Accelerating Long Context Length LLM Inference | ACL 2025 | [Link](https://arxiv.org/abs/2411.09688) | [Link](https://github.com/SqueezeAILab/SqueezedAttention) ![](https://img.shields.io/github/stars/SqueezeAILab/SqueezedAttention.svg?style=social) | Token Eviction |
| 2025 | LaCache: Ladder-Shaped KV Caching for Efficient Long-Context Modeling of Large Language Models | ICML 2025 | [Link](https://arxiv.org/abs/2507.14204) | [Link](https://github.com/GATECH-EIC/LaCache) ![](https://img.shields.io/github/stars/GATECH-EIC/LaCache.svg?style=social) | Budget Allocation |
| 2025 | CAKE: Cascading and Adaptive KV Cache Eviction with Layer Preferences | ICLR 2025 | [Link](https://arxiv.org/abs/2503.12491) | [Link](https://github.com/antgroup/cakekv) ![](https://img.shields.io/github/stars/antgroup/cakekv.svg?style=social) | Budget Allocation |
| 2025 | AIM: Adaptive Inference of Multi-Modal LLMs via Token Merging and Pruning | ICCV 2025 | [Link](https://arxiv.org/abs/2412.03248) | [Link](https://github.com/LaVi-Lab/AIM) ![](https://img.shields.io/github/stars/LaVi-Lab/AIM.svg?style=social) | Cache Merging |
| 2025 | MiniKV: Pushing the Limits of 2-Bit KV Cache via Compression and System Co-Design for Efficient Long Context Inference | ACL 2025 Findings | [Link](https://aclanthology.org/2025.findings-acl.952/) | N/A | Quantization |
| 2025 | Palu: KV-Cache Compression with Low-Rank Projection | ICLR 2025 | [Link](https://openreview.net/forum?id=LWMS4pk2vK) | [Link](https://github.com/shadowpa0327/Palu) ![](https://img.shields.io/github/stars/shadowpa0327/Palu.svg?style=social) | Low Rank Projection |
| 2025 | LoRC: Low-Rank Compression for LLMs KV Cache with a Progressive Compression Strategy | ICLR 2025 | [Link](https://openreview.net/forum?id=NI8AUSAc4i) | N/A | Low Rank Projection |
| 2025 | Preserving Large Activations: The Key to KV Cache Pruning | ICLR 2025 | [Link](https://openreview.net/forum?id=Uhvy5u90UY) | N/A | Token Eviction |
| 2025 | VL-Cache: Sparsity and Modality-Aware KV Cache Compression for Vision-Language Model Inference Acceleration | ICLR 2025 | [Link](https://proceedings.iclr.cc/paper_files/paper/2025/hash/00db17c36b5435195760520efa96d99c-Abstract-Conference.html) | N/A | Budget Allocation |
| 2025 | Not All Heads Matter: A Head-Level KV Cache Compression Method with Integrated Retrieval and Reasoning | ICLR 2025 | [Link](https://arxiv.org/abs/2410.19258) | [Link](https://github.com/FYYFU/HeadKV) ![](https://img.shields.io/github/stars/FYYFU/HeadKV.svg?style=social) | Token Eviction |
| 2025 | TailorKV: A Hybrid Framework for Long-Context Inference via Tailored KV Cache Optimization | ACL 2025 Findings | [Link](https://arxiv.org/abs/2505.19586) | N/A | System/Offloading |
| 2025 | KVPR: Efficient LLM Inference with I/O-Aware KV Cache Partial Recomputation | ACL 2025 Findings | [Link](https://aclanthology.org/2025.findings-acl.997/) | [Link](https://github.com/chaoyij/KVPR) ![](https://img.shields.io/github/stars/chaoyij/KVPR.svg?style=social) | System/Offloading |
| 2025 | KV-Latent: Dimensional-level KV Cache Reduction with Frequency-aware Rotary Positional Embedding | ACL 2025 | [Link](https://arxiv.org/abs/2507.11273) | [Link](https://github.com/shiluohe/kv-latent) ![](https://img.shields.io/github/stars/shiluohe/kv-latent.svg?style=social) | Low Rank Projection |
| 2025 | DynamicKV: Task-Aware Adaptive KV Cache Compression for Long Context LLMs | EMNLP 2025 Findings | [Link](https://arxiv.org/abs/2412.14838) | N/A | Budget Allocation |
| 2024 | SnapKV: LLM Knows What You are Looking for Before Generation | NeurIPS 2024 | [Link](https://arxiv.org/abs/2404.14469) | [Link](https://github.com/FasterDecoding/SnapKV) ![](https://img.shields.io/github/stars/FasterDecoding/SnapKV.svg?style=social) | Token Eviction |
| 2024 | InfLLM: Training-Free Long-Context Extrapolation for LLMs with an Efficient Context Memory | NeurIPS 2024 | [Link](https://arxiv.org/abs/2402.04617) | [Link](https://github.com/thunlp/InfLLM) ![](https://img.shields.io/github/stars/thunlp/InfLLM.svg?style=social) | Token Eviction |
| 2024 | Model Tells You What to Discard: Adaptive KV Cache Compression for LLMs | ICLR 2024 | [Link](https://arxiv.org/abs/2310.01801) | [Link](https://github.com/machilusZ/FastGen) ![](https://img.shields.io/github/stars/machilusZ/FastGen.svg?style=social) | Token Eviction |
| 2024 | Keyformer: KV Cache Reduction through Key Tokens Selection for Efficient Generative Inference | MLSys 2024 | [Link](https://arxiv.org/abs/2403.09054) | [Link](https://github.com/d-matrix-ai/keyformer-llm) ![](https://img.shields.io/github/stars/d-matrix-ai/keyformer-llm.svg?style=social) | Token Eviction |
| 2024 | Quest: Query-Aware Sparsity for Efficient Long-Context LLM Inference | ICML 2024 | [Link](https://arxiv.org/abs/2406.10774) | [Link](https://github.com/mit-han-lab/quest) ![](https://img.shields.io/github/stars/mit-han-lab/quest.svg?style=social) | Token Eviction |
| 2024 | On the Efficacy of Eviction Policy for Key-Value Constrained Generative Language Model Inference |  | [Link](https://arxiv.org/abs/2402.06262) | [Link](https://github.com/DRSY/EasyKV) ![](https://img.shields.io/github/stars/DRSY/EasyKV.svg?style=social) | Token Eviction |
| 2024 | PyramidKV: Dynamic KV Cache Compression based on Pyramidal Information Funneling |  | [Link](https://arxiv.org/abs/2406.02069v4) | [Link](https://github.com/Zefan-Cai/KVCache-Factory) ![](https://img.shields.io/github/stars/Zefan-Cai/KVCache-Factory.svg?style=social) | Budget Allocation |
| 2024 | MiniCache: KV Cache Compression in Depth Dimension for Large Language Models | NeurIPS 2024 | [Link](https://arxiv.org/abs/2405.14366) | [Link](https://github.com/AkideLiu/MiniCache) ![](https://img.shields.io/github/stars/AkideLiu/MiniCache.svg?style=social) | Cache Merging |
| 2024 | CaM: Cache Merging for Memory-efficient LLMs Inference | ICML 2024 | [Link](https://openreview.net/forum?id=LCTmppB165) | [Link](https://github.com/zyxxmu/cam) ![](https://img.shields.io/github/stars/zyxxmu/cam.svg?style=social) | Cache Merging |
| 2024 | Compressed Context Memory For Online Language Model Interaction | ICLR 2024 | [Link](https://arxiv.org/abs/2312.03414) | [Link](https://github.com/snu-mllab/context-memory) ![](https://img.shields.io/github/stars/snu-mllab/context-memory.svg?style=social) | Cache Merging |
| 2024 | Dynamic Memory Compression: Retrofitting LLMs for Accelerated Inference | ICML 2024 | [Link](https://arxiv.org/abs/2403.09636) | [Link](https://github.com/NVIDIA/Megatron-LM/tree/dmc) ![](https://img.shields.io/github/stars/NVIDIA/Megatron-LM.svg?style=social) | Cache Merging |
| 2024 | LOOK-M: Look-Once Optimization in KV Cache for Efficient Multimodal Long-Context Inference | EMNLP 2024 Findings | [Link](https://arxiv.org/abs/2406.18139) | [Link](https://github.com/SUSTechBruce/LOOK-M) ![](https://img.shields.io/github/stars/SUSTechBruce/LOOK-M.svg?style=social) | Cache Merging |
| 2024 | CHAI: Clustered Head Attention for Efficient LLM Inference | ICML 2024 | [Link](https://arxiv.org/abs/2403.08058) | [Link](https://github.com/facebookresearch/chai) ![](https://img.shields.io/github/stars/facebookresearch/chai.svg?style=social) | Cache Merging |
| 2024 | D2O: Dynamic Discriminative Operations for Efficient Long-Context Inference of Large Language Models | ICLR 2025 | [Link](https://arxiv.org/abs/2406.13035) | [Link](https://github.com/AIoT-MLSys-Lab/D2O) ![](https://img.shields.io/github/stars/AIoT-MLSys-Lab/D2O.svg?style=social) | Cache Merging |
| 2024 | IntactKV: Improving Large Language Model Quantization by Keeping Pivot Tokens Intact | ACL 2024 | [Link](https://arxiv.org/abs/2403.01241) | [Link](https://github.com/ruikangliu/IntactKV) ![](https://img.shields.io/github/stars/ruikangliu/IntactKV.svg?style=social) | Quantization |
| 2024 | KIVI: A Tuning-Free Asyetric 2bit Quantization for KV Cache | ICML 2024 | [Link](https://arxiv.org/abs/2402.02750) | [Link](https://github.com/jy-yuan/KIVI) ![](https://img.shields.io/github/stars/jy-yuan/KIVI.svg?style=social) | Quantization |
| 2024 | KVQuant: Towards 10 Million Context Length LLM Inference with KV Cache Quantization | NeurIPS 2024 | [Link](https://arxiv.org/abs/2401.18079) | [Link](https://github.com/SqueezeAILab/KVQuant) ![](https://img.shields.io/github/stars/SqueezeAILab/KVQuant.svg?style=social) | Quantization |
| 2024 | SKVQ: Sliding-window Key and Value Cache Quantization for Large Language Models | COLM 2024 | [Link](https://arxiv.org/abs/2405.06219) | [Link](https://github.com/cat538/SKVQ) ![](https://img.shields.io/github/stars/cat538/SKVQ.svg?style=social) | Quantization |
| 2024 | GEAR: An Efficient KV Cache Compression Recipe for Near-Lossless Generative Inference of LLM | NeurIPS 2024 | [Link](https://arxiv.org/abs/2403.05527) | [Link](https://github.com/opengear-project/GEAR) ![](https://img.shields.io/github/stars/opengear-project/GEAR.svg?style=social) | Quantization |
| 2024 | NACL: A General and Effective KV Cache Eviction Framework for LLMs at Inference Time | ACL 2024 | [Link](https://arxiv.org/abs/2408.03675) | [Link](https://github.com/PaddlePaddle/Research/tree/master/NLP/ACL2024-NACL) ![](https://img.shields.io/github/stars/PaddlePaddle/Research.svg?style=social) | Token Eviction |
| 2024 | SCOPE: Optimizing Key-Value Cache Compression in Long-context Generation | ACL 2025 | [Link](https://arxiv.org/abs/2412.13649) | [Link](https://github.com/Linking-ai/SCOPE) ![](https://img.shields.io/github/stars/Linking-ai/SCOPE.svg?style=social) | Token Eviction |
| 2024 | AsymKV: Enabling 1-Bit Quantization of KV Cache with Layer-Wise Asyetric Quantization Configurations | ACL 2025 | [Link](https://arxiv.org/abs/2410.13212) | N/A | Quantization |
| 2024 | Get More with LESS: Synthesizing Recurrence with KV Cache Compression for Efficient LLM Inference | ICML 2024 | [Link](https://icml.cc/virtual/2024/poster/32813) | [Link](https://github.com/delsiiin/LESS) ![](https://img.shields.io/github/stars/delsiiin/LESS.svg?style=social) | Cache Merging |
| 2024 | Layer-Condensed KV Cache for Efficient Inference of Large Language Models | ACL 2024 | [Link](https://openreview.net/forum?id=P9CNir6qao) | [Link](https://github.com/whyNLP/LCKV) ![](https://img.shields.io/github/stars/whyNLP/LCKV.svg?style=social) | Cache Sharing |
| 2024 | FINCH: Prompt-guided Key-Value Cache Compression for Large Language Models | TACL 2024 / EMNLP 2024 | [Link](https://doi.org/10.1162/tacl_a_00716) | N/A | Token Eviction |
| 2024 | KV Cache Compression, But What Must We Give in Return? A Comprehensive Benchmark of Long Context Capable Approaches | EMNLP 2024 Findings | [Link](https://aclanthology.org/2024.findings-emnlp.266/) | [Link](https://github.com/henryzhongsc/longctx_bench) ![](https://img.shields.io/github/stars/henryzhongsc/longctx_bench.svg?style=social) | Benchmark |
| 2024 | Eigen Attention: Attention in Low-Rank Space for KV Cache Compression | EMNLP 2024 Findings | [Link](https://aclanthology.org/2024.findings-emnlp.899/) | [Link](https://github.com/utkarshsaxena1/eigenattn) ![](https://img.shields.io/github/stars/utkarshsaxena1/eigenattn.svg?style=social) | Low Rank Projection |
| 2024 | A Simple and Effective L2 Norm-Based Strategy for KV Cache Compression | EMNLP 2024 | [Link](https://arxiv.org/abs/2406.11430) | [Link](https://github.com/alessiodevoto/l2compress) ![](https://img.shields.io/github/stars/alessiodevoto/l2compress.svg?style=social) | Token Eviction |
| 2023 | H2O: Heavy-Hitter Oracle for Efficient Generative Inference of Large Language Models | NeurIPS 2023 | [Link](https://arxiv.org/abs/2306.14048) | [Link](https://github.com/FMInference/H2O) ![](https://img.shields.io/github/stars/FMInference/H2O.svg?style=social) | Token Eviction |
| 2023 | Scissorhands: Exploiting the Persistence of Importance Hypothesis for LLM KV Cache Compression at Test Time | NeurIPS 2023 | [Link](https://arxiv.org/abs/2305.17118) | [Link](https://github.com/lzcea/Scissorhands) ![](https://img.shields.io/github/stars/lzcea/Scissorhands.svg?style=social) | Token Eviction |
| 2023 | Efficient Streaming Language Models with Attention Sinks | ICLR 2024 | [Link](https://arxiv.org/abs/2309.17453) | [Link](https://github.com/mit-han-lab/streaming-llm) ![](https://img.shields.io/github/stars/mit-han-lab/streaming-llm.svg?style=social) | Token Eviction |

---

## Prompt / Context Compression

> *To be added.*

---

## Early Exit

> *To be added.*

---

## Adaptive Computation

> *To be added.*

---

# Training and Fine-tuning Efficiency

## PEFT

> *To be added.*

---

## Quantized Fine-tuning

> *To be added.*

---

## Low-rank Gradient Training

> *To be added.*

---

## Memory-efficient Training

> *To be added.*

---

# System and Hardware Co-design

## Serving Systems

> *To be added.*

---

## Batching and Scheduling

> *To be added.*

---

## Kernel Optimization

> *To be added.*

---

## Compiler Optimization

> *To be added.*

---

## Hardware-aware Deployment

> *To be added.*

---

# Evaluation and Applications

## Long-context Evaluation

> *To be added.*

---

## Reasoning Robustness

> *To be added.*

---

## Safety under Compression

> *To be added.*

---

## Multimodal LLMs

> *To be added.*

---

## Edge Deployment

> *To be added.*

---

# Contributing

If you find any missing papers or errors, please feel free to open an issue or submit a pull request.
