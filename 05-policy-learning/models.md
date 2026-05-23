# 模型

## 关注方向

- 视觉语言模型（Vision-Language Model, VLM）作为语义理解和视觉表征基座。
- 视觉语言动作模型（Vision-Language-Action Model, VLA）。
- 视觉动作模型（Vision-Action Model, VAM）和纯视觉伺服策略。
- Diffusion policy 和轨迹生成模型。
- Flow policy 和连续动作生成模型。
- 世界动作模型（World-Action Model, WAM）等把世界预测和动作生成耦合起来的新路线。
- Transformer-based robot policy。
- 层级策略和技能组合。
- 世界模型辅助规划。
- Foundation model 与机器人控制器的接口。

## 模型谱系速查

| 缩写 | 全称 | 主要输入 | 主要输出 | 在系统里解决什么 |
| --- | --- | --- | --- | --- |
| LLM | Large Language Model | 文本、工具上下文 | 文本、计划、代码、工具调用 | 高层任务理解、任务分解、知识推理 |
| VLM | Vision-Language Model | 图像或视频 + 文本 | 文本、标签、区域、语义判断 | 看懂场景和指令，但通常不直接输出可执行动作 |
| VLA | Vision-Language-Action Model | 视觉、语言、机器人状态 | 动作、动作序列、动作 token | 把“看见什么、要做什么”连接到机器人动作 |
| VAM | Vision-Action Model | 视觉、机器人状态 | 动作或轨迹 | 不依赖语言，适合固定任务或视觉伺服式控制 |
| World Model | World Model | 状态、动作、历史观察 | 未来状态、未来图像、latent 预测 | 预测“如果这样做会发生什么”，服务规划、训练和异常检测 |
| WAM | World-Action Model | 视频、世界状态、动作条件或任务条件 | 动作、未来状态、可行动作预测 | 尝试把世界动态理解和动作生成合并，处在世界模型与策略模型之间 |
| Diffusion Policy | Diffusion Policy | 观察、状态、任务条件 | 一段连续动作轨迹 | 用扩散生成过程生成平滑动作序列 |
| Flow Policy | Flow Matching Policy | 观察、状态、任务条件 | 一段连续动作轨迹 | 用 flow matching 生成动作，常被讨论为更快的动作生成头 |
| ACT | Action Chunking Transformer | 观察、状态、任务条件 | 动作块 | 一次预测多个时间步，降低逐步控制的不稳定性 |

## 代表论文

这些论文不是完整书单，而是给每类模型一个“先读入口”。读的时候重点看三件事：输入输出接口、训练数据来源、它在机器人系统 loop 里替代或增强了哪个模块。

