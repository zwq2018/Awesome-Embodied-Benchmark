# 具身基础模型 Benchmark 精选列表 [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

[English Version](README.md) | 中文版

## 目录

- [概述](#概述)
- [具身问答 (Q&A)](#具身问答-qa)
  - [2D 具身问答](#2d-具身问答)
  - [3D 具身问答](#3d-具身问答)
- [具身导航](#具身导航)
  - [目标导航](#目标导航)
  - [指令导航](#指令导航)
- [具身任务规划](#具身任务规划)
- [能力分类体系](#能力分类体系)
- [评估平台](#评估平台)
- [贡献指南](#贡献指南)

## 概述

具身 AI Benchmark 用于评估基础模型在感知、推理和与物理环境交互方面的能力。这些 Benchmark 可分为三大任务类型：

| 任务类型 | 描述 | Benchmark 数量 |
|----------|------|----------------|
| **具身问答** | 针对具身场景的视觉问答 | 15+ |
| **具身导航** | 基于目标或指令的环境导航 | 5+ |
| **具身任务规划** | 将复杂任务分解为可执行步骤 | 3+ |

## 具身问答 (Q&A)

### 2D 具身问答

#### OpenEQA

- **论文**: [arXiv:2402.07025](https://arxiv.org/abs/2402.07025) (CVPR 2024)
- **GitHub**: [facebookresearch/open-eqa](https://github.com/facebookresearch/open-eqa)
- **HuggingFace**: [weikaih/open-eqa](https://huggingface.co/datasets/weikaih/open-eqa)
- **项目主页**: [open-eqa.github.io](https://open-eqa.github.io)

**简介**: OpenEQA 是由 Meta FAIR 提出的具身问答 Benchmark，用于评估基础模型的具身问答能力。包含两类任务：情景记忆问答 (EMQA) 和开放世界问答 (OQA)，基于 HM3D 和 ScanNet 场景，共 1,636 个开放式问题。

**分类**: 3D 场景 / 开放世界 / 记忆推理 / 具身问答

**使用方式**: 使用 GPT-4 作为评判器对模型生成的自由文本答案进行评分 (GPT-Match 评估)。

---

#### VSI-Bench

- **论文**: [arXiv:2412.14171](https://arxiv.org/abs/2412.14171) (NeurIPS 2025)
- **GitHub**: [vision-x-nyu/thinking-in-space](https://github.com/vision-x-nyu/thinking-in-space)
- **HuggingFace**: [nyu-visionx/VSI-Bench](https://huggingface.co/datasets/nyu-visionx/VSI-Bench)
- **项目主页**: [vision-x-nyu.github.io](https://vision-x-nyu.github.io/thinking-in-space.github.io/)

**简介**: VSI-Bench 由 NYU Vision-X 团队提出，用于评估多模态大语言模型的视觉空间智能 (Visual-Spatial Intelligence)。基于视频序列，测试模型对 3D 空间的感知、记忆与回忆能力。

**分类**: 3D 视频 / 空间感知 / 空间推理 / 视觉空间智能

**使用方式**: 基于视频输入的空间推理问答，涵盖空间定位、距离估计、方向判断等子任务。

---

#### ERQA

- **论文**: [arXiv:2503.11117](https://arxiv.org/abs/2503.11117)
- **GitHub**: [embodiedreasoning/ERQA](https://github.com/embodiedreasoning/ERQA)

**简介**: 探索感知具身问答 (Exploration-Aware Embodied Question Answering) Benchmark。与传统 EQA 假设完整环境观测不同，ERQA 测试智能体在探索过程中的推理能力，强调动态探索场景下的问答。

**分类**: 动态探索 / 3D 场景 / 具身推理 / 多步推理

**License**: CC-BY-4.0

---

#### Where2Place

- **论文**: [arXiv:2406.10721](https://arxiv.org/abs/2406.10721) (RoboPoint 论文中提出)
- **GitHub**: [wentao-yuan/robopoint](https://github.com/wentaoyuan/robopoint)
- **HuggingFace**: [wentao-yuan/where2place](https://huggingface.co/datasets/wentao-yuan/where2place)

**简介**: 评估视觉语言模型的自由空间引用能力。包含 100 张真实世界杂乱环境图像，用空间关系语言描述目标放置位置。

**分类**: 2D 图像 / 空间定位 / 空间可用性 / 自由空间引用

**数据规模**: 100 张图像

**使用方式**: 给定图像和空间描述，模型预测可放置位置坐标，计算准确率。

---

#### RoBoVQA

- **论文**: [arXiv:2311.00899](https://arxiv.org/abs/2311.00899)
- **GitHub**: [google-deepmind/robovqa](https://github.com/google-deepmind/robovqa)
- **HuggingFace**: [lmms-lab/RoboVQA](https://huggingface.co/datasets/lmms-lab/RoboVQA)
- **项目主页**: [robovqa.github.io](https://robovqa.github.io/)

**简介**: Google DeepMind 提出的多模态长程推理 Benchmark。采用自底向上的数据收集策略，从真实机器人操作中收集 VQA 数据，支持长时间序列推理任务。

**分类**: 机器人操作 / 长程推理 / 多模态 / 真实世界

**License**: Apache 2.0

---

#### IndustryEQA

- **论文**: [arXiv:2505.20640](https://arxiv.org/abs/2505.20640)
- **GitHub**: [JackYFL/IndustryEQA](https://github.com/JackYFL/IndustryEQA)
- **HuggingFace**: [IndustryEQA/IndustryEQA](https://huggingface.co/datasets/IndustryEQA/IndustryEQA)

**简介**: 首个面向安全关键仓储场景的具身问答 Benchmark。基于 NVIDIA Isaac Sim 构建，提供包含工业资产、动态工作人员和危险情境的情景记忆视频，并附带直接答案与推理答案标注。

**分类**: 工业场景具身问答 / 安全关键推理 / 时序理解 / 空间理解

**数据规模**: 1,344 组问答（小型仓库 971 + 大型仓库 373），16.4 GB

**License**: MIT

---

#### UniEQA

- **论文**: [arXiv:2509.15273](https://arxiv.org/abs/2509.15273) (Embodied Arena 论文)
- **HuggingFace**: [TJURL-Lab/UniEQA](https://huggingface.co/datasets/TJURL-Lab/UniEQA)

**简介**: 天津大学提出的统一具身问答 Benchmark，属于 Embodied Arena 统一评估平台的一部分。覆盖多个能力维度，基于 HM3D 和 ScanNet 场景，包含约 4,002 个问题-图像-答案三元组。

**分类**: 统一评估 / 多维度能力 / 3D 场景 / 具身问答

**License**: BSD-3-Clause

**数据规模**: 约 4,002 条数据

---

#### VABench-Point

- **论文**: [arXiv:2505.08548](https://arxiv.org/abs/2505.08548) (ICLR 2026)
- **GitHub**: [pickxiguapi/embodied-fsd](https://github.com/pickxiguapi/embodied-fsd)
- **项目主页**: [embodied-fsd.github.io](https://embodied-fsd.github.io/)

**简介**: 天津大学 FSD (From Seeing to Doing) 项目的一部分。评估模型从自然语言指令生成空间可用性点的能力，包含 300 个人工标注问题，来自 OXE、BridgeData、Droid 数据集。

**分类**: 2D/3D / 空间可用性 / 视觉锚定生成 / 机器人操作

**评估方式**: 使用点准确率评估预测点的准确性，基线对比：FSD: 61.82%, GPT-4o: 9.30%, RoboPoint: 19.09%

---

#### PhyBlock

- **论文**: [arXiv:2506.08708](https://arxiv.org/abs/2506.08708) (NeurIPS 2025)
- **GitHub**: [PhyBlock/PhyBlock](https://github.com/PhyBlock/PhyBlock)
- **项目主页**: [phyblock.github.io](https://phyblock.github.io/)

**简介**: 渐进式物理理解与规划 Benchmark。通过 3D 积木组装任务评估多模态模型的物理常识理解、空间推理和规划能力，任务难度逐级递增。

**分类**: 3D / 物理常识 / 空间规划 / 积木组装 / 推理 + 规划

**License**: MIT

---

#### MineAnyBuild

- **论文**: [arXiv:2505.20148](https://arxiv.org/abs/2505.20148) (NeurIPS 2025 D&B Track)
- **GitHub**: [MineAnyBuild/MineAnyBuild](https://github.com/MineAnyBuild/MineAnyBuild)
- **项目主页**: [mineanybuild.github.io](https://mineanybuild.github.io/)

**简介**: 基于 Minecraft 开放世界环境的空间规划 Benchmark。评估 AI 智能体在开放世界中的空间规划与建筑构建能力。

**分类**: 开放世界 / 空间规划 / Minecraft / 3D 构建

### 3D 具身问答

#### ScanQA

- **论文**: [arXiv:2112.10482](https://arxiv.org/abs/2112.10482) (CVPR 2022)
- **GitHub**: [ATR-DBI/ScanQA](https://github.com/ATR-DBI/ScanQA)

**简介**: 3D 场景问答的开创性工作，基于 ScanNet 场景。提出 3D-QA 任务：给定 3D 点云场景和自然语言问题，模型需理解空间关系并回答。

**分类**: 3D 点云 / 空间场景理解 / 3D-QA

**使用方式**: 基于 ScanNet 3D 点云进行多选或开放问答，评估 EM 和 F1 等指标。

---

#### Scan2Cap

- **论文**: [arXiv:2012.02206](https://arxiv.org/abs/2012.02206) (CVPR 2021)
- **GitHub**: [daveredrum/Scan2Cap](https://github.com/daveredrum/Scan2Cap)
- **项目主页**: [daveredrum.github.io/Scan2Cap](https://daveredrum.github.io/Scan2Cap/)

**简介**: 由 TUM 和 SFU 提出的 3D 场景上下文感知密集描述任务。给定 3D 扫描，模型需定位物体并生成自然语言描述。

**分类**: 3D 点云 / 密集描述 / 物体定位 + 描述生成

**评估方式**: 使用 CiDEr、BLEU 指标评估生成描述质量，同时评估 3D 定位精度 (mIoU)。

---

#### ScanRefer

- **论文**: [arXiv:1912.08830](https://arxiv.org/abs/1912.08830) (ECCV 2020)
- **GitHub**: [daveredrum/ScanRefer](https://github.com/daveredrum/ScanRefer)
- **项目主页**: [daveredrum.github.io/ScanRefer](https://daveredrum.github.io/ScanRefer/)
- **Benchmark**: [kaldir.vc.in.tum.de/scanrefer_benchmark](http://kaldir.vc.in.tum.de/scanrefer_benchmark)

**简介**: 由 TUM 和 SFU 提出的 3D 物体定位任务。给定 RGB-D 扫描和自然语言描述，模型需在 3D 场景中定位目标物体。

**分类**: 3D 点云 / 物体定位 / 自然语言引用

**评估方式**: 评估 3D 定位精度 (Acc@0.25 和 Acc@0.5 IoU 阈值)。

---

#### SQA3D

- **论文**: [arXiv:2210.07474](https://arxiv.org/abs/2210.07474) (ICLR 2023)
- **GitHub**: [SilongYong/SQA3D](https://github.com/SilongYong/SQA3D)

**简介**: 由 BIGAI、UCLA、清华大学等机构提出的场景化 3D 问答任务。要求智能体理解自身在 3D 场景中的位置 (situated)，并据此回答问题。

**分类**: 3D 场景 / 场景化理解 / 空间推理 / 具身问答

**License**: Apache License

---

#### Multi3DRefer

- **论文**: [arXiv:2309.05251](https://arxiv.org/abs/2309.05251) (ICCV 2023)
- **GitHub**: [3dlg-hcvc/multi3drefer](https://github.com/3dlg-hcvc/multi3drefer)

**简介**: 由 SFU 3DLG-HCVC 提出，将传统单物体定位扩展为多物体定位。给定文本描述，模型需在 3D 场景中定位多个目标物体，支持零目标和多目标场景。

**分类**: 3D 点云 / 多物体定位 / 文本引用

**评估方式**: 使用 Acc@0.25 和 Acc@0.5 评估多物体 3D 定位精度。

**License**: MIT

## 具身导航

### 目标导航

#### MP3D (Matterport3D)

- **论文**: [arXiv:1709.06158](https://arxiv.org/abs/1709.06158)
- **GitHub**: [niessner/Matterport](https://github.com/niessner/Matterport)
- **HuggingFace**: [JunweiZheng/matterport3d](https://huggingface.co/datasets/JunweiZheng/matterport3d) (非官方)

**简介**: 大规模 RGB-D 数据集，包含 90 个建筑场景的 10,800 个全景视图 (194,400 张 RGB-D 图像)，提供表面重建、相机位姿、2D/3D 语义分割标注。

**分类**: 3D 场景理解数据集，支持多种视觉任务 (语义分割、关键点匹配等)，广泛用于具身导航研究。

**使用方式**: 需签署使用协议后下载。提供基准任务：图像关键点匹配、视图重叠预测、表面法线估计、区域分类、语义体素标记。

**模拟器**: 常与 Habitat 模拟器结合使用。

---

#### HM3D (Habitat Matterport 3D)

- **论文**: [arXiv:2109.08238](https://arxiv.org/abs/2109.08238)
- **GitHub**: [facebookresearch/habitat-matterport3d-dataset](https://github.com/facebookresearch/habitat-matterport3d-dataset)

**简介**: 包含 1,000 个高分辨率 3D 扫描的大型数据集，涵盖住宅、商业等建筑空间。学术界最大的 3D 室内数据集，提供 112.5k m² 的可导航空间。

**分类**: 3D 环境数据集，主要用于具身 AI 任务，如点目标导航 (PointNav)。

**使用方式**: 通过 Habitat 模拟器使用。论文中提供了在 HM3D 上训练和评估 PointNav 智能体的基准代码。

**模拟器**: Habitat 模拟器。

---

#### EB-Navigation

- **论文**: [arXiv:2502.09560](https://arxiv.org/abs/2502.09560) (EmbodiedBench 论文)
- **GitHub**: [EmbodiedBench/EmbodiedBench](https://github.com/EmbodiedBench/EmbodiedBench)
- **HuggingFace**: [EmbodiedBench/EB-Nav_trajectory_dataset](https://huggingface.co/datasets/EmbodiedBench/EB-Nav_trajectory_dataset)

**简介**: EmbodiedBench 基准的一部分，专注于低层级导航任务，用于评估多模态大语言模型作为具身智能体的能力。包含 1,128 个测试任务，覆盖高层和低层任务。

**分类**: 具身导航基准，评估 MLLM 的感知、推理和规划能力。

**使用方式**: 通过 EmbodiedBench 框架评估，需安装对应环境 (`embench_nav`)。支持闭源和开源模型评估，提供 Gym 风格 API。

**模拟器**: 基于 Habitat 模拟器。

### 指令导航

#### R2R-CE (连续环境中的 Room-to-Room)

- **数据来源**: [VLN-CE 项目](https://jacobkrantz.github.io/vlnce/data)

**简介**: 将经典 R2R (Room-to-Room) 数据集从离散环境 (Matterport3D Simulator) 适配到连续环境 (Habitat Simulator) 的版本，用于连续环境中的视觉语言导航 (VLN-CE)。

**分类**: 指令导航 (视觉语言导航) 在连续环境中。

**使用方式**: 通过 VLN-CE 代码库使用。数据集包含在 Habitat 模拟器中运行的 episodes，提供训练/验证/测试分割。

**模拟器**: Habitat 模拟器。

---

#### RxR-CE (连续环境中的 Room-across-Room)

- **论文**: [arXiv:2010.10726](https://arxiv.org/abs/2010.10726)
- **GitHub**: [google-research-datasets/RxR](https://github.com/google-research-datasets/RxR)

**简介**: 大规模多语言视觉语言导航数据集，包含 126k 条导航指令 (英语、印地语、泰卢固语) 和 126k 个导航演示，提供密集时空对齐标注。

**分类**: 指令导航 (视觉语言导航)，支持多语言。

**使用方式**: 通过 Habitat 模拟器使用，有专门的竞赛 (RxR Competition 和 RxR-Habitat Competition)。评估指标包括 SR、SPL、DTW 等。

**模拟器**: Habitat 模拟器。

## 具身任务规划

#### ET-Plan-Bench

- **论文**: [arXiv:2410.14682](https://arxiv.org/abs/2410.14682) (ICLR 2025 Workshop)
- **机构**: 华为诺亚方舟实验室 / 华为云

**简介**: 专注于使用 LLM 进行具身任务规划的 Benchmark，重点评估模型在空间和时序/因果认知方面的能力。通过自动化任务生成管道，利用 LLM 生成多样化、可控难度的具身任务。

**分类**: 空间关系约束、目标物体遮挡、时序与因果理解

**模拟器**: 多源模拟器后端，包括 Virtual Home 和 Habitat-Sim，提供即时环境反馈。

**评估指标**: 成功率 (Success Rate)、平均序列长度、最长公共子序列 (LCS)、移动距离等。

---

#### EB-ALFRED

- **论文**: [arXiv:2502.09560](https://arxiv.org/abs/2502.09560) (ICML 2025 Oral)
- **GitHub**: [EmbodiedBench/EmbodiedBench](https://github.com/EmbodiedBench/EmbodiedBench)
- **HuggingFace**: [EmbodiedBench/EB-ALFRED](https://huggingface.co/datasets/EmbodiedBench/EB-ALFRED)
- **项目主页**: [embodiedbench.github.io](https://embodiedbench.github.io/)

**简介**: EmbodiedBench 框架中的高级任务规划环境，基于 ALFRED 模拟器构建。评估 MLLM 在家庭场景中的任务分解与规划能力 (如"把书放到桌子上")。

**分类 (6 个能力子集)**:
- 基础任务解决 (Basic Task Solving)
- 常识推理 (Commonsense Reasoning)
- 复杂指令理解 (Complex Instruction Understanding)
- 空间感知 (Spatial Awareness)
- 视觉感知 (Visual Perception)
- 长期规划 (Long-horizon Planning)

**模拟器**: 基于 AI2-THOR 的 ALFRED 模拟器 (逼真的 3D 家庭环境)

**使用方式**:
```bash
conda activate embench
python -m embodiedbench.main env=eb-alf model_name=gpt-4o-mini exp_name='baseline'
```
支持闭源 API (OpenAI/Gemini/Claude) 和开源模型。

---

#### EB-Habitat

- **论文**: [arXiv:2502.09560](https://arxiv.org/abs/2502.09560) (ICML 2025 Oral)
- **GitHub**: [EmbodiedBench/EmbodiedBench](https://github.com/EmbodiedBench/EmbodiedBench)
- **HuggingFace**: [EmbodiedBench/EB-Habitat_trajectory_dataset](https://huggingface.co/datasets/EmbodiedBench/EB-Habitat_trajectory_dataset)
- **项目主页**: [embodiedbench.github.io](https://embodiedbench.github.io/)

**简介**: EmbodiedBench 框架中的另一个高级任务规划环境，基于 Habitat 模拟器构建，专注于语言驱动的物体重排 (Language Rearrangement) 任务。包含长期视野任务，涉及在 ReplicaCAD 场景中使用 YCB 物体进行多步骤操作。

**分类**: 与 EB-ALFRED 相同的 6 个能力子集 (基础任务解决、常识推理、复杂指令、空间感知、视觉感知、长期规划)。

**模拟器**: Habitat-Sim 0.3.0 + Habitat-Lab (Facebook Research)，使用 ReplicaCAD 场景和 YCB 物体数据集。

**使用方式**:
```bash
conda activate embench
python -m embodiedbench.main env=eb-hab model_name=gpt-4o-mini exp_name='baseline'
```

#### EmbodiedMemory-Bench

- **论文**: [arXiv:2609.28236](https://arxiv.org/abs/2609.28236)（2026 年 arXiv 预印本）
- **GitHub**: [ZJU-OmniAI/Embodied-Omni — embodied_memory](https://github.com/ZJU-OmniAI/Embodied-Omni/tree/main/embodied_memory)
- **HuggingFace**: [lzLiang/EmbodiedMemoryBench](https://huggingface.co/datasets/lzLiang/EmbodiedMemoryBench)
- **项目主页**: [EmbodiedMemoryBench](https://zju-omniai.github.io/Embodied-Omni/EmbodiedMemoryBench/)

**描述**: 在 2,554 个回合、四类任务中，评测智能体从观测与交互历史中建立、更新记忆，并将记忆用于后续具身行动的能力。

**能力类别**: 视觉感知、空间感知、时间与因果理解、长程规划；具体覆盖视觉细节记忆、动态状态追踪、交互结果记忆与经验泛化。

**仿真器**: AI2-THOR（仿真评测）。

**评估指标**: 成功率、记忆增强交互效率（MAE）。

**使用方法**: 安装官方包，准备公开数据及 manifest，并配置兼容 OpenAI 接口的推理服务。可先运行 `emem-bench evaluate --mode emem --model MODEL_ALIAS --base-url http://localhost:8000/v1 --data-root /path/to/data --manifest /path/to/data/manifests/full2554.jsonl --per-family 1 --output outputs/emem-smoke`。

**许可证**: 基准子目录代码为 Apache-2.0，数据集为 CC BY-NC 4.0；仿真资产遵循各自上游条款。

## 能力分类体系

基于 [Embodied Arena](https://arxiv.org/abs/2509.15273)，具身能力分为 7 个核心能力，包含 25 个细粒度维度：

### 感知层
1. **物体感知 (Object Perception)**
   - 物体类型 (Object Type)
   - 物体属性 (Object Property) - 颜色、形状、材质、大小
   - 物体状态 (Object State) - 开启、关闭、静止
   - 物体数量 (Object Count)

2. **空间感知 (Spatial Perception)**
   - 空间关系 (Spatial Relationship)
   - 空间距离 (Spatial Distance)
   - 空间定位 (Spatial Localization)
   - 空间大小 (Spatial Size)

3. **时序感知 (Temporal Perception)**
   - 时序描述 (Temporal Description)
   - 时序顺序 (Temporal Order)

### 认知层
4. **具身知识 (Embodied Knowledge)**
   - 通用知识 (General Knowledge)
   - 可用性预测 (Affordance Prediction)

5. **具身推理 (Embodied Reasoning)**
   - 物体推理 (Object Reasoning)
   - 空间推理 (Spatial Reasoning)
   - 时序推理 (Temporal Reasoning)
   - 知识推理 (Knowledge Reasoning)
   - 任务推理 (Task Reasoning)

### 任务执行层
6. **具身导航 (Embodied Navigation)**
   - 目标导航 (Object Navigation)
   - 位置导航 (Location Navigation)
   - 指令导航 (Instruction Navigation)

7. **具身任务规划 (Embodied Task Planning)**
   - 基础规划 (Basic Planning)
   - 视觉参考规划 (Visual Reference Planning)
   - 空间参考规划 (Spatial Reference Planning)
   - 时序参考规划 (Temporal Reference Planning)
   - 知识参考规划 (Knowledge Reference Planning)

## 评估平台

### EmbodiedEval

- **论文**: [arXiv:2501.11858](https://arxiv.org/abs/2501.11858)
- **GitHub**: [thunlp/EmbodiedEval](https://github.com/thunlp/EmbodiedEval)
- **HuggingFace**: [EmbodiedEval/EmbodiedEval](https://huggingface.co/datasets/EmbodiedEval/EmbodiedEval)
- **项目主页**: [embodiedeval.github.io](https://embodiedeval.github.io/)

**简介**: 一个用于评估多模态大语言模型作为具身智能体的综合交互式 Benchmark。它在统一仿真框架中覆盖 125 个 3D 场景、328 个任务，涉及导航、物体交互、社会交互、属性问答和空间问答。

**分类**: 统一交互评估 / 导航 + 交互 + 空间问答 / 3D 仿真

**使用方式**: 提供开源模拟器、可下载基准数据、基线智能体和指标脚本，支持端到端评估。

**License**: CC0-1.0 数据集 / MIT 代码

### Embodied Arena

- **论文**: [arXiv:2509.15273](https://arxiv.org/abs/2509.15273)
- **网站**: [embodied-arena.com](https://embodied-arena.com/)

**简介**: 一个全面、统一且不断演进的具身 AI 评估平台和排行榜。集成了 22+ 个多样化 Benchmark，涵盖三个领域 (2D/3D 具身问答、导航和任务规划)，以及来自全球 20+ 个机构的 30+ 个先进模型。

**特性**:
- 系统化的具身能力分类体系 (7 个核心能力，25 个细粒度维度)
- 统一的评估系统和标准化输入/输出格式
- LLM 驱动的自动化数据生成管道
- 三种类型的排行榜，支持 Benchmark 视图和能力视图
- 实时评估和排行榜更新

### EmbodiedBench

- **论文**: [arXiv:2502.09560](https://arxiv.org/abs/2502.09560) (ICML 2025 Oral)
- **GitHub**: [EmbodiedBench/EmbodiedBench](https://github.com/EmbodiedBench/EmbodiedBench)
- **项目主页**: [embodiedbench.github.io](https://embodiedbench.github.io/)

**简介**: 全面评估视觉驱动具身智能体的多模态大语言模型 Benchmark。具有多种动作层级和面向能力的评估，包含 1,128 个测试任务。

**环境**:
- EB-ALFRED (高层级，AI2-THOR)
- EB-Habitat (高层级，Habitat-Sim)
- EB-Navigation (低层级，Habitat-Sim)
- EB-Manipulation (低层级，CoppeliaSim/PyRep)

### StaticEmbodiedBench

- **论文**: [arXiv:2508.06553](https://arxiv.org/abs/2508.06553)
- **HuggingFace**: [xiaojiahao/StaticEmbodiedBench](https://huggingface.co/datasets/xiaojiahao/StaticEmbodiedBench)

**简介**: 一个即插即用的具身评测 Benchmark，用静态场景表示替代高成本的交互式评测。完整基准覆盖 42 个场景和 8 个核心维度，公开版本提供 200 条样本以支持开放研究。

**分类**: 静态评估 / 宏观规划 / 微观感知 / 阶段性推理

**使用方式**: 由 VLMEvalKit 原生支持，提供 `StaticEmbodiedBench` 和 `StaticEmbodiedBench_circular` 两种评测模式。

**License**: MIT

**数据规模**: 200 条公开样本，231 MB

## 贡献指南

欢迎贡献！请先阅读 [贡献指南](CONTRIBUTING.md)。

### 如何添加新 Benchmark

1. Fork 本仓库
2. 创建新分支：`git checkout -b add-benchmark-name`
3. 添加 Benchmark 条目，包含：
   - 论文链接 (arXiv 或会议)
   - GitHub 仓库
   - HuggingFace 数据集 (如有)
   - 简要描述
   - 分类和能力维度
   - 使用说明
4. 提交 Pull Request

### Benchmark 条目模板

```markdown
#### [Benchmark 名称]

- **论文**: [arXiv:XXXX.XXXXX](https://arxiv.org/abs/XXXX.XXXXX) ([会议/期刊])
- **GitHub**: [owner/repo](https://github.com/owner/repo)
- **HuggingFace**: [owner/dataset](https://huggingface.co/datasets/owner/dataset) (如有)
- **项目主页**: [project-page](https://project-page.github.io/) (如有)

**简介**: 简要描述该 Benchmark 评估的内容。

**分类**: [来自分类体系的能力维度]

**使用方式**: 如何使用该 Benchmark 进行评估。

**License**: [许可证类型]
```

## 许可证

[Apache License 2.0](./LICENSE)

在法律允许的范围内，贡献者已放弃本作品的所有版权和相关或邻接权。
