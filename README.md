# 论文精读与复现

这里整理了 LoRA、rsLoRA 和 Differential Transformer 的阅读报告，以及相关的小规模复现实验分析。重点是把方法读懂：公式是怎么推出来的，代码该怎么实现，实验结果又能说明什么。

## 阅读报告

| 论文 | 发表信息 | 报告 |
| --- | --- | --- |
| LoRA | ICLR 2022 | [下载 DOCX · 16 页](reports/LoRA/LoRA_精读与复现报告_修订版_20261011.docx) |
| rsLoRA | arXiv 2023 预印本 | [下载 DOCX · 12 页](reports/rsLoRA/rsLoRA_精读与复现报告_修订版_20261011.docx) |
| Differential Transformer | ICLR 2025 | [下载 DOCX · 14 页](reports/DifferentialTransformer/DifferentialTransformer_精读与复现报告_修订版_20261011.docx) |

三份报告都可以独立阅读。刚接触这些方法的话，可以先看 LoRA，再接着看 rsLoRA；Differential Transformer 则转向注意力机制本身。

## 主要看了什么

- **LoRA**：从矩阵背景、前向计算和梯度推导开始理解低秩微调，再看 rank、学习率、目标层选择，以及训练后的权重合并。
- **rsLoRA**：沿着 LoRA 继续看 rank 增大后的学习信号，拆解缩放因子的作用，以及初始化和优化器对结论的影响。
- **Differential Transformer**：结合手算、机制反例和小型检索任务，分析两张注意力图相减的过程，以及噪声抵消成立的条件。

报告中穿插了必要背景、手算例子、实现流程和实验对照，也整理了一些值得继续尝试的方向。可以配合原论文阅读，遇到不熟悉的公式时再回头看推导。

## 原论文

- **LoRA**：[LoRA: Low-Rank Adaptation of Large Language Models](https://arxiv.org/abs/2106.09685v2)
- **rsLoRA**：[A Rank Stabilization Scaling Factor for Fine-Tuning with LoRA](https://arxiv.org/abs/2312.03732v1)
- **Differential Transformer**：[Differential Transformer](https://proceedings.iclr.cc/paper_files/paper/2025/hash/00b67df24009747e8bbed4c2c6f9c825-Abstract-Conference.html)

## 关于复现

本地实验以机制检查、小模型训练和部署验证为主。原论文的大规模结果单独注明来源；没有提升、指标冲突和还没验证的想法，也都保留在报告里。

仓库目前提供三份 DOCX 报告，下载后可用 Word 或兼容编辑器阅读。文件校验信息见 [manifest.json](manifest.json)。
