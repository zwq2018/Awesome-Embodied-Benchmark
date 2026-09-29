# Awesome Embodied Foundation Models Benchmark [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

English | [中文版](README_zh.md)

## Contents

- [Overview](#overview)
- [Embodied Question Answering (Q&A)](#embodied-question-answering-qa)
  - [2D Embodied Q&A](#2d-embodied-qa)
  - [3D Embodied Q&A](#3d-embodied-qa)
- [Embodied Navigation](#embodied-navigation)
  - [Object Navigation](#object-navigation)
  - [Instruction Navigation](#instruction-navigation)
- [Embodied Task Planning](#embodied-task-planning)
- [Capability Taxonomy](#capability-taxonomy)
- [Evaluation Platforms](#evaluation-platforms)
- [Contributing](#contributing)

## Overview

Embodied AI benchmarks evaluate the capabilities of foundation models in perceiving, reasoning about, and interacting with physical environments. These benchmarks can be categorized into three main task types:

| Task Type | Description | Benchmark Count |
|-----------|-------------|-----------------|
| **Embodied Q&A** | Visual question answering about embodied scenes | 15+ |
| **Embodied Navigation** | Navigating environments based on goals or instructions | 5+ |
| **Embodied Task Planning** | Decomposing complex tasks into executable steps | 3+ |

## Embodied Question Answering (Q&A)

### 2D Embodied Q&A

#### OpenEQA

- **Paper**: [arXiv:2402.07025](https://arxiv.org/abs/2402.07025) (CVPR 2024)
- **GitHub**: [facebookresearch/open-eqa](https://github.com/facebookresearch/open-eqa)
- **HuggingFace**: [weikaih/open-eqa](https://huggingface.co/datasets/weikaih/open-eqa)
- **Project**: [open-eqa.github.io](https://open-eqa.github.io)

**Description**: OpenEQA is a benchmark for evaluating foundation models' embodied question answering capabilities. It includes two task types: Episodic Memory QA (EMQA) and Open-world QA (OQA), based on HM3D and ScanNet scenes with 1,636 open-ended questions.

**Category**: 3D Scene / Open World / Memory Reasoning / Embodied QA

**Usage**: Uses GPT-4 as an evaluator to score model-generated free-text answers (GPT-Match evaluation).

---

#### VSI-Bench

- **Paper**: [arXiv:2412.14171](https://arxiv.org/abs/2412.14171) (NeurIPS 2025)
- **GitHub**: [vision-x-nyu/thinking-in-space](https://github.com/vision-x-nyu/thinking-in-space)
- **HuggingFace**: [nyu-visionx/VSI-Bench](https://huggingface.co/datasets/nyu-visionx/VSI-Bench)
- **Project**: [vision-x-nyu.github.io](https://vision-x-nyu.github.io/thinking-in-space.github.io/)

**Description**: VSI-Bench evaluates Visual-Spatial Intelligence of multimodal large language models. Based on video sequences, it tests models' perception, memory, and recall abilities of 3D spaces.

**Category**: 3D Video / Spatial Perception / Spatial Reasoning / Visual-Spatial Intelligence

**Usage**: Spatial reasoning Q&A based on video input, covering spatial localization, distance estimation, and direction judgment subtasks.

---

#### ERQA

- **Paper**: [arXiv:2503.11117](https://arxiv.org/abs/2503.11117)
- **GitHub**: [embodiedreasoning/ERQA](https://github.com/embodiedreasoning/ERQA)

**Description**: Exploration-Aware Embodied Question Answering benchmark. Unlike traditional EQA that assumes complete environment observation, ERQA tests agents' reasoning capabilities during exploration, emphasizing dynamic exploration scenarios.

**Category**: Dynamic Exploration / 3D Scene / Embodied Reasoning / Multi-step Reasoning

**License**: CC-BY-4.0

---

#### Where2Place

- **Paper**: [arXiv:2406.10721](https://arxiv.org/abs/2406.10721) (in RoboPoint paper)
- **GitHub**: [wentao-yuan/robopoint](https://github.com/wentaoyuan/robopoint)
- **HuggingFace**: [wentao-yuan/where2place](https://huggingface.co/datasets/wentao-yuan/where2place)

**Description**: Evaluates VLMs' free space reference capability. Contains 100 real-world cluttered environment images with spatial relationship language descriptions for target placement locations.

**Category**: 2D Image / Spatial Localization / Spatial Affordance / Free Space Reference

**Data Size**: 100 images

**Usage**: Given an image and spatial description, models predict placement coordinates, with accuracy evaluation.

---

#### RoBoVQA

- **Paper**: [arXiv:2311.00899](https://arxiv.org/abs/2311.00899)
- **GitHub**: [google-deepmind/robovqa](https://github.com/google-deepmind/robovqa)
- **HuggingFace**: [lmms-lab/RoboVQA](https://huggingface.co/datasets/lmms-lab/RoboVQA)
- **Project**: [robovqa.github.io](https://robovqa.github.io/)

**Description**: A multimodal long-horizon reasoning benchmark from Google DeepMind. Uses bottom-up data collection strategy from real robot operations for VQA data, supporting long temporal reasoning tasks.

**Category**: Robot Manipulation / Long-horizon Reasoning / Multimodal / Real World

**License**: Apache 2.0

---

#### IndustryEQA

- **Paper**: [arXiv:2505.20640](https://arxiv.org/abs/2505.20640)
- **GitHub**: [JackYFL/IndustryEQA](https://github.com/JackYFL/IndustryEQA)
- **HuggingFace**: [IndustryEQA/IndustryEQA](https://huggingface.co/datasets/IndustryEQA/IndustryEQA)

**Description**: The first benchmark dedicated to embodied question answering in safety-critical warehouse scenarios. Built on NVIDIA Isaac Sim, it provides episodic-memory videos with industrial assets, dynamic human workers, and hazardous situations, plus direct-answer and reasoning annotations.

**Category**: Industrial EQA / Safety-critical Reasoning / Temporal Understanding / Spatial Understanding

**Data Size**: 1,344 QA pairs (971 small-warehouse + 373 large-warehouse), 16.4 GB

**License**: MIT

---

#### UniEQA

- **Paper**: [arXiv:2509.15273](https://arxiv.org/abs/2509.15273) (Embodied Arena paper)
- **HuggingFace**: [TJURL-Lab/UniEQA](https://huggingface.co/datasets/TJURL-Lab/UniEQA)

**Description**: A unified Embodied QA benchmark from Tianjin University, part of the Embodied Arena evaluation platform. Covers multiple capability dimensions based on HM3D and ScanNet scenes with ~4,002 question-image-answer triplets.

**Category**: Unified Evaluation / Multi-dimensional Capability / 3D Scene / Embodied QA

**License**: BSD-3-Clause

**Data Size**: ~4,002 samples

---

#### VABench-Point

- **Paper**: [arXiv:2505.08548](https://arxiv.org/abs/2505.08548) (ICLR 2026)
- **GitHub**: [pickxiguapi/embodied-fsd](https://github.com/pickxiguapi/embodied-fsd)
- **Project**: [embodied-fsd.github.io](https://embodied-fsd.github.io/)

**Description**: Part of the FSD (From Seeing to Doing) project from Tianjin University. Evaluates models' ability to generate spatial affordance points from natural language instructions, with 300 human-annotated questions from OXE, BridgeData, and Droid datasets.

**Category**: 2D/3D / Spatial Affordance / Visual Grounding Generation / Robot Manipulation

**Evaluation**: Point Accuracy for predicted points, with baseline comparisons: FSD: 61.82%, GPT-4o: 9.30%, RoboPoint: 19.09%

---

#### PhyBlock

- **Paper**: [arXiv:2506.08708](https://arxiv.org/abs/2506.08708) (NeurIPS 2025)
- **GitHub**: [PhyBlock/PhyBlock](https://github.com/PhyBlock/PhyBlock)
- **Project**: [phyblock.github.io](https://phyblock.github.io/)

**Description**: Progressive physical understanding and planning benchmark. Evaluates multimodal models' physical commonsense understanding, spatial reasoning, and planning capabilities through 3D block assembly tasks with progressive difficulty levels.

**Category**: 3D / Physical Commonsense / Spatial Planning / Block Assembly / Reasoning + Planning

**License**: MIT

---

#### MineAnyBuild

- **Paper**: [arXiv:2505.20148](https://arxiv.org/abs/2505.20148) (NeurIPS 2025 D&B Track)
- **GitHub**: [MineAnyBuild/MineAnyBuild](https://github.com/MineAnyBuild/MineAnyBuild)
- **Project**: [mineanybuild.github.io](https://mineanybuild.github.io/)

**Description**: Spatial planning benchmark based on Minecraft open world environment. Evaluates AI agents' spatial planning and construction capabilities in open worlds.

**Category**: Open World / Spatial Planning / Minecraft / 3D Construction

### 3D Embodied Q&A

#### ScanQA

- **Paper**: [arXiv:2112.10482](https://arxiv.org/abs/2112.10482) (CVPR 2022)
- **GitHub**: [ATR-DBI/ScanQA](https://github.com/ATR-DBI/ScanQA)

**Description**: A pioneering work for 3D scene question answering based on ScanNet scenes. Proposes the 3D-QA task: given a 3D point cloud scene and natural language question, models need to understand spatial relationships and answer.

**Category**: 3D Point Cloud / Spatial Scene Understanding / 3D-QA

**Usage**: Based on ScanNet 3D point clouds for multiple-choice or open-ended Q&A, evaluating EM and F1 metrics.

---

#### Scan2Cap

- **Paper**: [arXiv:2012.02206](https://arxiv.org/abs/2012.02206) (CVPR 2021)
- **GitHub**: [daveredrum/Scan2Cap](https://github.com/daveredrum/Scan2Cap)
- **Project**: [daveredrum.github.io/Scan2Cap](https://daveredrum.github.io/Scan2Cap/)

**Description**: Context-aware dense captioning in 3D scenes from TUM and SFU. Given 3D scans, models need to localize objects and generate natural language descriptions.

**Category**: 3D Point Cloud / Dense Captioning / Object Localization + Description Generation

**Evaluation**: CiDEr, BLEU metrics for description quality, and mIoU for 3D localization precision.

---

#### ScanRefer

- **Paper**: [arXiv:1912.08830](https://arxiv.org/abs/1912.08830) (ECCV 2020)
- **GitHub**: [daveredrum/ScanRefer](https://github.com/daveredrum/ScanRefer)
- **Project**: [daveredrum.github.io/ScanRefer](https://daveredrum.github.io/ScanRefer/)
- **Benchmark**: [kaldir.vc.in.tum.de/scanrefer_benchmark](http://kaldir.vc.in.tum.de/scanrefer_benchmark)

**Description**: 3D object localization task from TUM and SFU. Given RGB-D scans and natural language descriptions, models need to localize target objects in 3D scenes.

**Category**: 3D Point Cloud / Object Localization / Natural Language Reference

**Evaluation**: 3D localization accuracy (Acc@0.25 and Acc@0.5 IoU thresholds).

---

#### SQA3D

- **Paper**: [arXiv:2210.07474](https://arxiv.org/abs/2210.07474) (ICLR 2023)
- **GitHub**: [SilongYong/SQA3D](https://github.com/SilongYong/SQA3D)

**Description**: Situated Question Answering in 3D Scenes from BIGAI, UCLA, and Tsinghua. Requires agents to understand their own position in 3D scenes (situated) and answer questions accordingly.

**Category**: 3D Scene / Situated Understanding / Spatial Reasoning / Embodied QA

**License**: Apache License

---

#### Multi3DRefer

- **Paper**: [arXiv:2309.05251](https://arxiv.org/abs/2309.05251) (ICCV 2023)
- **GitHub**: [3dlg-hcvc/multi3drefer](https://github.com/3dlg-hcvc/multi3drefer)

**Description**: Extends traditional single-object localization to multi-object localization from SFU 3DLG-HCVC. Given text descriptions, models need to localize multiple target objects in 3D scenes, supporting zero-target and multi-target scenarios.

**Category**: 3D Point Cloud / Multi-object Localization / Text Reference

**Evaluation**: Acc@0.25 and Acc@0.5 for multi-object 3D localization precision.

**License**: MIT

## Embodied Navigation

### Object Navigation

#### MP3D (Matterport3D)

- **Paper**: [arXiv:1709.06158](https://arxiv.org/abs/1709.06158)
- **GitHub**: [niessner/Matterport](https://github.com/niessner/Matterport)
- **HuggingFace**: [JunweiZheng/matterport3d](https://huggingface.co/datasets/JunweiZheng/matterport3d) (unofficial)

**Description**: Large-scale RGB-D dataset containing 90 building scenes with 10,800 panoramic views (194,400 RGB-D images). Provides surface reconstruction, camera poses, and 2D/3D semantic segmentation annotations.

**Category**: 3D Scene Understanding Dataset, supports various visual tasks (semantic segmentation, keypoint matching, etc.), widely used in embodied navigation research.

**Usage**: Requires signing usage agreement for download. Provides benchmark tasks: image keypoint matching, view overlap prediction, surface normal estimation, region classification, semantic voxel labeling.

**Simulator**: Often combined with Habitat simulator.

---

#### HM3D (Habitat Matterport 3D)

- **Paper**: [arXiv:2109.08238](https://arxiv.org/abs/2109.08238)
- **GitHub**: [facebookresearch/habitat-matterport3d-dataset](https://github.com/facebookresearch/habitat-matterport3d-dataset)

**Description**: Large-scale dataset with 1,000 high-resolution 3D scans covering residential and commercial spaces. The largest 3D indoor dataset in academia with 112.5k m² navigable space.

**Category**: 3D Environment Dataset, primarily for embodied AI tasks like Point Goal Navigation (PointNav).

**Usage**: Used through Habitat simulator. Paper provides benchmark code for training and evaluating PointNav agents on HM3D.

**Simulator**: Habitat simulator.

---

#### EB-Navigation

- **Paper**: [arXiv:2502.09560](https://arxiv.org/abs/2502.09560) (EmbodiedBench paper)
- **GitHub**: [EmbodiedBench/EmbodiedBench](https://github.com/EmbodiedBench/EmbodiedBench)
- **HuggingFace**: [EmbodiedBench/EB-Nav_trajectory_dataset](https://huggingface.co/datasets/EmbodiedBench/EB-Nav_trajectory_dataset)

**Description**: Part of EmbodiedBench benchmark, focusing on low-level navigation tasks. Evaluates multimodal large language models' capabilities as embodied agents with 1,128 test tasks covering high and low-level tasks.

**Category**: Embodied Navigation Benchmark, evaluates MLLMs' perception, reasoning, and planning capabilities.

**Usage**: Evaluated through EmbodiedBench framework, requires installing corresponding environment (`embench_nav`). Supports closed-source and open-source model evaluation with Gym-style API.

**Simulator**: Based on Habitat simulator.

### Instruction Navigation

#### R2R-CE (Room-to-Room in Continuous Environments)

- **Data Source**: [VLN-CE project](https://jacobkrantz.github.io/vlnce/data)

**Description**: Adaptation of classic R2R (Room-to-Room) dataset from discrete environment (Matterport3D Simulator) to continuous environment (Habitat Simulator) for Vision-Language Navigation in Continuous Environments (VLN-CE).

**Category**: Instruction Navigation (Vision-Language Navigation) in continuous environments.

**Usage**: Used through VLN-CE codebase. Dataset contains episodes for running in Habitat simulator with training/validation/test splits.

**Simulator**: Habitat simulator.

---

#### RxR-CE (Room-across-Room in Continuous Environments)

- **Paper**: [arXiv:2010.10726](https://arxiv.org/abs/2010.10726)
- **GitHub**: [google-research-datasets/RxR](https://github.com/google-research-datasets/RxR)

**Description**: Large-scale multilingual vision-and-language navigation dataset with 126k navigation instructions (English, Hindi, Telugu) and 126k navigation demonstrations, providing dense spatiotemporal alignment annotations.

**Category**: Instruction Navigation (Vision-Language Navigation), supports multiple languages.

**Usage**: Used through Habitat simulator, with dedicated competitions (RxR Competition and RxR-Habitat Competition). Evaluation metrics include SR, SPL, DTW, etc.

**Simulator**: Habitat simulator.

## Embodied Task Planning

#### ET-Plan-Bench

- **Paper**: [arXiv:2410.14682](https://arxiv.org/abs/2410.14682) (ICLR 2025 Workshop)
- **Institution**: Huawei Noah's Ark Lab / Huawei Cloud

**Description**: A benchmark focused on embodied task planning using LLMs, emphasizing evaluation of models' spatial and temporal/causal cognition capabilities. Uses automated task generation pipeline with LLM to generate diverse, controllable difficulty embodied tasks.

**Category**: Spatial Relation Constraint, Occlusion for Target Objects, Temporal & Causal Understanding

**Simulator**: Multi-source simulator backend including Virtual Home and Habitat-Sim, providing immediate environment feedback.

**Evaluation Metrics**: Success Rate, Average Sequence Length, LCS (Longest Common Subsequence), Moving Distance, etc.

---

#### EB-ALFRED

- **Paper**: [arXiv:2502.09560](https://arxiv.org/abs/2502.09560) (ICML 2025 Oral)
- **GitHub**: [EmbodiedBench/EmbodiedBench](https://github.com/EmbodiedBench/EmbodiedBench)
- **HuggingFace**: [EmbodiedBench/EB-ALFRED](https://huggingface.co/datasets/EmbodiedBench/EB-ALFRED)
- **Project**: [embodiedbench.github.io](https://embodiedbench.github.io/)

**Description**: High-level task planning environment in EmbodiedBench framework, based on ALFRED simulator. Evaluates MLLM's task decomposition and planning capabilities in household scenarios (e.g., "put the book on the table").

**Category (6 Capability Subsets)**:
- Basic Task Solving
- Commonsense Reasoning
- Complex Instruction Understanding
- Spatial Awareness
- Visual Perception
- Long-horizon Planning

**Simulator**: ALFRED simulator based on AI2-THOR (Photorealistic 3D home environments)

**Usage**:
```bash
conda activate embench
python -m embodiedbench.main env=eb-alf model_name=gpt-4o-mini exp_name='baseline'
```
Supports closed-source APIs (OpenAI/Gemini/Claude) and open-source models.

---

#### EB-Habitat

- **Paper**: [arXiv:2502.09560](https://arxiv.org/abs/2502.09560) (ICML 2025 Oral)
- **GitHub**: [EmbodiedBench/EmbodiedBench](https://github.com/EmbodiedBench/EmbodiedBench)
- **HuggingFace**: [EmbodiedBench/EB-Habitat_trajectory_dataset](https://huggingface.co/datasets/EmbodiedBench/EB-Habitat_trajectory_dataset)
- **Project**: [embodiedbench.github.io](https://embodiedbench.github.io/)

**Description**: Another high-level task planning environment in EmbodiedBench framework, based on Habitat simulator. Focuses on Language Rearrangement tasks with long-horizon tasks involving multi-step operations in ReplicaCAD scenes using YCB objects.

**Category**: Same 6 capability subsets as EB-ALFRED (basic task solving, commonsense reasoning, complex instruction, spatial awareness, visual perception, long-horizon planning).

**Simulator**: Habitat-Sim 0.3.0 + Habitat-Lab (Facebook Research), using ReplicaCAD scenes and YCB object dataset.

**Usage**:
```bash
conda activate embench
python -m embodiedbench.main env=eb-hab model_name=gpt-4o-mini exp_name='baseline'
```

#### EmbodiedMemory-Bench

- **Paper**: [arXiv:2609.28236](https://arxiv.org/abs/2609.28236) (arXiv preprint, 2026)
- **GitHub**: [ZJU-OmniAI/Embodied-Omni — embodied_memory](https://github.com/ZJU-OmniAI/Embodied-Omni/tree/main/embodied_memory)
- **HuggingFace**: [lzLiang/EmbodiedMemoryBench](https://huggingface.co/datasets/lzLiang/EmbodiedMemoryBench)
- **Project**: [EmbodiedMemoryBench](https://zju-omniai.github.io/Embodied-Omni/EmbodiedMemoryBench/)

**Description**: Evaluates how agents build and update memory from observation and interaction history, then use it for later embodied actions across 2,554 episodes and four task families.

**Category**: Visual Perception, Spatial Awareness, Temporal & Causal Understanding, Long-horizon Planning; with visual recall, dynamic tracking, interaction-outcome memory, and experience generalization.

**Simulator**: AI2-THOR (simulation).

**Evaluation Metrics**: Success rate and memory-augmented efficiency (MAE).

**Usage**: Install the official package, prepare the released dataset and manifest, and configure an OpenAI-compatible inference endpoint. Start with `emem-bench evaluate --mode emem --model MODEL_ALIAS --base-url http://localhost:8000/v1 --data-root /path/to/data --manifest /path/to/data/manifests/full2554.jsonl --per-family 1 --output outputs/emem-smoke`.

**License**: Code: Apache-2.0 (benchmark subdirectory); dataset: CC BY-NC 4.0. Simulator assets retain their upstream terms.

## Capability Taxonomy

Based on [Embodied Arena](https://arxiv.org/abs/2509.15273), embodied capabilities are categorized into 7 core capabilities with 25 fine-grained dimensions:

### Perception Level
1. **Object Perception**
   - Object Type
   - Object Property (color, shape, material, size)
   - Object State (open, closed, stationary)
   - Object Count

2. **Spatial Perception**
   - Spatial Relationship
   - Spatial Distance
   - Spatial Localization
   - Spatial Size

3. **Temporal Perception**
   - Temporal Description
   - Temporal Order

### Cognition Level
4. **Embodied Knowledge**
   - General Knowledge
   - Affordance Prediction

5. **Embodied Reasoning**
   - Object Reasoning
   - Spatial Reasoning
   - Temporal Reasoning
   - Knowledge Reasoning
   - Task Reasoning

### Task Execution Level
6. **Embodied Navigation**
   - Object Navigation
   - Location Navigation
   - Instruction Navigation

7. **Embodied Task Planning**
   - Basic Planning
   - Visual Reference Planning
   - Spatial Reference Planning
   - Temporal Reference Planning
   - Knowledge Reference Planning

## Evaluation Platforms

### EmbodiedEval

- **Paper**: [arXiv:2501.11858](https://arxiv.org/abs/2501.11858)
- **GitHub**: [thunlp/EmbodiedEval](https://github.com/thunlp/EmbodiedEval)
- **HuggingFace**: [EmbodiedEval/EmbodiedEval](https://huggingface.co/datasets/EmbodiedEval/EmbodiedEval)
- **Project**: [embodiedeval.github.io](https://embodiedeval.github.io/)

**Description**: A comprehensive interactive benchmark for evaluating MLLMs as embodied agents. It spans 328 tasks across 125 3D scenes and covers navigation, object interaction, social interaction, attribute QA, and spatial QA in one simulation framework.

**Category**: Unified Interactive Evaluation / Navigation + Interaction + Spatial QA / 3D Simulation

**Usage**: Includes an open-source simulator, downloadable benchmark data, baseline agents, and metric scripts for end-to-end evaluation.

**License**: CC0-1.0 dataset / MIT code

### Embodied Arena

- **Paper**: [arXiv:2509.15273](https://arxiv.org/abs/2509.15273)
- **Website**: [embodied-arena.com](https://embodied-arena.com/)

**Description**: A comprehensive, unified, and evolving evaluation platform and leaderboards for Embodied AI. Integrates 22+ diverse benchmarks across three domains (2D/3D Embodied Q&A, Navigation, and Task Planning) and 30+ advanced models from 20+ worldwide institutes.

**Features**:
- Systematic embodied capability taxonomy (7 core capabilities, 25 fine-grained dimensions)
- Unified evaluation system with standardized input/output formats
- LLM-driven automated data generation pipeline
- Three types of leaderboards with benchmark view and capability view
- Real-time evaluation and leaderboard updates

### EmbodiedBench

- **Paper**: [arXiv:2502.09560](https://arxiv.org/abs/2502.09560) (ICML 2025 Oral)
- **GitHub**: [EmbodiedBench/EmbodiedBench](https://github.com/EmbodiedBench/EmbodiedBench)
- **Project**: [embodiedbench.github.io](https://embodiedbench.github.io/)

**Description**: Comprehensive benchmarking multimodal large language models for vision-driven embodied agents. Features various action levels and capability-oriented evaluation with 1,128 test tasks.

**Environments**:
- EB-ALFRED (High-Level, AI2-THOR)
- EB-Habitat (High-Level, Habitat-Sim)
- EB-Navigation (Low-Level, Habitat-Sim)
- EB-Manipulation (Low-Level, CoppeliaSim/PyRep)

### StaticEmbodiedBench

- **Paper**: [arXiv:2508.06553](https://arxiv.org/abs/2508.06553)
- **HuggingFace**: [xiaojiahao/StaticEmbodiedBench](https://huggingface.co/datasets/xiaojiahao/StaticEmbodiedBench)

**Description**: A plug-and-play benchmark that replaces expensive interactive evaluation with static scene representations. The full benchmark covers 42 scenarios and 8 core dimensions, while the public release exposes a 200-sample subset for open research.

**Category**: Static Evaluation / Macro Planning / Micro Perception / Stage-wise Reasoning

**Usage**: Supported by VLMEvalKit with `StaticEmbodiedBench` and `StaticEmbodiedBench_circular` evaluation modes.

**License**: MIT

**Data Size**: 200 public samples, 231 MB

## Contributing

Contributions welcome! Read the [contribution guidelines](CONTRIBUTING.md) first.

### How to Add a New Benchmark

1. Fork this repository
2. Create a new branch: `git checkout -b add-benchmark-name`
3. Add your benchmark entry with:
   - Paper link (arXiv or conference)
   - GitHub repository
   - HuggingFace dataset (if available)
   - Brief description
   - Category and capability dimensions
   - Usage instructions
4. Submit a pull request

### Benchmark Entry Template

```markdown
#### [Benchmark Name]

- **Paper**: [arXiv:XXXX.XXXXX](https://arxiv.org/abs/XXXX.XXXXX) ([Conference/Journal])
- **GitHub**: [owner/repo](https://github.com/owner/repo)
- **HuggingFace**: [owner/dataset](https://huggingface.co/datasets/owner/dataset) (if available)
- **Project**: [project-page](https://project-page.github.io/) (if available)

**Description**: Brief description of what this benchmark evaluates.

**Category**: [Capability dimensions from taxonomy]

**Usage**: How to use this benchmark for evaluation.

**License**: [License type]
```

## License

[Apache License 2.0](./LICENSE)

To the extent possible under law, the contributors have waived all copyright and related or neighboring rights to this work.
