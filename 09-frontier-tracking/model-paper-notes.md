# 模型谱系代表论文笔记

按 [../05-policy-learning/models.md](../05-policy-learning/models.md) 的代表论文顺序整理。定位：不是完整论文库，而是帮助读者把 LLM、VLM、VAM、VLA、World Model、WAM、Diffusion Policy、Flow Policy、ACT 放回具身智能系统 loop 中。

字段说明：
- **技术链接**：论文主要影响哪个目录。
- **证据**：论文验证方式，区分互联网 benchmark、仿真、真实机器人、离线 RL、综述等。
- **记住一句话**：读完后最应该带走的判断。
- **局限或追问**：后续精读、复现或迁移到稳定主题页时要检查的问题。

---

## 1. Do As I Can, Not As I Say: Grounding Language in Robotic Affordances

- 模型类别：LLM + 技能库 / affordance grounding
- 年份：2022
- 链接：[arXiv](https://arxiv.org/abs/2204.01691), [项目页](https://say-can.github.io/)
- 技术链接：06-planning-and-control / 05-policy-learning
- 解决什么问题：大语言模型知道“任务应该怎么做”，但不知道当前机器人在当前环境里“能不能做”。
- 方法：用 LLM 给候选自然语言技能打语义分数，用技能 value function 或 affordance score 约束可执行性，再选择下一步技能。
- 证据：真实移动操作机器人上的长程自然语言任务；后续版本加入 PaLM、抽屉操作、多语言和链式思考等实验。
- 记住一句话：SayCan 的关键不是让 LLM 直接控制机器人，而是把“语言合理性”和“物理可执行性”相乘。
- 局限或追问：依赖预定义技能库；低层技能覆盖不到的动作无法凭语言泛化出来；失败恢复仍主要靠外部反馈。

## 2. Inner Monologue: Embodied Reasoning through Planning with Language Models

- 模型类别：LLM + 闭环语言反馈
- 年份：2022
- 链接：[arXiv](https://arxiv.org/abs/2207.05608), [项目页](https://innermonologue.github.io/)
- 技术链接：06-planning-and-control / 06-planning-and-control/failure-recovery.md
- 解决什么问题：高层语言规划如果只开环生成动作序列，机器人执行中环境变化、技能失败和人类反馈都无法进入推理。
- 方法：把成功检测、场景描述、人类交互等反馈转成语言上下文，让 LLM 在任务过程中持续更新计划。
- 证据：仿真和真实桌面整理任务、真实厨房移动操作长程任务。
- 记住一句话：机器人里的 LLM 更像“持续读状态的任务协调器”，而不是一次性写完计划的脚本生成器。
- 局限或追问：反馈质量决定推理质量；语言化反馈会丢失低层连续状态；对实时控制帮助有限。

## 3. Code as Policies: Language Model Programs for Embodied Control

- 模型类别：LLM 生成策略代码
- 年份：2022
- 链接：[arXiv](https://arxiv.org/abs/2209.07753), [项目页](https://code-as-policies.github.io/)
- 技术链接：06-planning-and-control / 08-hardware-and-deployment
- 解决什么问题：自然语言计划很难直接连接几何计算、控制 API 和第三方库。
- 方法：用 few-shot prompt 让代码 LLM 生成 Python 策略程序，程序调用感知输出、几何库和控制 primitive；递归生成缺失函数。
- 证据：多个真实机器人平台上的 pick-and-place、轨迹控制和反应式策略；同时报告 HumanEval 代码生成表现。
- 记住一句话：Code as Policies 把 LLM 的输出从“文字计划”推进到“可执行控制胶水层”。
- 局限或追问：安全边界、运行时检查和 API 约束非常关键；生成代码不等于学到了物理控制。

## 4. Learning Transferable Visual Models From Natural Language Supervision

- 模型类别：VLM / CLIP
- 年份：2021
- 链接：[arXiv](https://arxiv.org/abs/2103.00020), [Code](https://github.com/openai/CLIP)
- 技术链接：02-perception / 03-representation
- 解决什么问题：传统视觉模型绑定固定类别，难以用自然语言指定开放概念。
- 方法：用 4 亿图文对训练图像和文本的对比表征，推理时用文本描述作为类别或概念查询。
- 证据：30 多个视觉 benchmark 的零样本迁移，包括 OCR、动作识别、地理定位和细粒度分类。
- 记住一句话：CLIP 是开放词汇视觉能力的地基，但它只给语义表征，不给动作能力。
- 局限或追问：互联网图文偏静态语义，缺少接触、力、连续动作和机器人视角。

## 5. Flamingo: a Visual Language Model for Few-Shot Learning

- 模型类别：VLM / few-shot multimodal model
- 年份：2022
- 链接：[arXiv](https://arxiv.org/abs/2204.14198)
- 技术链接：02-perception / 05-policy-learning
- 解决什么问题：多模态模型需要用少量图文示例快速适应新任务，而不是每个任务都重新微调。
- 方法：桥接预训练视觉模型和语言模型，支持任意交错的图像、视频和文本输入。
- 证据：视觉问答、caption、多选视觉问答等多类图像和视频任务 few-shot 评测。
- 记住一句话：Flamingo 说明 VLM 可以具备多图文上下文学习能力，这是后续 VLA 继承“互联网知识”的重要前提。
- 局限或追问：仍主要输出语言，不直接处理机器人动作、延迟或安全约束。

## 6. PaLM-E: An Embodied Multimodal Language Model

- 模型类别：VLM / embodied multimodal LLM
- 年份：2023
- 链接：[arXiv](https://arxiv.org/abs/2303.03378)
- 技术链接：02-perception / 06-planning-and-control
- 解决什么问题：如何把真实世界传感器和机器人状态直接接入大语言模型，让模型做具身推理。
- 方法：把视觉、连续状态估计和文本编码成交错多模态句子，与预训练 LLM 端到端联合训练。
- 证据：机器人序列操作规划、视觉问答、caption；最大 PaLM-E-562B 同时保留强语言能力和视觉语言泛化。
- 记住一句话：PaLM-E 是 VLM 向具身系统过渡的桥：它能理解和规划，但还不是低层动作策略。
- 局限或追问：动作执行依赖外部策略或技能；模型规模巨大，实时部署和开源复现门槛高。

## 7. RT-1: Robotics Transformer for Real-World Control at Scale

- 模型类别：VAM / Robotics Transformer
- 年份：2022
- 链接：[arXiv](https://arxiv.org/abs/2212.06817), [项目页](https://robotics-transformer1.github.io/)
- 技术链接：05-policy-learning / 04-data
- 解决什么问题：机器人策略能否像视觉和语言模型一样，从大规模多任务真实数据中获得泛化。
- 方法：用高容量 Transformer 吸收真实机器人多任务数据，把视觉和任务条件映射到离散动作 token。
- 证据：Google 真实机器人数据上的模型大小、数据规模、数据多样性消融。
- 记住一句话：RT-1 把“大规模真实机器人数据 + Transformer 策略”变成可讨论的系统路线。
- 局限或追问：仍强依赖同类机器人和数据分布；开放词汇语义和互联网知识还不如 RT-2/VLA。

## 8. BC-Z: Zero-Shot Task Generalization with Robotic Imitation Learning

- 模型类别：VAM / task-conditioned imitation learning
- 年份：2021 / arXiv 2022
- 链接：[arXiv](https://arxiv.org/abs/2202.02005)
- 技术链接：05-policy-learning / 04-data
- 解决什么问题：模仿学习如何在没有目标任务机器人示范的情况下执行新任务。
- 方法：构建可交互模仿学习系统，从示范和 interventions 学习；任务条件可来自语言 embedding 或人类任务视频。
- 证据：真实机器人上超过 100 个训练任务，24 个未见操作任务平均成功率 44%。
- 记住一句话：BC-Z 是“多任务真实数据 + 任务条件”的早期零样本泛化样本。
- 局限或追问：成功率离可靠部署还有距离；语言和视频条件更多是任务指定，不是完整世界理解。

## 9. R3M: A Universal Visual Representation for Robot Manipulation

- 模型类别：VAM 相关视觉表征 / human video pretraining
- 年份：2022
- 链接：[arXiv](https://arxiv.org/abs/2203.12601), [Code/Model](https://tinyurl.com/robot-r3m)
- 技术链接：02-perception / 03-representation / 05-policy-learning
- 解决什么问题：能否用大量人类视频预训练视觉表征，减少下游机器人示范需求。
- 方法：在 Ego4D 人类视频上结合时间对比学习、视频语言对齐和稀疏紧凑正则，得到冻结视觉模块。
- 证据：12 个仿真操作任务；真实 Franka Panda 在杂乱公寓中用 20 条示范学习多种操作。
- 记住一句话：R3M 说明人类视频能提供有用视觉先验，但它本身不是完整策略。
- 局限或追问：从人类视频到机器人动作仍有 embodiment gap；触觉和低层动作因果缺失。

## 10. RT-2: Vision-Language-Action Models Transfer Web Knowledge to Robotic Control

- 模型类别：VLA
- 年份：2023
- 链接：[arXiv](https://arxiv.org/abs/2307.15818), [项目页](https://robotics-transformer.github.io/)
- 技术链接：05-policy-learning / 03-representation
- 解决什么问题：如何让互联网规模 VLM 的语义知识直接改善机器人控制泛化。
- 方法：把机器人动作表示成文本 token，与视觉问答等互联网视觉语言任务共同微调 VLM。
- 证据：约 6000 次机器人评测；新物体、未见命令、符号/数字指令和简单语义推理显著改善。
- 记住一句话：RT-2 正式把“动作作为语言 token”推到 VLA 范式中心。
- 局限或追问：动作 token 化方便复用 VLM，但连续控制精度、延迟和跨本体泛化仍受限制。

## 11. OpenVLA: An Open-Source Vision-Language-Action Model

- 模型类别：VLA / open-source VLA
- 年份：2024
- 链接：[arXiv](https://arxiv.org/abs/2406.09246), [项目页](https://openvla.github.io/)
- 技术链接：05-policy-learning / 09-frontier-tracking/open-source.md
- 解决什么问题：VLA 如果大多闭源，研究者难以复现、微调和比较。
- 方法：7B 参数模型，Llama 2 语言模型 + DINOv2/SigLIP 视觉特征，在 970k 真实机器人示范上训练。
- 证据：29 个任务、多机器人本体；报告相对 RT-2-X 更少参数下的更高任务成功率；支持 LoRA 和量化部署。
- 记住一句话：OpenVLA 的价值不仅是模型效果，而是把 VLA 训练、微调、部署开放成研究基线。
- 局限或追问：开放模型与闭源前沿系统仍可能有零样本鲁棒性差距；真实部署需要独立复现。

## 12. Octo: An Open-Source Generalist Robot Policy

- 模型类别：generalist robot policy / VLA 邻近
- 年份：2024
- 链接：[arXiv](https://arxiv.org/abs/2405.12213), [项目页](https://octo-models.github.io/)
- 技术链接：05-policy-learning / 04-data / 10-case-studies
- 解决什么问题：通用机器人策略需要适配不同传感器、动作空间、机器人平台和任务条件。
- 方法：在 Open X-Embodiment 的 800k 轨迹上训练大 Transformer，可用语言或目标图像指令，并可在新平台上微调。
- 证据：9 个机器人平台；对架构、训练数据和微调设计做系统消融。
- 记住一句话：Octo 更像“通用策略初始化器”，而不是单一封闭任务模型。
- 局限或追问：跨平台微调仍需要本体适配数据；离真正免微调泛化还有距离。

## 13. pi0: A Vision-Language-Action Flow Model for General Robot Control

- 模型类别：VLA + Flow Policy
- 年份：2024 / RSS 2025
- 链接：[arXiv](https://arxiv.org/abs/2410.24164), [项目页](https://www.physicalintelligence.company/blog/pi0)
- 技术链接：05-policy-learning / 10-case-studies
- 解决什么问题：通用机器人策略需要同时继承 VLM 语义知识，又能生成高频连续灵巧动作。
- 方法：在预训练 VLM 之上构建 flow matching 动作生成架构，使用多平台灵巧操作数据训练。
- 证据：单臂、双臂、移动操作等多种平台；洗衣折叠、清桌、组装盒子等多任务；评估预训练零样本、语言跟随和新技能微调。
- 记住一句话：pi0 把 VLA 的语义理解和 flow-based 连续动作头连到一起，是当前通用控制路线的重要样本。
- 局限或追问：数据和训练细节开放度有限；泛化边界、失败检测和安全接管仍需第三方实测。

## 14. World Models

- 模型类别：World Model
- 年份：2018
- 链接：[arXiv](https://arxiv.org/abs/1803.10122), [Interactive Paper](https://worldmodels.github.io/)
- 技术链接：03-representation/world-models.md
- 解决什么问题：智能体能否先学习环境的压缩时空模型，再在“想象”里训练策略。
- 方法：无监督学习环境的视觉和时序表示，用世界模型特征训练紧凑控制器，甚至在模型生成的梦境中训练。
- 证据：经典强化学习环境中的生成世界模型和策略迁移。
- 记住一句话：世界模型的核心承诺是把经验压缩成可用于规划和训练的内部模拟器。
- 局限或追问：早期实验环境相对简单；真实机器人中的接触、遮挡和长程误差累积更难。

## 15. Dream to Control: Learning Behaviors by Latent Imagination

- 模型类别：World Model / Dreamer
- 年份：2019
- 链接：[arXiv](https://arxiv.org/abs/1912.01603)
- 技术链接：03-representation / 05-policy-learning
- 解决什么问题：如何从图像输入中学世界模型，并用 latent imagination 高效优化行为。
- 方法：学习紧凑 latent dynamics，在想象轨迹中通过价值梯度训练策略。
- 证据：20 个视觉控制任务，数据效率、计算时间和最终性能优于多种基线。
- 记住一句话：Dreamer 让“在 latent 世界里做策略学习”成为强基线。
- 局限或追问：从 benchmark 到真实机器人仍有 sim/real、奖励和稳定性挑战。

## 16. DayDreamer: World Models for Physical Robot Learning

- 模型类别：World Model / real robot online RL
- 年份：2022
- 链接：[arXiv](https://arxiv.org/abs/2206.14176)
- 技术链接：03-representation / 07-simulation-and-evaluation
- 解决什么问题：Dreamer 这类世界模型方法能否直接在真实机器人上在线学习，而不是只靠仿真。
- 方法：把 Dreamer 应用于 4 类真实机器人，从图像和稀疏奖励中在线学习。
- 证据：四足机器人 1 小时内从翻身、站起到行走；扰动后 10 分钟内适应；机械臂 pick-and-place、轮式机器人视觉导航。
- 记住一句话：DayDreamer 是世界模型从游戏/仿真走向真机在线学习的重要证据。
- 局限或追问：任务仍较基础；真实部署中的安全边界、探索成本和 reset 机制需要系统工程。

## 17. Learning Interactive Real-World Simulator

- 模型类别：World Model / interactive simulator / UniSim
- 年份：2023 / ICLR 2024
- 链接：[Google DeepMind](https://deepmind.google/research/publications/47545/), [arXiv](https://arxiv.org/abs/2310.06114)
- 技术链接：07-simulation-and-evaluation / 04-data
- 解决什么问题：能否从多源真实数据学习一个可交互的真实世界模拟器，用于训练具身智能体。
- 方法：整合图像、机器人、导航等互补数据，让生成模型根据高层指令或低层控制模拟未来视觉结果。
- 证据：用 UniSim 生成交互经验训练高层视觉语言 planner 和低层 RL policy，并展示真实迁移。
- 记住一句话：UniSim 把世界模型从“预测未来”推进到“可作为训练环境的生成式模拟器”。
- 局限或追问：生成视觉真实不等于物理精确；接触丰富操作和闭环控制误差仍需谨慎评估。

## 18. Scaling Offline Model-Based RL via Jointly-Optimized World-Action Model Pretraining

- 模型类别：WAM / offline model-based RL
- 年份：2025
- 链接：[OpenReview](https://openreview.net/forum?id=T1OvCSFaum)
- 技术链接：03-representation / 05-policy-learning
- 解决什么问题：离线 RL 如何利用大规模异构数据学习可迁移的世界和动作能力。
- 方法：JOWA 用共享 Transformer backbone 联合优化 world-action model，在多 Atari 游戏、60 亿 token 数据上预训练，并配合并行规划算法修正 Q 估计误差。
- 证据：预训练游戏上 10% 离线数据达到 78.9% human-level performance；相对大规模离线 RL baseline 平均提升 31.6%；新游戏仅约 5k 离线微调数据可迁移。
- 记住一句话：JOWA 的 WAM 还不是机器人 VLA 语境，但它把“世界预测 + 动作决策联合预训练”做成可扩展 RL 证据。
- 局限或追问：Atari 与真实机器人物理差距大；动作空间、观测噪声和安全探索问题尚未覆盖。

## 19. World Action Models are Zero-shot Policies

- 模型类别：WAM / DreamZero
- 年份：2026
- 链接：[arXiv](https://arxiv.org/abs/2602.15922), [项目页](https://dreamzero0.github.io/)
- 技术链接：05-policy-learning / 03-representation
- 解决什么问题：VLA 擅长语义泛化，但对新环境中的未见物理运动泛化不足。
- 方法：基于预训练视频扩散 backbone 构建 WAM，联合建模未来视频状态和动作，用视频作为世界演化的密集表征。
- 证据：真实机器人实验中相对 SOTA VLA 在新任务/新环境泛化上超过 2 倍；14B 自回归视频扩散模型通过优化达到 7Hz 闭环控制；人类或其他机器人视频示范带来跨本体提升。
- 记住一句话：DreamZero 把 WAM 明确推成“视频世界模型也能直接成为策略”的路线。
- 局限或追问：7Hz 对很多操作任务仍偏慢；视频生成质量和动作准确性如何解耦，是工程核心。

## 20. GigaWorld-Policy: An Efficient Action-Centered World-Action Model

- 模型类别：WAM / action-centered WAM
- 年份：2026
- 链接：[arXiv](https://arxiv.org/abs/2603.17240)
- 技术链接：05-policy-learning / 08-hardware-and-deployment
- 解决什么问题：WAM 同时生成未来视频和动作时，推理开销大，且动作质量容易受视频预测误差影响。
- 方法：动作中心化设计：预测未来动作序列，同时可选生成未来视频；因果结构阻止未来视频 token 反向影响动作 token。
- 证据：真实机器人平台上比 Motus 快 9 倍，任务成功率提升 7%；RoboTwin 2.0 上相对 pi0.5 提升 95%。
- 记住一句话：GigaWorld-Policy 的重点是把 WAM 从“会想象”推向“部署时能快出动作”。
- 局限或追问：需要核实数据集构成和任务分布；与 VLA/flow policy 的公平延迟对比仍需看细节。

## 21. World Action Models: The Next Frontier in Embodied AI

- 模型类别：WAM survey
- 年份：2026
- 链接：[arXiv](https://arxiv.org/abs/2605.12090)
- 技术链接：03-representation / 05-policy-learning / 09-frontier-tracking
- 解决什么问题：WAM 相关工作分散在 VLA、世界模型、视频生成和策略学习中，需要统一概念框架。
- 方法：将 WAM 定义为统一预测状态建模和动作生成、面向未来状态与动作联合分布的具身基础模型；区分 cascaded WAM 和 joint WAM。
- 证据：综述论文，系统整理数据生态、模型分类、评测协议和开放挑战。
- 记住一句话：这篇是当前维护 WAM 术语边界的入口，但不是实证性能论文。
- 局限或追问：概念仍在快速漂移；分类是否被 2026 下半年新模型改写需要持续复查。

## 22. Diffusion Policy: Visuomotor Policy Learning via Action Diffusion

- 模型类别：Diffusion Policy
- 年份：2023 / journal version 2024
- 链接：[arXiv](https://arxiv.org/abs/2303.04137), [项目页](https://diffusion-policy.cs.columbia.edu/)
- 技术链接：05-policy-learning / 03-representation/action-representation.md
- 解决什么问题：机器人动作分布常是多模态、高维且连续的，传统回归策略容易平均化或不稳定。
- 方法：把视觉运动策略表示为条件去噪扩散过程，结合 receding horizon control、视觉条件和 time-series diffusion transformer。
- 证据：4 个机器人操作 benchmark、12 个任务，平均比已有 SOTA robot learning 方法提升 46.9%；开源代码、数据和训练细节。
- 记住一句话：Diffusion Policy 让“生成一段动作轨迹”成为机器人策略学习的主流动作头。
- 局限或追问：迭代采样带来延迟；高频控制、失败恢复和安全约束需要额外系统设计。

## 23. FlowPolicy: Enabling Fast and Robust 3D Flow-based Policy via Consistency Flow Matching for Robot Manipulation

- 模型类别：Flow Policy
- 年份：2024
- 链接：[arXiv](https://arxiv.org/abs/2412.04987)
- 技术链接：05-policy-learning / 02-perception/depth-and-point-cloud.md
- 解决什么问题：扩散/flow 类策略从噪声到动作的递归采样效率低，速度和质量之间有冲突。
- 方法：基于一致性 flow matching 和 3D 点云条件，将不同时间状态到同一动作空间的流场约束为自一致，支持单步策略生成。
- 证据：Adroit 和 Metaworld 评测，报告 7 倍推理速度提升并保持有竞争力的成功率。
- 记住一句话：FlowPolicy 的看点是“更快的生成式动作头 + 3D 视觉条件”。
- 局限或追问：主要是 benchmark 证据；真实机器人接触丰富任务和长程任务仍需验证。

## 24. VFP: Variational Flow-Matching Policy for Multi-Modal Robot Manipulation

- 模型类别：Flow Policy / multi-modal action distribution
- 年份：2025
- 链接：[arXiv](https://arxiv.org/abs/2508.01622)
- 技术链接：05-policy-learning / 03-representation/action-representation.md
- 解决什么问题：标准 flow matching 在复杂操作的多模态动作分布上容易坍塌到平均或模糊行为。
- 方法：引入 variational latent prior 做 mode-aware 动作生成，用 Kantorovich OT 做分布对齐，并用 MoE decoder 做模式专门化。
- 证据：41 个仿真任务和 3 个真实机器人任务；仿真中相对标准 flow baseline 成功率提升 49%。
- 记住一句话：VFP 说明 Flow Policy 的下一步不是只追求快，还要解决多模态动作选择。
- 局限或追问：真实任务数量有限；和 diffusion policy 在同等延迟预算下的对比需要进一步看。

## 25. Learning Fine-Grained Bimanual Manipulation with Low-Cost Hardware

- 模型类别：ACT / Action Chunking Transformer
- 年份：2023
- 链接：[arXiv](https://arxiv.org/abs/2304.13705), [项目页](https://tonyzhaozh.github.io/aloha/)
- 技术链接：05-policy-learning / 08-hardware-and-deployment/dexterous-hands.md
- 解决什么问题：低成本、非高精度硬件如何通过学习完成细粒度双臂操作。
- 方法：用自制遥操作接口采集真实示范，ACT 一次生成动作序列块，缓解逐步误差累积和示范非平稳性。
- 证据：6 个真实精细双臂任务，包括打开透明调料杯、插入电池等；约 10 分钟示范下达到 80-90% 成功率。
- 记住一句话：ACT 的重要性在于简单、好用、数据需求低，是很多后续低成本机器人学习系统的基本组件。
- 局限或追问：任务仍是相对短程和受控场景；跨物体、跨环境、失败恢复还要靠更多数据和系统设计。

---

## 横向判断

| 观察 | 判断 |
| --- | --- |
| LLM 路线 | 更适合作高层规划、工具调用和任务约束，不应直接承担连续控制。 |
| VLM 路线 | 提供开放词汇视觉和语义表征，是 VLA 的上游基座，但物理交互能力不足。 |
| VAM / early robot transformer | 证明真实机器人数据规模化有效，但开放语义和跨本体能力有限。 |
| VLA 路线 | 当前最清晰的通用策略主线：把视觉、语言、状态和动作统一，但仍受动作表示、延迟、数据和安全约束。 |
| World Model 路线 | 长期价值在于预测动作后果、支持低成本训练和异常检测；短板是物理准确性和长程误差。 |
| WAM 路线 | 2026 年开始快速成形，试图把世界预测和动作生成合并；最大工程问题是推理效率和动作质量解耦。 |
| Diffusion / Flow / ACT | 它们更像动作生成头或策略实现方式，可以嵌入 VLA/VAM/WAM，而不是与这些路线完全并列。 |

## 后续处理建议

1. 把 VLA 论文（RT-2、OpenVLA、Octo、pi0）迁移一部分稳定结论到 [../05-policy-learning/vision-language-action.md](../05-policy-learning/vision-language-action.md)。
2. 单独创建 WAM 主题页，解释 WAM、World Model、VLA、video generation policy 的边界。
3. 在 [papers.md](papers.md) 中补齐这些论文的链接和笔记入口。
4. 为每个高优先级系统（OpenVLA、Octo、pi0、DreamZero）补 case study 或扩展现有 case study。
