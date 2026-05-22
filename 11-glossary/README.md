# 11 Glossary

术语表用于统一概念和缩写。初学者遇到陌生词时，先来这里查工作定义，再跳到对应技术环节。

| 术语 | 英文 | 工作定义 | 相关页面 |
| --- | --- | --- | --- |
| 具身智能 | Embodied AI | 通过身体或物理执行接口与环境闭环交互的智能系统。 | [what-is-embodied-ai](../00-start-here/what-is-embodied-ai.md) |
| 感知 | Perception | 从图像、深度、触觉和状态信号中理解环境。 | [perception](../02-perception/README.md) |
| 表征 | Representation | 把世界、状态、对象和动作转成模型可处理的形式。 | [representation](../03-representation/README.md) |
| 视觉语言动作模型 | Vision-Language-Action Model, VLA | 将视觉、语言和动作统一建模，用于机器人任务执行的模型。 | [models](../05-policy-learning/models.md) |
| 世界模型 | World Model | 学习环境如何随状态和行动变化的模型。 | [world-models](../03-representation/world-models.md) |
| Sim2Real | Simulation to Reality | 将仿真训练或验证的能力迁移到真实系统。 | [sim2real](../07-simulation-and-evaluation/sim2real.md) |
| 模仿学习 | Imitation Learning | 从专家示范中学习策略的方法。 | [robot-learning-basics](../05-policy-learning/robot-learning-basics.md) |
| 强化学习 | Reinforcement Learning | 通过奖励信号和交互优化策略的方法。 | [robot-learning-basics](../05-policy-learning/robot-learning-basics.md) |
| 行为克隆 | Behavior Cloning | 直接学习观察到动作映射的模仿学习方法。 | [robot-learning-basics](../05-policy-learning/robot-learning-basics.md) |
| 动作表示 | Action Representation | 模型输出动作的形式，例如关节控制、轨迹或动作 token。 | [action-representation](../03-representation/action-representation.md) |
| 遥操作 | Teleoperation | 人类远程控制机器人完成任务并记录训练数据。 | [teleoperation](../04-data/teleoperation.md) |
| 扩散策略 | Diffusion Policy | 用扩散生成模型生成动作序列的机器人策略方法。 | [diffusion-policy](../05-policy-learning/diffusion-policy.md) |
| 任务规划 | Task Planning | 把高层目标拆成可执行子任务。 | [task-planning](../06-planning-and-control/task-planning.md) |
| 运动规划 | Motion Planning | 计算机器人从当前位置到目标位置的安全路径或轨迹。 | [motion-planning](../06-planning-and-control/motion-planning.md) |
| 技能库 | Skill Library | 可复用机器人技能的集合，例如抓取、放置、导航。 | [skill-library](../06-planning-and-control/skill-library.md) |
| 失败恢复 | Failure Recovery | 发现动作失败、定位原因并重新回到可执行状态。 | [failure-recovery](../06-planning-and-control/failure-recovery.md) |
| 可供性 | Affordance | 环境或物体对某种动作的可执行性，例如哪里可抓、哪里可放。 | [perception-pipeline](../02-perception/perception-pipeline.md) |
| 本体感知 | Proprioception | 机器人对自身关节、速度、末端状态等内部状态的感知。 | [tactile-and-proprioception](../02-perception/tactile-and-proprioception.md) |
| Benchmark | Benchmark | 用于比较方法的标准任务、数据集或评测协议。 | [benchmark-design](../07-simulation-and-evaluation/benchmark-design.md) |

## 待补术语

- Diffusion Policy
- Offline RL
- Contact-Rich Manipulation
- Action Tokenization
- World-Action Model
