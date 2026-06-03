# 机器人策略模型路线图

Status: draft

Last checked: 2026-06-03

这条路线图整理“机器人如何从观察和目标生成可执行动作”的模型演进。它不强绑定 Manipulation；操作任务只是最常用的验证场景之一。对移动操作、服务机器人、人形机器人、导航和云端机器人平台，同样可以用这张图理解模型接口。

## 它解决什么

机器人策略模型要把这些输入变成动作：

- 视觉：图像、视频、深度、点云。
- 语言：人类指令、目标描述、任务上下文。
- 本体状态：关节、末端、底盘、夹爪、传感器状态。
- 历史：过去观察、动作、失败和纠正。

输出可以是：

- 单步动作。
- 一段动作 chunk。
- 连续轨迹。
- 离散动作 token。
- 技能调用。
- 先预测未来，再选择动作。

## 路线分层

| 阶段 | 核心问题 | 代表论文或系统 | 主要贡献 | 典型风险 |
| --- | --- | --- | --- | --- |
| 几何和可供性 | 哪里能抓、哪里能放、当前能做什么 | GraspNet、CLIPort、SayCan | 把视觉、语言和可执行性接起来 | 依赖任务结构和技能库 |
| 示范学习 | 如何从人类示范中学动作 | robomimic、ACT、ALOHA | 数据、硬件、动作分块形成实践闭环 | 分布外泛化弱 |
| 生成式动作头 | 动作是多模态连续分布，不能简单回归 | Diffusion Policy、DP3、RDT、pi0 | 用 diffusion / flow / transformer 生成动作序列 | 延迟、安全和失败恢复 |
| 数据和跨本体 | 不同机器人、任务和数据如何共享 | Open X、UMI、HPT、LeRobot | 数据格式、动作接口、共享表征 | 异构数据噪声和动作空间不统一 |
| VLA | 视觉、语言和动作如何统一建模 | RT-2、OpenVLA、Octo、SmolVLA、GR00T | 继承 VLM 语义知识并输出动作 | 语言强不等于物理执行强 |
| 世界模型和经验学习 | 如何预测后果、生成数据、从部署经验变强 | DreamerV3、UniSim、Cosmos、RECAP、GigaBrain | 数据增强、模拟、RL 自我提升 | 物理准确性、奖励和安全探索 |

## 主要路线

### 1. 技能库 + 语言规划

代表：SayCan、ChatGPT for Robotics。

这条路线把 LLM 放在高层，让它选择或编排已有技能。低层技能负责真实动作，affordance/value score 负责判断当前技能是否可执行。

优势：

- 可解释、可调试。
- 适合有可靠技能库的场景。
- 安全边界更容易加。

风险：

- 技能库覆盖不到的动作很难泛化。
- 高层语言计划容易忽略连续控制细节。
- 失败恢复依赖外部感知和状态反馈。

### 2. 示范学习 + 动作分块

代表：robomimic、ACT、ALOHA、Mobile ALOHA、UMI。

这条路线关注“怎么让人类示范变成策略”。ACT 的关键是一次预测动作 chunk，减少逐帧误差累积；ALOHA 和 UMI 则说明数据采集接口本身就是核心创新。

优势：

- 直接学真实任务，不必手写复杂控制逻辑。
- 低成本硬件和遥操作让实践门槛下降。
- 对短程和中程技能很有效。

风险：

- 任务和环境分布外容易失败。
- 示范质量、延迟匹配、相机配置和动作空间会强烈影响结果。
- 长程任务需要任务分解、记忆和恢复机制。

### 3. Diffusion / Flow 动作生成

代表：Diffusion Policy、DP3、RDT、pi0。

动作往往有多个合理解，直接回归会把多种动作平均成坏动作。Diffusion 和 flow 把动作看成条件生成分布，生成一段可执行轨迹。

优势：

- 能表达多模态动作分布。
- 适合连续、高维、接触丰富任务。
- 可以作为 VLA 或通用策略的动作头。

风险：

- Diffusion 迭代采样可能带来延迟。
- Flow 更快但需要验证复杂动作分布的保真度。
- 动作生成强不代表任务理解强。

### 4. VLA 和开源通用策略

代表：RT-2、OpenVLA、Octo、HPT、SmolVLA、GR00T。

VLA 试图把视觉、语言和动作放进统一模型。RT-2 让动作 token 进入 VLM 序列；OpenVLA 和 SmolVLA 把这条路线开源；GR00T 把模型接到 humanoid、仿真和部署平台。

优势：

- 有机会继承互联网视觉语言知识。
- 支持开放语言指令和多任务泛化。
- 开源模型让社区复现、微调和比较成为可能。

风险：

- 动作 token 化、连续控制、实时性和安全仍是硬问题。
- 训练数据远少于文本/图像数据。
- 跨本体泛化需要动作空间和状态接口设计，而不是简单扩大模型。

### 5. 世界模型 + RL + 数据飞轮

代表：DreamerV3、UniSim、Cosmos、pi*0.6 / RECAP、GigaBrain。

这条路线解决“纯模仿学习的天花板”。世界模型可以生成训练数据、预测动作后果或作为仿真环境；RL 可以从真实部署经验、专家纠正和自主尝试中继续提升策略。

优势：

- 有机会降低真实数据成本。
- 可以让策略从失败和部署经验中变强。
- 对长程任务、异常检测和安全评估有潜在价值。

风险：

- 世界模型的视觉真实不等于物理准确。
- RL 需要奖励、价值函数、安全探索和人类接管机制。
- 新近论文声称强，必须看公开代码、评测协议和独立复现。

## 重要误区

- 不要把 VLA 理解成“有语言就会干活”。语言理解和物理执行是两件事。
- 不要把 Diffusion Policy、Flow Policy 和 VLA 看成互斥路线。它们常常是动作头和上层模型的组合。
- 不要把开源等同于低门槛。相机、标定、动作空间、延迟、安全和数据质量仍然昂贵。
- 不要只看成功 demo。失败模式、恢复能力和部署监控决定真实价值。

## 阅读入口

- 论文横向比较：[../09-frontier-tracking/paper-notes/robot-strategy-models-comparison.md](../09-frontier-tracking/paper-notes/robot-strategy-models-comparison.md)
- 逐篇精读笔记：[../09-frontier-tracking/paper-notes/robot-strategy-models-detailed.md](../09-frontier-tracking/paper-notes/robot-strategy-models-detailed.md)
- 论文原文索引：[../09-frontier-tracking/papers-pdf/README.md](../09-frontier-tracking/papers-pdf/README.md)
- VLA 主题页：[../05-policy-learning/vision-language-action.md](../05-policy-learning/vision-language-action.md)
- Diffusion Policy：[../05-policy-learning/diffusion-policy.md](../05-policy-learning/diffusion-policy.md)
- Flow Policy：[../05-policy-learning/flow-policy.md](../05-policy-learning/flow-policy.md)
- 世界模型：[../03-representation/world-models.md](../03-representation/world-models.md)

## 当前判断

短期最稳的实践路线是：LeRobot / ALOHA / UMI 这类数据和硬件入口，加 ACT 或 Diffusion Policy 跑通真实技能，再尝试 SmolVLA、OpenVLA 或 openpi 微调。中期值得跟踪的是 VLA + 生成式动作头 + 低成本数据飞轮。长期不确定但重要的是世界模型和 RL 是否能把机器人从“静态模仿工具”推进到“部署中持续学习的物理智能体”。
