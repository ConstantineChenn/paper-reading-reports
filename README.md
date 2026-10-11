# 论文精读与有限复现报告

三篇报告围绕研究问题、必要背景、方法流程、公式推导、手算例子、实验对照及扩展思考展开。报告为独立学习整理，并非论文作者的官方复现。

修订日期：2026 年 10 月 11 日。共 42 页，DOCX 保留可编辑公式与表格，已完成逐页版式检查。GitHub 可下载文件，使用 Word 或兼容编辑器阅读。

## 报告入口

| 论文 | 报告 | 页数 | 阅读重点 |
| --- | --- | ---: | --- |
| LoRA | [下载精读与复现报告](reports/LoRA/LoRA_精读与复现报告_修订版_20261011.docx) | 16 | 低秩与内在维度的区别、前向与梯度推导、初始化、手算例子、公平对照、合并与部署 |
| rsLoRA | [下载精读与复现报告](reports/rsLoRA/rsLoRA_精读与复现报告_修订版_20261011.docx) | 12 | 秩与缩放、首步更新期望、理论适用条件、初始化方差、SGD 与 Adam 的差异 |
| Differential Transformer | [下载精读与复现报告](reports/DifferentialTransformer/DifferentialTransformer_精读与复现报告_修订版_20261011.docx) | 14 | 差分注意力、负权重与抵消、完整梯度链、具体任务流程、指标冲突、机制反例 |

建议按 **LoRA → rsLoRA → Differential Transformer** 阅读；每篇也可独立阅读。前两篇聚焦参数高效微调，第三篇聚焦 Transformer 注意力机制的创新。

## 证据与结论边界

报告区分四类内容：

- **原作者结果**：来自论文或官方代码的结论，附原始来源，不视作本地实验结果。
- **本地验证**：在明确的小规模配置与协议下完成的机制、任务或部署检查，仅支持对应范围的结论。
- **观察与解释**：包括事后诊断和有限样本现象，不当作因果证据或普遍性能优势。
- **尚未复现或尚未执行**：原论文的大规模训练结论、未开展的设置及后续扩展建议。

LoRA 报告汇总十阶段工作；rsLoRA 与 Differential Transformer 按六阶段组织。rsLoRA 的历史训练对照是 LoRA 项目已有记录的子集，不重复计作新训练。Differential Transformer 的小型任务结果有优势与劣势并存的情况，报告保留准确率与损失等不同指标的冲突。

本次 **2026 年 10 月 11 日报告修订新增训练 0 次，新增模型前向 0 次**。修订补强技术叙述、解析推导、教学例子、既有结果解读和可证伪的后续实验建议；不将重绘已有结果计作新增实验。

## 原论文

- LoRA：[LoRA: Low-Rank Adaptation of Large Language Models](https://arxiv.org/abs/2106.09685v2)
- rsLoRA：[A Rank Stabilization Scaling Factor for Fine-Tuning with LoRA](https://arxiv.org/abs/2312.03732v1)（本报告使用 2023 年预印本版本）
- Differential Transformer：[ICLR 2025 论文页面](https://proceedings.iclr.cc/paper_files/paper/2025/hash/00b67df24009747e8bbed4c2c6f9c825-Abstract-Conference.html)

本仓库仅上传独立报告及文件清单。原论文只提供来源链接，不上传论文 PDF；模型权重、数据集和完整实验归档不包含在此次上传中。