| 模型 | 先读论文 | 为什么读 |
| --- | --- | --- |
| LLM | [Do As I Can, Not As I Say: Grounding Language in Robotic Affordances](https://arxiv.org/abs/2204.01691) | SayCan 代表“LLM 做高层语义选择 + affordance/value function 约束可执行性”的早期路线。 |
| LLM | [Inner Monologue: Embodied Reasoning through Planning with Language Models](https://arxiv.org/abs/2207.05608) | 展示如何把环境反馈、任务状态和语言推理接入机器人规划循环。 |
| LLM | [Code as Policies: Language Model Programs for Embodied Control](https://arxiv.org/abs/2209.07753) | 代表“LLM 生成可执行策略代码/工具调用”的路线，适合理解 LLM 和控制 API 的接口。 |
| VLM | [Learning Transferable Visual Models From Natural Language Supervision](https://arxiv.org/abs/2103.00020) | CLIP 是视觉-语言对齐的基础入口，很多机器人视觉表征和开放词汇能力受它影响。 |
| VLM | [Flamingo: a Visual Language Model for Few-Shot Learning](https://arxiv.org/abs/2204.14198) | 代表少样本、多图文交错输入的 VLM 方向，帮助理解后续具身多模态模型的上下文学习能力。 |
| VLM | [PaLM-E: An Embodied Multimodal Language Model](https://arxiv.org/abs/2303.03378) | 把视觉、语言和机器人状态接入同一多模态语言模型，是 VLM 走向具身系统的重要桥梁。 |
| VAM | [RT-1: Robotics Transformer for Real-World Control at Scale](https://arxiv.org/abs/2212.06817) | 代表大规模真实机器人数据训练的视觉/任务条件策略，说明机器人动作 token 化和实时控制接口。 |
| VAM | [BC-Z: Zero-Shot Task Generalization with Robotic Imitation Learning](https://arxiv.org/abs/2202.02005) | 早期展示多任务模仿学习如何借助语言或人类视频条件实现未见任务泛化。 |
| VAM | [R3M: A Universal Visual Representation for Robot Manipulation](https://arxiv.org/abs/2203.12601) | 虽然不是直接动作模型，但它是“人类视频预训练视觉表征用于下游控制”的关键参考。 |
| VLA | [RT-2: Vision-Language-Action Models Transfer Web Knowledge to Robotic Control](https://arxiv.org/abs/2307.15818) | 明确把互联网 VLM 知识迁移到低层机器人动作，是 VLA 范式的关键起点。 |
| VLA | [OpenVLA: An Open-Source Vision-Language-Action Model](https://arxiv.org/abs/2406.09246) | 开源 VLA 代表作，适合研究训练数据、视觉编码器、动作解码和高效微调。 |
| VLA | [Octo: An Open-Source Generalist Robot Policy](https://arxiv.org/abs/2405.12213) | 通用机器人策略入口，关注跨数据集、跨传感器和跨动作空间的策略预训练。 |
| VLA | [pi0: A Vision-Language-Action Flow Model for General Robot Control](https://arxiv.org/abs/2410.24164) | 把 VLA 和 flow-based 动作生成结合，适合理解高频连续控制路线。 |
| World Model | [World Models](https://arxiv.org/abs/1803.10122) | 世界模型经典起点：学习压缩的时空表征，并在“想象环境”中训练策略。 |
| World Model | [Dream to Control: Learning Behaviors by Latent Imagination](https://arxiv.org/abs/1912.01603) | Dreamer 代表 latent imagination 路线，说明如何用学习到的动态模型优化行为。 |
| World Model | [DayDreamer: World Models for Physical Robot Learning](https://arxiv.org/abs/2206.14176) | 把 Dreamer 搬到真实机器人，适合理解世界模型在真机在线学习中的潜力和限制。 |
| World Model | [Learning Interactive Real-World Simulators](https://deepmind.google/research/publications/47545/) | UniSim 代表把多源数据学习成可交互真实世界模拟器的路线。 |
| WAM | [Scaling Offline Model-Based RL via Jointly-Optimized World-Action Model Pretraining](https://openreview.net/forum?id=T1OvCSFaum) | JOWA 是较早把 world model 和 action model 联合预训练的代表，主要在离线 model-based RL 语境。 |
| WAM | [World Action Models are Zero-shot Policies](https://arxiv.org/abs/2602.15922) | DreamZero 代表“视频扩散世界模型 + 动作生成”成为零样本机器人策略的路线。 |
| WAM | [GigaWorld-Policy: An Efficient Action-Centered World-Action Model](https://arxiv.org/abs/2603.17240) | 关注 WAM 的部署瓶颈：把动作预测和视频生成解耦，降低推理开销。 |
| WAM | [World Action Models: The Next Frontier in Embodied AI](https://arxiv.org/abs/2605.12090) | 2026 年的 WAM 综述入口，用于理解概念边界、分类和开放问题。 |
| Diffusion Policy | [Diffusion Policy: Visuomotor Policy Learning via Action Diffusion](https://arxiv.org/abs/2303.04137) | 扩散策略经典入口，解释为什么动作生成可以建模为条件去噪过程。 |
| Flow Policy | [FlowPolicy: Enabling Fast and Robust 3D Flow-based Policy via Consistency Flow Matching for Robot Manipulation](https://arxiv.org/abs/2412.04987) | 代表用 consistency flow matching 提高动作采样速度的 3D 操作策略。 |
| Flow Policy | [VFP: Variational Flow-Matching Policy for Multi-Modal Robot Manipulation](https://arxiv.org/abs/2508.01622) | 关注 flow policy 在多模态动作分布下的模式坍塌问题。 |
| ACT | [Learning Fine-Grained Bimanual Manipulation with Low-Cost Hardware](https://arxiv.org/abs/2304.13705) | ACT 原始入口，说明为什么一次预测动作块能缓解高精度双臂操作中的误差累积。 |

## 记录字段

- 输入：语言、图像、视频、深度、点云、本体状态。
- 输出：离散动作、连续控制、轨迹、子目标、代码或技能调用。
- 训练：监督、模仿、强化、离线强化、自监督、多阶段训练。
- 泛化：跨任务、跨场景、跨物体、跨机器人本体。
- 约束：延迟、算力、安全、可解释性。

## 开放问题

- VLA 会走向统一模型，还是保持高层模型加低层策略的组合？
- WAM 会成为独立路线，还是被 VLA + world model 或 video foundation model 吸收？
- 动作表示的标准化会不会成为数据规模化的关键？
- 机器人策略的 scaling law 应该如何定义？
