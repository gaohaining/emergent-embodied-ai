# 论文跟踪

论文原文索引见 [papers-pdf/README.md](papers-pdf/README.md)。策略模型论文阅读比较见 [paper-notes/robot-strategy-models-comparison.md](paper-notes/robot-strategy-models-comparison.md)，逐篇精读见 [paper-notes/robot-strategy-models-detailed.md](paper-notes/robot-strategy-models-detailed.md)。这组笔记不把路线强绑定到 Manipulation，而是按机器人策略模型、VLA、动作生成、数据工具链和世界模型来组织。

| 年份 | 标题 | 机构 | 方向 | 关键贡献 | 证据强度 | 链接 | 笔记 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 2024 | OpenVLA: An Open-Source Vision-Language-Action Model | Stanford / UC Berkeley 等 | VLA | 开源 VLA 路线代表，需要跟踪复现和实机泛化 | 论文 / 项目页 / 代码 | [arXiv](https://arxiv.org/abs/2406.09246) | [精读](paper-notes/2024-openvla.md) / [路线笔记](model-paper-notes.md#11-openvla-an-open-source-vision-language-action-model) |
| 2024 | Open X-Embodiment: Robotic Learning Datasets and RT-X Models | 多机构 | data / cross-embodiment | 跨本体机器人数据和 RT-X 模型的重要节点 | 论文 / 项目页 / 数据集 | 待补链接 |  |
| 2024 | Octo: An Open-Source Generalist Robot Policy | UC Berkeley 等 | policy | 基于大规模机器人数据的通用策略代表 | 论文 / 项目页 / 代码 | [arXiv](https://arxiv.org/abs/2405.12213) | [速读](model-paper-notes.md#12-octo-an-open-source-generalist-robot-policy) |
| 2024 | pi0: A Vision-Language-Action Flow Model for General Robot Control | Physical Intelligence | VLA / flow policy | flow matching 与通用机器人控制路线代表 | 论文 / 项目页 | [arXiv](https://arxiv.org/abs/2410.24164) | [速读](model-paper-notes.md#13-pi0-a-vision-language-action-flow-model-for-general-robot-control) |
| 2024 | RDT-1B: a Diffusion Foundation Model for Bimanual Manipulation | 清华等 | bimanual foundation model | 双臂操作 diffusion foundation model，补强双臂与扩散基础模型路线 | 论文 / 项目页 / 代码 | [arXiv](https://arxiv.org/abs/2410.07864) |  |
| 2024 | TraceVLA: Visual Trace Prompting Enhances Spatial-Temporal Awareness for Generalist Robotic Policies | Microsoft Research 等 | VLA / spatial-temporal prompting | 用 visual trace prompt 增强通用策略的时空感知与跨本体泛化 | 论文 / 项目页 | [arXiv](https://arxiv.org/abs/2412.10345) |  |
| 2025 | SpatialVLA: Exploring Spatial Representations for Visual-Language-Action Model | 上海 AI Lab 等 | VLA / spatial representation | 通过 Ego3D PE 和 adaptive action grids 强化 VLA 的空间表示 | 论文 / 项目页 | [arXiv](https://arxiv.org/abs/2501.15830) |  |
| 2023 | VoxPoser: Composable 3D Value Maps for Robotic Manipulation with Language Models | Stanford / MIT / Columbia 等 | LLM + 3D manipulation | 用语言模型和视觉模型组合 3D value map / constraint map，把高层语言规划接到低层运动规划 | 论文 / 项目页 / 代码 | [arXiv](https://arxiv.org/abs/2307.05973) | [精读](paper-notes/2023-voxposer.md) |
| 2024 | FoundationPose: Unified 6D Pose Estimation and Tracking of Novel Objects | NVIDIA | perception / pose estimation | 统一新物体的 6D 位姿估计与跟踪，补强“看见物体”到“可操作姿态”的关键环节 | 论文 / 项目页 / 代码 | [项目页](https://nvlabs.github.io/FoundationPose/) | [精读](paper-notes/2024-foundationpose.md) |
| 2026 | Image Generators are Generalist Vision Learners（Vision Banana） | Google DeepMind | perception / 生成即感知 | 文生图基座轻量微调即成通用视觉模型，分割超 SAM 3、深度超 Depth Anything V3，提出“生成式预训练=视觉预训练” | 论文（未见独立复现） | [arXiv](https://arxiv.org/abs/2604.20329) | [精读](paper-notes/2026-vision-banana.md) |
| 2020 | Object Goal Navigation using Goal-Oriented Semantic Exploration | Georgia Tech / Facebook AI | navigation / semantic mapping | 目标导向语义探索（SemExp）是 object-goal navigation 的经典代表，体现模块化导航栈价值 | 论文 / 项目页 / 代码 | [arXiv](https://arxiv.org/abs/2007.00643) |  |
| 2025 | OmniManip: Towards General Robotic Manipulation via Object-Centric Interaction Primitives as Spatial Constraints | NUS / Tsinghua / Shanghai AI Lab 等 | 3D manipulation / spatial constraints | 用 object-centric interaction primitives 把 VLM 的高层语义与精细 3D 操作约束连接起来 | 论文 / 项目页 | [arXiv](https://arxiv.org/abs/2501.03841) |  |
| 2025 | RoboTwin 2.0: A Scalable Data Generator and Benchmark with Strong Domain Randomization for Robust Bimanual Robotic Manipulation | RoboTwin 团队 | simulator / benchmark / data | 双臂操作的强随机化数据合成与 benchmark，适合补“仿真-数据-评测”链路 | 论文 / 项目页 / 代码 | [arXiv](https://arxiv.org/abs/2506.18088) |  |
| 2023 | Foundation Models in Robotics: Applications, Challenges, and the Future | 多机构 | survey | 梳理 foundation models 与机器人栈的关系 | 综述 / 配套仓库 | 待补链接 |  |

## 模型谱系代表论文清单

| 年份 | 标题 | 方向 | 关键贡献 | 链接 | 笔记 |
| --- | --- | --- | --- | --- | --- |
| 2022 | Do As I Can, Not As I Say: Grounding Language in Robotic Affordances | LLM / planning | 用 LLM 语义分数和 affordance/value score 共同选择可执行技能 | [arXiv](https://arxiv.org/abs/2204.01691) | [速读](model-paper-notes.md#1-do-as-i-can-not-as-i-say-grounding-language-in-robotic-affordances) |
| 2022 | Inner Monologue: Embodied Reasoning through Planning with Language Models | LLM / feedback | 把环境反馈、人类反馈和成功检测语言化后接回规划循环 | [arXiv](https://arxiv.org/abs/2207.05608) | [速读](model-paper-notes.md#2-inner-monologue-embodied-reasoning-through-planning-with-language-models) |
| 2022 | Code as Policies: Language Model Programs for Embodied Control | LLM / code policy | 让 LLM 生成调用感知、几何和控制 API 的可执行策略代码 | [arXiv](https://arxiv.org/abs/2209.07753) | [速读](model-paper-notes.md#3-code-as-policies-language-model-programs-for-embodied-control) |
| 2021 | Learning Transferable Visual Models From Natural Language Supervision | VLM | CLIP，用图文对比学习获得开放词汇视觉表征 | [arXiv](https://arxiv.org/abs/2103.00020) | [速读](model-paper-notes.md#4-learning-transferable-visual-models-from-natural-language-supervision) |
| 2022 | Flamingo: a Visual Language Model for Few-Shot Learning | VLM | 支持图像/视频/文本交错输入的 few-shot VLM | [arXiv](https://arxiv.org/abs/2204.14198) | [速读](model-paper-notes.md#5-flamingo-a-visual-language-model-for-few-shot-learning) |
| 2023 | PaLM-E: An Embodied Multimodal Language Model | VLM / embodied LLM | 把视觉和机器人状态接入多模态语言模型做具身推理 | [arXiv](https://arxiv.org/abs/2303.03378) | [速读](model-paper-notes.md#6-palm-e-an-embodied-multimodal-language-model) |
| 2022 | RT-1: Robotics Transformer for Real-World Control at Scale | VAM / robot transformer | 大规模真实机器人数据训练 Transformer 策略 | [arXiv](https://arxiv.org/abs/2212.06817) | [速读](model-paper-notes.md#7-rt-1-robotics-transformer-for-real-world-control-at-scale) |
| 2022 | BC-Z: Zero-Shot Task Generalization with Robotic Imitation Learning | VAM / imitation | 多任务模仿学习中的零样本任务泛化 | [arXiv](https://arxiv.org/abs/2202.02005) | [速读](model-paper-notes.md#8-bc-z-zero-shot-task-generalization-with-robotic-imitation-learning) |
| 2022 | R3M: A Universal Visual Representation for Robot Manipulation | VAM / representation | 用人类视频预训练机器人操作视觉表征 | [arXiv](https://arxiv.org/abs/2203.12601) | [速读](model-paper-notes.md#9-r3m-a-universal-visual-representation-for-robot-manipulation) |
| 2023 | RT-2: Vision-Language-Action Models Transfer Web Knowledge to Robotic Control | VLA | 将互联网 VLM 知识通过动作 token 迁移到机器人控制 | [arXiv](https://arxiv.org/abs/2307.15818) | [速读](model-paper-notes.md#10-rt-2-vision-language-action-models-transfer-web-knowledge-to-robotic-control) |
| 2024 | OpenVLA: An Open-Source Vision-Language-Action Model | VLA | 开源 7B VLA，支持微调和真实机器人部署研究 | [arXiv](https://arxiv.org/abs/2406.09246) | [精读](paper-notes/2024-openvla.md) / [路线笔记](model-paper-notes.md#11-openvla-an-open-source-vision-language-action-model) |
| 2024 | Octo: An Open-Source Generalist Robot Policy | Generalist policy | 基于 Open X-Embodiment 的通用机器人策略初始化器 | [arXiv](https://arxiv.org/abs/2405.12213) | [速读](model-paper-notes.md#12-octo-an-open-source-generalist-robot-policy) |
| 2024 | pi0: A Vision-Language-Action Flow Model for General Robot Control | VLA / flow policy | 将 VLM 语义理解和 flow matching 连续动作生成结合 | [arXiv](https://arxiv.org/abs/2410.24164) | [速读](model-paper-notes.md#13-pi0-a-vision-language-action-flow-model-for-general-robot-control) |
| 2024 | RDT-1B: a Diffusion Foundation Model for Bimanual Manipulation | Bimanual FM | 双臂操作 diffusion foundation model，强调统一动作空间和多机器人预训练 | [arXiv](https://arxiv.org/abs/2410.07864) |  |
| 2024 | TraceVLA: Visual Trace Prompting Enhances Spatial-Temporal Awareness for Generalist Robotic Policies | VLA extension | 用 visual trace 提升通用策略的空间时间 awareness | [arXiv](https://arxiv.org/abs/2412.10345) |  |
| 2025 | SpatialVLA: Exploring Spatial Representations for Visual-Language-Action Model | VLA extension | 从 3D 空间表示与动作网格角度增强 VLA | [arXiv](https://arxiv.org/abs/2501.15830) |  |
| 2023 | VoxPoser: Composable 3D Value Maps for Robotic Manipulation with Language Models | LLM + 3D manipulation | 用 composable 3D value map 把语言约束转成可规划的几何目标 | [arXiv](https://arxiv.org/abs/2307.05973) | [精读](paper-notes/2023-voxposer.md) |
| 2024 | FoundationPose: Unified 6D Pose Estimation and Tracking of Novel Objects | Perception | 统一 novel object 的 6D 位姿估计与跟踪 | [项目页](https://nvlabs.github.io/FoundationPose/) | [精读](paper-notes/2024-foundationpose.md) |
| 2020 | Object Goal Navigation using Goal-Oriented Semantic Exploration | Navigation | 模块化 object-goal navigation 的经典语义探索路线 | [arXiv](https://arxiv.org/abs/2007.00643) |  |
| 2025 | OmniManip: Towards General Robotic Manipulation via Object-Centric Interaction Primitives as Spatial Constraints | 3D manipulation | 用 object-centric spatial constraints 连接高层语义和低层操作执行 | [arXiv](https://arxiv.org/abs/2501.03841) |  |
| 2018 | World Models | World Model | 学习压缩世界模型并在想象环境中训练策略 | [arXiv](https://arxiv.org/abs/1803.10122) | [速读](model-paper-notes.md#14-world-models) |
| 2019 | Dream to Control: Learning Behaviors by Latent Imagination | World Model | Dreamer，用 latent imagination 训练行为策略 | [arXiv](https://arxiv.org/abs/1912.01603) | [速读](model-paper-notes.md#15-dream-to-control-learning-behaviors-by-latent-imagination) |
| 2022 | DayDreamer: World Models for Physical Robot Learning | World Model / real robot | 将 Dreamer 搬到真实机器人在线学习 | [arXiv](https://arxiv.org/abs/2206.14176) | [速读](model-paper-notes.md#16-daydreamer-world-models-for-physical-robot-learning) |
| 2023 | Learning Interactive Real-World Simulator | World Model / simulator | UniSim，从多源真实数据学习可交互生成式模拟器 | [arXiv](https://arxiv.org/abs/2310.06114) | [速读](model-paper-notes.md#17-learning-interactive-real-world-simulator) |
| 2025 | Scaling Offline Model-Based RL via Jointly-Optimized World-Action Model Pretraining | WAM / offline MBRL | JOWA，联合预训练 world-action model 做大规模离线 model-based RL | [OpenReview](https://openreview.net/forum?id=T1OvCSFaum) | [速读](model-paper-notes.md#18-scaling-offline-model-based-rl-via-jointly-optimized-world-action-model-pretraining) |
| 2026 | World Action Models are Zero-shot Policies | WAM | DreamZero，用视频扩散世界模型直接产生零样本机器人策略 | [arXiv](https://arxiv.org/abs/2602.15922) | [速读](model-paper-notes.md#19-world-action-models-are-zero-shot-policies) |
| 2026 | GigaWorld-Policy: An Efficient Action-Centered World-Action Model | WAM | 动作中心化 WAM，降低推理开销并解耦视频预测误差 | [arXiv](https://arxiv.org/abs/2603.17240) | [速读](model-paper-notes.md#20-gigaworld-policy-an-efficient-action-centered-world-action-model) |
| 2026 | World Action Models: The Next Frontier in Embodied AI | WAM survey | 系统整理 WAM 定义、分类、数据和评测挑战 | [arXiv](https://arxiv.org/abs/2605.12090) | [速读](model-paper-notes.md#21-world-action-models-the-next-frontier-in-embodied-ai) |
| 2023 | Diffusion Policy: Visuomotor Policy Learning via Action Diffusion | Diffusion Policy | 用条件去噪扩散生成连续动作轨迹 | [arXiv](https://arxiv.org/abs/2303.04137) | [精读](paper-notes/2023-diffusion-policy.md) / [路线笔记](model-paper-notes.md#22-diffusion-policy-visuomotor-policy-learning-via-action-diffusion) |
| 2024 | FlowPolicy: Enabling Fast and Robust 3D Flow-based Policy via Consistency Flow Matching for Robot Manipulation | Flow Policy | 用一致性 flow matching 加速 3D 操作策略采样 | [arXiv](https://arxiv.org/abs/2412.04987) | [速读](model-paper-notes.md#23-flowpolicy-enabling-fast-and-robust-3d-flow-based-policy-via-consistency-flow-matching-for-robot-manipulation) |
| 2025 | VFP: Variational Flow-Matching Policy for Multi-Modal Robot Manipulation | Flow Policy | 面向多模态动作分布的 variational flow matching policy | [arXiv](https://arxiv.org/abs/2508.01622) | [速读](model-paper-notes.md#24-vfp-variational-flow-matching-policy-for-multi-modal-robot-manipulation) |
| 2023 | Learning Fine-Grained Bimanual Manipulation with Low-Cost Hardware | ACT | ACT，一次预测动作块，支持低成本双臂精细操作 | [arXiv](https://arxiv.org/abs/2304.13705) | [速读](model-paper-notes.md#25-learning-fine-grained-bimanual-manipulation-with-low-cost-hardware) |
| 2024 | NaVILA: Legged Robot Vision-Language-Action Model for Navigation | Navigation VLA | 用两级 VLA+locomotion skill 把语言导航接到腿式机器人低层动作 | [arXiv](https://arxiv.org/abs/2412.04453) |  |

## 精读候选

- Open X-Embodiment / RT-X。
- OpenVLA。
- Octo。
- pi0。
- Foundation Models in Robotics survey。
- 模型谱系代表论文见 [model-paper-notes.md](model-paper-notes.md)。

## 需要复查

- 论文年份、机构和代码链接需要逐篇确认。
- 新近 VLA/WAM 论文优先从论文原文、官方项目页和官方代码仓库补充。
