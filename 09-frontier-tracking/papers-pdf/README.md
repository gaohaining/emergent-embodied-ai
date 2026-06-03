# 论文原文索引

这个目录整理机器人策略模型路线相关的 primary-source 论文原文。它不是一个无差别论文列表，而是服务于“机器人策略模型 / 具身基础模型路线”的本地阅读包。

维护原则：

- 只收录论文、技术报告、model card 这类 primary source。
- 动态版本需要记录 `last checked`。
- 论文解释和横向比较写在 [../paper-notes/robot-strategy-models-comparison.md](../paper-notes/robot-strategy-models-comparison.md)，这里主要负责原文定位。
- 不把这些论文强绑定到 Manipulation；操作任务只是许多系统最常用、最密集的验证场景。

Last checked: 2026-06-03

| 年份 | 标题 | 本地文件 | 原始来源 | 技术链接 | 为什么纳入 |
| --- | --- | --- | --- | --- | --- |
| 2020 | GraspNet-1Billion: A Large-Scale Benchmark for General Object Grasping | [PDF](2020-graspnet-1billion.pdf) | [arXiv](https://arxiv.org/abs/1912.13470) | perception / grasping / evaluation | 早期从几何抓取走向大规模抓取数据和 benchmark 的代表。 |
| 2021 | CLIPort: What and Where Pathways for Robotic Manipulation | [PDF](2021-cliport.pdf) | [arXiv](https://arxiv.org/abs/2109.12098) | VLM grounding / policy learning | 把 CLIP 语义和 Transporter 空间操作结合，是 VLM 接机器人动作的早期样本。 |
| 2021 | robomimic: What Matters in Learning from Offline Human Demonstrations for Robot Manipulation | [PDF](2021-robomimic.pdf) | [arXiv](https://arxiv.org/abs/2108.03298) | data / imitation learning | 帮助理解离线示范学习的工程变量和 benchmark 化。 |
| 2022 | Do As I Can, Not As I Say: Grounding Language in Robotic Affordances | [PDF](2022-saycan.pdf) | [arXiv](https://arxiv.org/abs/2204.01691) | planning / affordance / skill library | LLM 规划和机器人可执行性打分相乘的经典路线。 |
| 2022 | RT-1: Robotics Transformer for Real-World Control at Scale | [PDF](2022-rt-1.pdf) | [arXiv](https://arxiv.org/abs/2212.06817) | robot transformer / data scaling | 大规模真实机器人数据训练 Transformer 策略的重要节点。 |
| 2023 | ChatGPT for Robotics: Design Principles and Model Abilities | [PDF](2023-chatgpt-for-robotics.pdf) | [arXiv](https://arxiv.org/abs/2306.17582) | LLM / robotics interface | 作为 LLM 接机器人 API 的设计原则线索，而不是低层控制路线。 |
| 2023 | Learning Fine-Grained Bimanual Manipulation with Low-Cost Hardware | [PDF](2023-act-aloha.pdf) | [arXiv](https://arxiv.org/abs/2304.13705) | ACT / low-cost hardware / imitation learning | ACT 和 ALOHA，把低成本硬件、遥操作数据和动作分块连起来。 |
| 2023 | Diffusion Policy: Visuomotor Policy Learning via Action Diffusion | [PDF](2023-diffusion-policy.pdf) | [arXiv](https://arxiv.org/abs/2303.04137) | diffusion policy / action generation | 生成式动作头进入机器人策略学习主流的关键论文。 |
| 2023 | Mastering Diverse Domains through World Models | [PDF](2023-dreamerv3.pdf) | [arXiv](https://arxiv.org/abs/2301.04104) | world model / RL | DreamerV3，理解“先学世界模型，再在想象里优化策略”的基线。 |
| 2023 | Open X-Embodiment: Robotic Learning Datasets and RT-X Models | [PDF](2023-open-x-embodiment-rt-x.pdf) | [arXiv](https://arxiv.org/abs/2310.08864) | data / cross-embodiment / RT-X | 跨实验室、跨本体数据集和 RT-X 模型的关键节点。 |
| 2023 | RT-2: Vision-Language-Action Models Transfer Web Knowledge to Robotic Control | [PDF](2023-rt-2.pdf) | [arXiv](https://arxiv.org/abs/2307.15818) | VLA / action tokenization | 把动作当作 token 接入 VLM，VLA 范式的重要起点。 |
| 2023 | Learning Interactive Real-World Simulators | [PDF](2023-unisim.pdf) | [arXiv](https://arxiv.org/abs/2310.06114) | world model / simulation / data generation | UniSim，世界模型从预测未来走向交互式训练环境。 |
| 2024 | Mobile ALOHA: Learning Bimanual Mobile Manipulation with Low-Cost Whole-Body Teleoperation | [PDF](2024-mobile-aloha.pdf) | [arXiv](https://arxiv.org/abs/2401.02117) | data / mobile manipulation / teleoperation | 将 ALOHA 从桌面双臂扩展到移动操作和家务任务。 |
| 2024 | Universal Manipulation Interface: In-The-Wild Robot Teaching Without In-The-Wild Robots | [PDF](2024-umi.pdf) | [arXiv](https://arxiv.org/abs/2402.10329) | data collection / action representation | 用手持 gripper 收人类演示，再迁移到机器人策略。 |
| 2024 | 3D Diffusion Policy: Generalizable Visuomotor Policy Learning via Simple 3D Representations | [PDF](2024-dp3.pdf) | [arXiv](https://arxiv.org/abs/2403.03954) | 3D representation / diffusion policy | 把 3D 点云条件引入 diffusion policy，补强空间泛化。 |
| 2024 | ALOHA Unleashed: A Simple Recipe for Robot Dexterity | [PDF](2024-aloha-unleashed.pdf) | [项目页](https://aloha-unleashed.github.io/) | data scaling / diffusion policy / dexterity | 大规模 ALOHA 2 数据 + diffusion policy 推进复杂双臂任务。 |
| 2024 | Octo: An Open-Source Generalist Robot Policy | [PDF](2024-octo.pdf) | [arXiv](https://arxiv.org/abs/2405.12213) | generalist policy / open source | 开源通用策略初始化器，重点是多数据、多平台和可微调。 |
| 2024 | OpenVLA: An Open-Source Vision-Language-Action Model | [PDF](2024-openvla.pdf) | [arXiv](https://arxiv.org/abs/2406.09246) | VLA / open source | 开源 7B VLA，适合作为可复现 VLA 基线。 |
| 2024 | Scaling Proprioceptive-Visual Learning with Heterogeneous Pre-trained Transformers | [PDF](2024-hpt.pdf) | [arXiv](https://arxiv.org/abs/2409.20537) | cross-embodiment / representation pretraining | HPT，从异构机器人数据中预训练共享策略表征。 |
| 2024 | RDT-1B: A Diffusion Foundation Model for Bimanual Manipulation | [PDF](2024-rdt-1b.pdf) | [arXiv](https://arxiv.org/abs/2410.07864) | diffusion foundation model / bimanual policy | 大参数 diffusion transformer 策略，代表 diffusion foundation policy 路线。 |
| 2024 | pi0: A Vision-Language-Action Flow Model for General Robot Control | [PDF](2024-pi0.pdf) | [arXiv](https://arxiv.org/abs/2410.24164) | VLA / flow matching / general control | 把 VLM 语义理解和 flow matching 连续动作生成结合。 |
| 2025 | FAST: Efficient Action Tokenization for Vision-Language-Action Models | [PDF](2025-fast-action-tokenization.pdf) | [arXiv](https://arxiv.org/abs/2501.09747) | action tokenization / VLA | 用频域压缩解决高频动作 token 化低效问题，支撑 pi0-FAST。 |
| 2025 | Cosmos World Foundation Model Platform for Physical AI | [PDF](2025-cosmos.pdf) | [arXiv](https://arxiv.org/abs/2501.03575) | world foundation model / synthetic data | NVIDIA 世界基础模型平台，作为 Physical AI 数据和仿真基础设施线索。 |
| 2025 | GR00T N1: An Open Foundation Model for Generalist Humanoid Robots | [PDF](2025-gr00t-n1.pdf) | [arXiv](https://arxiv.org/abs/2503.14734) | humanoid VLA / sim2real / platform | NVIDIA 开放 humanoid foundation model，连接 VLA、仿真和部署栈。 |
| 2025 | pi0.5: a Vision-Language-Action Model with Open-World Generalization | [PDF](2025-pi05.pdf) | [arXiv](https://arxiv.org/abs/2504.16054) | VLA / open-world generalization | pi0 后续版本，强调异构训练和开放世界泛化。 |
| 2025 | SmolVLA: A Vision-Language-Action Model for Affordable and Efficient Robotics | [PDF](2025-smolvla.pdf) | [arXiv](https://arxiv.org/abs/2506.01844) | lightweight VLA / LeRobot | 450M 级开源 VLA，代表低门槛和消费级硬件方向。 |
| 2025 | GigaBrain-0: A World Model-Powered Vision-Language-Action Model | [PDF](2025-gigabrain-0.pdf) | [arXiv](https://arxiv.org/abs/2510.19430) | VLA / world-model-generated data | 用世界模型生成数据增强 VLA 的前沿路线，证据需持续复查。 |
| 2025 | pi0.6 Model Card | [PDF](2025-pi06-model-card.pdf) | [model card](https://website.pi-asset.com/pi06star/PI06_model_card.pdf) | model card / VLA | 记录 pi0.6 架构、数据和推理速度等版本信息。 |
| 2025 | pi*0.6: a VLA That Learns From Experience | [PDF](2025-pistar06-recap.pdf) | [arXiv](https://arxiv.org/abs/2511.14759) | VLA + RL / RECAP | 用 offline RL、人在回路和自主经验提升 VLA 的代表。 |
| 2026 | GigaBrain-0.5M*: a VLA That Learns From World Model-Based Reinforcement Learning | [PDF](2026-gigabrain-05m-ramp.pdf) | [arXiv](https://arxiv.org/abs/2602.12099) | VLA + world model + RL | 世界模型条件强化学习路线，属于高动态前沿。 |
| 2026 | LeRobot: An Open-Source Library for End-to-End Robot Learning | [PDF](2026-lerobot.pdf) | [arXiv](https://arxiv.org/abs/2602.22818) | tooling / data / deployment | 开源端到端机器人学习工具链，连接学习路线和实践路线。 |
