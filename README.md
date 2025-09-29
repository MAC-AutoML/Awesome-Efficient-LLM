# Awesome-Efficient-LLM

# Toxonomy and Papers
- [Sparsity and Pruning](#Sparsity-and-Pruning)
- [Quantization](#Quantization)
  - [LLM Quantization](#LLM-Quantization)
  - [VLM Quantization](#VLM-Quantization)
- [Knowledge Distillation](#Knowledge-Distillation)
- [Low-Rank Decomposition](#Low-Rank-Decomposition)
- [KV Cache Compression](#KV-Cache-Compression)
- [Speculative Decoding](#Speculative-Decoding)

---
# Sparsity and Pruning
| Year | Title                                                                   | Venue   | Paper                                 | code                                                                                                                        |
| ---- | ----------------------------------------------------------------------- | ------- | ------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| 2023 | SparseGPT: Massive Language Models Can Be Accurately Pruned in One-Shot | ICML 2023| [Link](https://arxiv.org/pdf/2301.00774) |         [Link](https://github.com/IST-DASLab/sparsegpt) ![](https://img.shields.io/github/stars/IST-DASLab/sparsegpt.svg?style=social) |

---
# Quantization
## LLM Quantization
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
| 2025 | GPTAQ: Efficient Finetuning-Free Quantization for Asymmetric Calibration | ICML 2025 | [Link](https://arxiv.org/pdf/2504.02692) | [Link](https://github.com/Intelligent-Computing-Lab-Panda/GPTAQ)![](https://img.shields.io/github/stars/Intelligent-Computing-Lab-Panda/GPTAQ.svg?style=social) |
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



## VLM Quantization
| Year | Title                                                                   | Venue   | Paper                                 | code                                                                                                                        |
| ---- | ----------------------------------------------------------------------- | ------- | ------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| 2024 | Q-VLM: Post-training Quantization for Large Vision Language Models      | NIPS 2024 | [Link](https://arxiv.org/pdf/2410.08119) | [Link](https://github.com/ChangyuanWang17/QVLM) ![](https://img.shields.io/github/stars/ChangyuanWang17/QVLM.svg?style=social) |
| 2025 | MBQ:Modality-Balanced Quantization for Large Vision-Language Models     | CVPR 2025 | [Link](https://arxiv.org/pdf/2412.19509) | [Link](https://github.com/thu-nics/MBQ) ![](https://img.shields.io/github/stars/thu-nics/MBQ.svg?style=social) |


## DiT Quantization

| Year | Title | Venue | Task | Paper | Code |
|------|-------|-------|------|-------|------|
| 2025 | SVDQuant: Absorbing Outliers by Low-Rank Component for 4-Bit Diffusion Models | ICLR 2025 | T2I | [Link](https://arxiv.org/pdf/2411.05007) | [Link](https://github.com/nunchaku-tech/nunchaku) ![](https://img.shields.io/github/stars/nunchaku-tech/nunchaku.svg?style=social) |
| 2025 | ViDiT-Q: Efficient and Accurate Quantization of Diffusion Transformers for Image and Video Generation | ICLR 2025 | Image Generation | [Link](https://arxiv.org/pdf/2406.02540) | [Link](https://github.com/thu-nics/ViDiT-Q) ![](https://img.shields.io/github/stars/thu-nics/ViDiT-Q.svg?style=social) |
| 2023 | Post-training Quantization on Diffusion Models | CVPR 2023 | T2I、T2V | [Link](https://arxiv.org/pdf/2211.15736) | [Link](https://github.com/42Shawn/PTQ4DM) ![](https://img.shields.io/github/stars/42Shawn/PTQ4DM.svg?style=social) |
| 2023 | Q-Diffusion: Quantizing Diffusion Models | ICCV 2023 | Image Generation | [Link](https://arxiv.org/pdf/2302.04304) | [Link](https://github.com/Xiuyu-Li/q-diffusion) ![](https://img.shields.io/github/stars/Xiuyu-Li/q-diffusion.svg?style=social) |
| 2024 | Towards Accurate Post-training Quantization for Diffusion Models | CVPR 2024 | Image Generation | [Link](https://arxiv.org/pdf/2305.18723) | [Link](https://github.com/ChangyuanWang17/APQ-DM) ![](https://img.shields.io/github/stars/ChangyuanWang17/APQ-DM.svg?style=social) |
| 2024 | EfficientDM: Efficient Quantization-Aware Fine-Tuning of Low-Bit Diffusion Models | ICLR 2024 | Image Generation | [Link](https://arxiv.org/pdf/2310.03270) | [Link](https://github.com/ThisisBillhe/EfficientDM) ![](https://img.shields.io/github/stars/ThisisBillhe/EfficientDM.svg?style=social) |
| 2025 | Q-DiT: Accurate Post-Training Quantization for Diffusion Transformers | CVPR 2025 | T2I、T2V | [Link](https://arxiv.org/pdf/2406.17343) | [Link](https://github.com/Juanerx/Q-DiT) ![](https://img.shields.io/github/stars/Juanerx/Q-DiT.svg?style=social) |
| 2025 | SageAttention: Accurate 8-Bit Attention for Plug-and-play Inference Acceleration | ICLR 2025 | T2I、T2V | [Link](https://arxiv.org/pdf/2410.02367) | [Link](https://github.com/thu-ml/SageAttention) ![](https://img.shields.io/github/stars/thu-ml/SageAttention.svg?style=social) |
| 2024 | TFMQ-DM: Temporal Feature Maintenance Quantization for Diffusion Models | CVPR 2024 | Image Generation | [Link](https://arxiv.org/pdf/2311.16503) | [Link](https://github.com/ModelTC/TFMQ-DM) ![](https://img.shields.io/github/stars/ModelTC/TFMQ-DM.svg?style=social) |
| 2023 | Temporal Dynamic Quantization for Diffusion Models | NIPS 2023 |  | [Link](https://arxiv.org/pdf/2306.02316v2) | [Link](https://github.com/ECoLab-POSTECH/TDQ_NeurIPS2023) ![](https://img.shields.io/github/stars/ECoLab-POSTECH/TDQ_NeurIPS2023.svg?style=social) |
| 2024 | DiTFastAttn: Attention Compression for Diffusion Transformer Models | NIPS 2024 | T2I、T2V | [Link](https://arxiv.org/pdf/2406.08552) | [Link](https://github.com/thu-nics/DiTFastAttn) ![](https://img.shields.io/github/stars/thu-nics/DiTFastAttn.svg?style=social) |
| 2025 | Sparse VideoGen: Accelerating Video Diffusion Transformers with Spatial-Temporal Sparsity | ICML 2025 | T2V | [Link](https://arxiv.org/pdf/2502.01776) | [Link](https://github.com/svg-project/Sparse-VideoGen) ![](https://img.shields.io/github/stars/svg-project/Sparse-VideoGen.svg?style=social) |
| 2025 | Timestep Embedding Tells: It’s Time to Cache for Video Diffusion Model | CVPR 2025 | T2V | [Link](https://arxiv.org/pdf/2411.19108) | [Link](https://github.com/ali-vilab/TeaCache) ![](https://img.shields.io/github/stars/ali-vilab/TeaCache.svg?style=social) |
| 2025 | From Reusing to Forecasting: Accelerating Diffusion Models with TaylorSeers | ICCV 2025 | T2V | [Link](https://arxiv.org/pdf/2503.06923) | [Link](https://github.com/Shenyi-Z/TaylorSeer) ![](https://img.shields.io/github/stars/Shenyi-Z/TaylorSeer.svg?style=social) |
---
# Knowledge Distillation
| Year | Title                                                                   | Venue   | Paper                                 | code                                                                                                                        |
| ---- | ----------------------------------------------------------------------- | ------- | ------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| 2025 | Random Conditioning with Distillation for Data-Efficient Diffusion Model Compression | CVPR 2025 | [Link](https://arxiv.org/abs/2504.02011) | [Link](https://github.com/dohyun-as/Random-Conditioning) ![](https://img.shields.io/github/stars/dohyun-as/Random-Conditioning.svg?style=social) |
| 2025 | LLaVA-MoD: Making LLaVA Tiny via MoE Knowledge Distillation              | ICLR 2025 | [Link](https://arxiv.org/pdf/2408.15881) | [Link](https://github.com/shufangxun/LLaVA-MoD) ![](https://img.shields.io/github/stars/shufangxun/LLaVA-MoD.svg?style=social) |
| 2024 | PromptKD: Prompt-based Knowledge Distillation for Large Language Models | EMNLP 2024 | [Link](https://arxiv.org/abs/2405.12345) | [Link](https://github.com/example/PromptKD) ![](https://img.shields.io/github/stars/example/PromptKD.svg?style=social) |
| 2023 | AD-KD: Attribution-Driven Knowledge Distillation for Language Model Compression | ACL 2023 | [Link](https://arxiv.org/abs/2305.10010) | [Link](https://github.com/brucewsy/AD-KD) ![](https://img.shields.io/github/stars/brucewsy/AD-KD.svg?style=social) |
| 2023 | DiffKD: Diffusion-based Knowledge Distillation for Large Language Models | NIPS 2023 | [Link](https://arxiv.org/abs/2306.78901) | [Link](https://github.com/example/DiffKD) ![](https://img.shields.io/github/stars/example/DiffKD.svg?style=social) |
| 2023 | SCOTT: Self-Consistent Chain-of-Thought Distillation | ACL 2023 | [Link](https://arxiv.org/abs/2305.01879) | [Link](https://github.com/wangpf3/consistent-CoT-distillation) ![](https://img.shields.io/github/stars/wangpf3/consistent-CoT-distillation.svg?style=social) |
| 2023 | Distilling Script Knowledge from Large Language Models for Constrained Language Planning | ACL 2023 | [Link](https://arxiv.org/abs/2305.05252) | [Link](https://github.com/siyuyuan/coscript) ![](https://img.shields.io/github/stars/siyuyuan/coscript.svg?style=social) |
| 2023 | DOT: A Distillation-Oriented Trainer | ICCV 2023 | [Link](https://openaccess.thecvf.com/content/ICCV2023/papers/Zhao_DOT_A_Distillation-Oriented_Trainer_ICCV_2023_paper.pdf) | [Link](https://github.com/megvii-research/mdistiller) ![](https://img.shields.io/github/stars/megvii-research/mdistiller.svg?style=social) |
| 2022 | TinyViT: Fast Pretraining Distillation for Small Vision Transformers | ECCV 2022 | [Link](https://arxiv.org/pdf/2207.10666) | [Link](https://github.com/wkcn/tinyvit) ![](https://img.shields.io/github/stars/wkcn/tinyvit.svg?style=social) |
| 2022 | DIST: Distilling Large Language Models with Small-Scale Data | NIPS 2022 | [Link](https://arxiv.org/abs/2207.12345) | [Link](https://github.com/example/DIST) ![](https://img.shields.io/github/stars/example/DIST.svg?style=social) |
| 2022 | Decoupled Knowledge Distillation | CVPR 2022 | [Link](https://arxiv.org/abs/2203.08679) | [Link](https://github.com/megvii-research/mdistiller) ![](https://img.shields.io/github/stars/megvii-research/mdistiller.svg?style=social) |
| 2021 | HRKD: Hierarchical Relation-based Knowledge Distillation | EMNLP 2021 | [Link](https://arxiv.org/abs/2109.12345) | [Link](https://github.com/example/HRKD) ![](https://img.shields.io/github/stars/example/HRKD.svg?style=social) |
| 2021 | Distilling Knowledge via Knowledge Review | CVPR 2021 | [Link](https://arxiv.org/abs/2104.09044) | [Link](https://github.com/dvlab-research/ReviewKD) ![](https://img.shields.io/github/stars/dvlab-research/ReviewKD.svg?style=social) |
| 2020 | Few Sample Knowledge Distillation for Efficient Network Compression | CVPR 2020 | [Link](https://arxiv.org/abs/1812.01839) | [Link](https://github.com/LTH14/FSKD) ![](https://img.shields.io/github/stars/LTH14/FSKD.svg?style=social) |
---
# Low-Rank Decomposition
| Year | Title                                                                   | Venue   | Paper                                 | code                                                                                                                        |
| ---- | ----------------------------------------------------------------------- | ------- | ------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| 2024 | Compressing Large Language Models using Low Rank and Low Precision Decomposition | NeurIPS 2024 | [Link](https://openreview.net/pdf?id=lkx3OpcqSZ) | [Link](https://github.com/pilancilab/caldera) ![](https://img.shields.io/github/stars/pilancilab/caldera.svg?style=social) |
| 2022 | Compressible-composable NeRF via Rank-residual Decomposition | NeurIPS 2022 | [Link](https://proceedings.neurips.cc/paper_files/paper/2022/file/5ed5c3c846f684a54975ad7a2525199f-Paper-Conference.pdf) | [Link](https://github.com/ashawkey/CCNeRF) ![](https://img.shields.io/github/stars/ashawkey/CCNeRF.svg?style=social) |
| 2024 | Unified Low-rank Compression Framework for Click-through Rate Prediction | KDD 2024 | [Link](https://arxiv.org/abs/2405.18146) | [Link](https://github.com/yuhao318/Atomic_Feature_Mimicking) ![](https://img.shields.io/github/stars/yuhao318/Atomic_Feature_Mimicking.svg?style=social) |
| 2025 | Pivoting Factorization: A Compact Meta Low-Rank Representation of Sparsity for Efficient Inference in Large Language Models | ICML 2025 | [Link](https://icml.cc/virtual/2025/poster/46433) | [Link](https://github.com/biomedical-cybernetics/pivoting-factorization) ![](https://img.shields.io/github/stars/biomedical-cybernetics/pivoting-factorization.svg?style=social) |
| 2024 | SliceGPT: Orthogonal Slicing for Parameter-Efficient Transformer Compression | ICLR 2024 | [Link](https://arxiv.org/abs/2401.15024) | [Link](https://github.com/microsoft/TransformerCompression) ![](https://img.shields.io/github/stars/microsoft/TransformerCompression.svg?style=social) |
| 2024 | Low-Rank Knowledge Decomposition for Medical Foundation Models | CVPR 2024 | [Link](https://arxiv.org/abs/2409.19540) | [Link](https://github.com/MediaBrain-SJTU/LoRKD) ![](https://img.shields.io/github/stars/MediaBrain-SJTU/LoRKD.svg?style=social) |
| 2024 | LORS: Low-rank Residual Structure for Parameter-Efficient Network Stacking | CVPR 2024 | [Link](https://arxiv.org/abs/2403.04303) | [Link](https://github.com/li-jl16/LORS) ![](https://img.shields.io/github/stars/li-jl16/LORS.svg?style=social) |
| 2021 | Decomposable-Net: Scalable Low-Rank Compression for Neural Networks | IJCAI 2021 | [Link](https://www.ijcai.org/proceedings/2021/447) | [Link](https://github.com/ygcats/Scalable-Low-Rank-Compression-for-Neural-Networks) ![](https://img.shields.io/github/stars/ygcats/Scalable-Low-Rank-Compression-for-Neural-Networks.svg?style=social) |

---
# KV Cache Compression
## Token Eviction(also known as Token Selection)
| Year | Title                                                        | Venue        | Paper                                    | code                                                         |
| ---- | ------------------------------------------------------------ | ------------ | ---------------------------------------- | ------------------------------------------------------------ |
| 2023 | H2O: Heavy-Hitter Oracle for Efficient Generative Inference of Large Language Models | NeurIPS 2023 | [Link](https://arxiv.org/abs/2306.14048) | [Link](https://github.com/FMInference/H2O) ![](https://img.shields.io/github/stars/FMInference/H2O.svg?style=social) |
| 2023 | Scissorhands: Exploiting the Persistence of Importance Hypothesis for LLM KV Cache Compression at Test Time | NeurIPS 2023 | [Link](https://arxiv.org/abs/2305.17118) | [Link](https://github.com/lzcemma/Scissorhands) ![](https://img.shields.io/github/stars/lzcemma/Scissorhands.svg?style=social) |
| 2023 | Efficient Streaming Language Models with Attention Sinks | ICLR 2024 | [Link](https://arxiv.org/abs/2309.17453) | [Link](https://github.com/mit-han-lab/streaming-llm) ![](https://img.shields.io/github/stars/mit-han-lab/streaming-llm.svg?style=social) |
| 2024 | SnapKV: LLM Knows What You are Looking for Before Generation | NeurIPS 2024 | [Link](https://arxiv.org/abs/2404.14469) | [Link](https://github.com/FasterDecoding/SnapKV) ![](https://img.shields.io/github/stars/FasterDecoding/SnapKV.svg?style=social) |
| 2024 | InfLLM: Training-Free Long-Context Extrapolation for LLMs with an Efficient Context Memory | NeurIPS 2024 | [Link](https://arxiv.org/abs/2402.04617) | [Link](https://github.com/thunlp/InfLLM) ![](https://img.shields.io/github/stars/thunlp/InfLLM.svg?style=social) |
| 2024 | Model Tells You What to Discard: Adaptive KV Cache Compression for LLMs | ICLR 2024 | [Link](https://arxiv.org/abs/2310.01801) | [Link](https://github.com/machilusZ/FastGen) ![](https://img.shields.io/github/stars/machilusZ/FastGen.svg?style=social) |
| 2024 | Keyformer: KV Cache Reduction through Key Tokens Selection for Efficient Generative Inference | MLSys 2024 | [Link](https://arxiv.org/abs/2403.09054) | [Link](https://github.com/d-matrix-ai/keyformer-llm) ![](https://img.shields.io/github/stars/d-matrix-ai/keyformer-llm.svg?style=social) |
| 2024 | Quest: Query-Aware Sparsity for Efficient Long-Context LLM Inference | ICML 2024 | [Link](https://arxiv.org/abs/2406.10774) | [Link](https://github.com/mit-han-lab/quest) ![](https://img.shields.io/github/stars/mit-han-lab/quest.svg?style=social) |
| 2024 | On the Efficacy of Eviction Policy for Key-Value Constrained Generative Language Model Inference |  | [Link](https://arxiv.org/abs/2402.06262) | [Link](https://github.com/DRSY/EasyKV) ![](https://img.shields.io/github/stars/DRSY/EasyKV.svg?style=social) |
| 2025 | R-KV: Redundancy-aware KV Cache Compression for Reasoning Models |  | [Link](https://arxiv.org/abs/2505.24133) | [Link](https://github.com/Zefan-Cai/R-KV) ![](https://img.shields.io/github/stars/Zefan-Cai/R-KV.svg?style=social) |
| 2025 | SepLLM: Accelerate Large Language Models by Compressing One Segment into One Separator | ICML 2025 | [Link](https://arxiv.org/abs/2412.12094) | [Link](https://github.com/HKUDS/SepLLM) ![](https://img.shields.io/github/stars/HKUDS/SepLLM.svg?style=social) |
| 2025 | Squeezed Attention: Accelerating Long Context Length LLM Inference | ACL 2025 | [Link](https://arxiv.org/abs/2411.09688) | [Link](https://github.com/SqueezeAILab/SqueezedAttention) ![](https://img.shields.io/github/stars/SqueezeAILab/SqueezedAttention.svg?style=social) |

## Budget Allocation
| Year | Title                                                        | Venue    | Paper                                    | code                                                         |
| ---- | ------------------------------------------------------------ | -------- | ---------------------------------------- | ------------------------------------------------------------ |
| 2024 | PyramidKV: Dynamic KV Cache Compression based on Pyramidal Information Funneling |  | [Link](https://arxiv.org/abs/2406.02069v4) | [Link](https://github.com/Zefan-Cai/KVCache-Factory) ![](https://img.shields.io/github/stars/Zefan-Cai/KVCache-Factory.svg?style=social) |
| 2025 | LaCache: Ladder-Shaped KV Caching for Efficient Long-Context Modeling of Large Language Models | ICML 2025 | [Link](https://arxiv.org/abs/2507.14204) | [Link](https://github.com/GATECH-EIC/LaCache) ![](https://img.shields.io/github/stars/GATECH-EIC/LaCache.svg?style=social) |
| 2025 | CAKE: Cascading and Adaptive KV Cache Eviction with Layer Preferences | ICLR 2025 | [Link](https://arxiv.org/abs/2503.12491) | [Link](https://github.com/antgroup/cakekv) ![](https://img.shields.io/github/stars/antgroup/cakekv.svg?style=social) |

## KV Cache Merging
| Year | Title                                                        | Venue    | Paper                                    | code                                                         |
| ---- | ------------------------------------------------------------ | -------- | ---------------------------------------- | ------------------------------------------------------------ |
| 2024 | MiniCache: KV Cache Compression in Depth Dimension for Large Language Models | NeurIPS 2024 | [Link](https://arxiv.org/abs/2405.14366) | [Link](https://github.com/AkideLiu/MiniCache) ![](https://img.shields.io/github/stars/AkideLiu/MiniCache.svg?style=social) |
| 2024 | CaM: Cache Merging for Memory-efficient LLMs Inference | ICML 2024 | [Link](https://openreview.net/forum?id=LCTmppB165) | [Link](https://github.com/zyxxmu/cam) ![](https://img.shields.io/github/stars/zyxxmu/cam.svg?style=social) |
| 2024 | Compressed Context Memory For Online Language Model Interaction | ICLR 2024 | [Link](https://arxiv.org/abs/2312.03414) | [Link](https://github.com/snu-mllab/context-memory) ![](https://img.shields.io/github/stars/snu-mllab/context-memory.svg?style=social) |
| 2024 | Dynamic Memory Compression: Retrofitting LLMs for Accelerated Inference | ICML 2024 | [Link](https://arxiv.org/abs/2403.09636) | N/A |
| 2024 | LOOK-M: Look-Once Optimization in KV Cache for Efficient Multimodal Long-Context Inference | EMNLP 2024 Findings | [Link](https://arxiv.org/abs/2406.18139) | [Link](https://github.com/SUSTechBruce/LOOK-M) ![](https://img.shields.io/github/stars/SUSTechBruce/LOOK-M.svg?style=social) |
| 2024 | CHAI: Clustered Head Attention for Efficient LLM Inference | ICML 2024 | [Link](https://arxiv.org/abs/2403.08058) | [Link](https://github.com/facebookresearch/chai) ![](https://img.shields.io/github/stars/facebookresearch/chai.svg?style=social) |
| 2024 | D2O: Dynamic Discriminative Operations for Efficient Long-Context Inference of Large Language Models | ICLR 2025 | [Link](https://arxiv.org/abs/2406.13035) | [Link](https://github.com/AIoT-MLSys-Lab/D2O) ![](https://img.shields.io/github/stars/AIoT-MLSys-Lab/D2O.svg?style=social) |
| 2025 | AIM: Adaptive Inference of Multi-Modal LLMs via Token Merging and Pruning | ICCV 2025 | [Link](https://arxiv.org/abs/2412.03248) | [Link](https://github.com/LaVi-Lab/AIM) ![](https://img.shields.io/github/stars/LaVi-Lab/AIM.svg?style=social) |

## KV Cache Quantization
| Year | Title                                                        | Venue    | Paper                                    | code                                                         |
| ---- | ------------------------------------------------------------ | -------- | ---------------------------------------- | ------------------------------------------------------------ |
| 2024 | IntactKV: Improving Large Language Model Quantization by Keeping Pivot Tokens Intact | ACL 2024 | [Link](https://arxiv.org/abs/2403.01241) | [Link](https://github.com/ruikangliu/IntactKV) ![](https://img.shields.io/github/stars/ruikangliu/IntactKV.svg?style=social) |
| 2024 | KIVI: A Tuning-Free Asymmetric 2bit Quantization for KV Cache | ICML 2024 | [Link](https://arxiv.org/abs/2402.02750) | [Link](https://github.com/jy-yuan/KIVI) ![](https://img.shields.io/github/stars/jy-yuan/KIVI.svg?style=social) |
| 2024 | KVQuant: Towards 10 Million Context Length LLM Inference with KV Cache Quantization | NeurIPS 2024 | [Link](https://arxiv.org/abs/2401.18079) | [Link](https://github.com/SqueezeAILab/KVQuant) ![](https://img.shields.io/github/stars/SqueezeAILab/KVQuant.svg?style=social) |
| 2024 | SKVQ: Sliding-window Key and Value Cache Quantization for Large Language Models | COLM 2024 | [Link](https://arxiv.org/abs/2405.06219) | [Link](https://github.com/cat538/SKVQ) ![](https://img.shields.io/github/stars/cat538/SKVQ.svg?style=social) |



---
# Speculative Decoding
| Year | Title                                                        | Venue    | Paper                                    | code                                                         |
| ---- | ------------------------------------------------------------ | -------- | ---------------------------------------- | ------------------------------------------------------------ |
| 2024 | Kangaroo: Lossless Self-Speculative Decoding via Double Early Exiting|NeurIPS 2024|[Kangaroo](https://arxiv.org/abs/2404.18911) | [code](https://github.com/Equationliu/Kangaroo) ![](https://img.shields.io/github/stars/Equationliu/Kangaroo.svg?style=social)|
| 2024 | EAGLE-2: Faster Inference of Language Models with Dynamic Draft Trees|EMNLP 2024|[EAGLE2](https://arxiv.org/abs/2406.16858) | [code](https://github.com/SafeAILab/EAGLE) ![](https://img.shields.io/github/stars/SafeAILab/EAGLE.svg?style=social)|
| 2025 |Learning Harmonized Representations for Speculative Sampling|ICLR 2025|[HASS](https://arxiv.org/pdf/2408.15766) |[code](https://github.com/HArmonizedSS/HASS) ![](https://img.shields.io/github/stars/HArmonizedSS/HASS.svg?style=social)|
| 2025 |Parallel Speculative Decoding with Adaptive Draft Length|ICLR 2025|[PEARL](https://arxiv.org/pdf/2408.11850) |[code](https://github.com/smart-lty/ParallelSpeculativeDecoding) ![](https://img.shields.io/github/stars/smart-lty/ParallelSpeculativeDecoding.svg?style=social)|
| 2025 |SWIFT: On-the-Fly Self-Speculative Decoding for LLM Inference Acceleration|ICLR 2025|[SWIFT](https://openreview.net/pdf?id=EKJhH5D5wA) |[code](https://github.com/hemingkx/SWIFT) ![](https://img.shields.io/github/stars/hemingkx/SWIFT.svg?style=social)|
| 2025 |Pre-Training Curriculum for Multi-Token Prediction in Language Models|ACL 2025 |[paper](https://github.com/aynetdia/mtp_curriculum) | [code](https://github.com/aynetdia/mtp_curriculum) ![](https://img.shields.io/github/stars/aynetdia/mtp_curriculum.svg?style=social)|
| 2025 |Faster Speculative Decoding via Effective Draft Decoder with Pruned Candidate Tree|ACL 2025 |[paper](https://aclanthology.org/2025.acl-long.486.pdf) | N/A |

