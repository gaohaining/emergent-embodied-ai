# 11 Glossary

术语表用于统一概念和缩写。遇到陌生词时，可以先来这里查工作定义，再跳到对应技术环节。

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
| 运动学 | Robot Kinematics | 描述机器人关节、连杆和末端执行器之间几何关系的方法，不直接处理力和质量。 | [robot-kinematics-basics](../06-planning-and-control/robot-kinematics-basics.md) |
| 正向运动学 / 正解 | Forward Kinematics, FK | 已知机器人关节状态，计算末端执行器的位置和朝向。 | [robot-kinematics-basics](../06-planning-and-control/robot-kinematics-basics.md) |
| 逆向运动学 / 逆解 | Inverse Kinematics, IK | 已知目标末端位姿，求一组可行关节状态。 | [robot-kinematics-basics](../06-planning-and-control/robot-kinematics-basics.md) |
| 自由度 | Degree of Freedom, DoF | 机器人可以独立运动的维度，一个旋转关节通常对应 1 个自由度。 | [robot-kinematics-basics](../06-planning-and-control/robot-kinematics-basics.md) |
| 末端执行器 | End Effector | 机器人真正执行任务的末端工具，例如夹爪、吸盘或焊枪。 | [robot-kinematics-basics](../06-planning-and-control/robot-kinematics-basics.md) |
| 位姿 | Pose | 位置和朝向的组合，用来描述物体、相机或末端执行器在空间中的状态。 | [spatial-representation](../03-representation/spatial-representation.md), [robot-kinematics-basics](../06-planning-and-control/robot-kinematics-basics.md) |
| 关节空间 | Joint Space | 用每个关节的位置或速度描述机器人状态的空间。 | [robot-kinematics-basics](../06-planning-and-control/robot-kinematics-basics.md) |
| 笛卡尔空间 | Cartesian Space | 用真实空间中的位置和朝向描述目标的空间。 | [robot-kinematics-basics](../06-planning-and-control/robot-kinematics-basics.md) |
| 机器人模型 | Robot Model | 描述机器人连杆、关节、坐标系、限制和碰撞几何的结构信息。 | [robot-kinematics-basics](../06-planning-and-control/robot-kinematics-basics.md) |
| URDF | Unified Robot Description Format | ROS 生态中常见的机器人结构描述格式，用于记录连杆、关节、坐标系和碰撞几何。 | [robot-kinematics-basics](../06-planning-and-control/robot-kinematics-basics.md) |
| 雅可比矩阵 | Jacobian | 描述关节小变化如何影响末端位置或速度的数学对象。 | [robot-kinematics-basics](../06-planning-and-control/robot-kinematics-basics.md) |
| 奇异点 | Singularity | 机器人在某些姿态下失去部分可控方向，或需要极大关节速度才能产生末端运动的状态。 | [robot-kinematics-basics](../06-planning-and-control/robot-kinematics-basics.md) |
| 运动规划 | Motion Planning | 计算机器人从当前位置到目标位置的安全路径或轨迹。 | [motion-planning](../06-planning-and-control/motion-planning.md) |
| 技能库 | Skill Library | 可复用机器人技能的集合，例如抓取、放置、导航。 | [skill-library](../06-planning-and-control/skill-library.md) |
| 失败恢复 | Failure Recovery | 发现动作失败、定位原因并重新回到可执行状态。 | [failure-recovery](../06-planning-and-control/failure-recovery.md) |
| 可供性 | Affordance | 环境或物体对某种动作的可执行性，例如哪里可抓、哪里可放。 | [perception-pipeline](../02-perception/perception-pipeline.md) |
| 本体感知 | Proprioception | 机器人对自身关节、速度、末端状态等内部状态的感知。 | [tactile-and-proprioception](../02-perception/tactile-and-proprioception.md) |
| Benchmark | Benchmark | 用于比较方法的标准任务、数据集或评测协议。 | [benchmark-design](../07-simulation-and-evaluation/benchmark-design.md) |
| 视觉语言模型 | Vision-Language Model, VLM | 同时处理视觉和语言输入的模型。 | [multimodal-understanding](../02-perception/multimodal-understanding.md) |
| 视觉动作模型 | Vision-Action Model, VAM | 从视觉观察直接预测动作或轨迹的模型，通常不把自然语言作为核心输入。 | [models](../05-policy-learning/models.md) |
| 世界动作模型 | World-Action Model, WAM | 将世界动态预测和动作生成耦合起来的模型路线，概念仍在演化中，常位于世界模型和 VLA 之间。 | [models](../05-policy-learning/models.md) |
| Action Chunking | Action Chunking | 一次预测一段动作序列，而不是单步动作。 | [act](../05-policy-learning/act.md) |
| 动作分词 | Action Tokenization | 把连续动作或动作序列压缩成离散 token，便于 Transformer 或 VLA 建模。 | [action-representation](../03-representation/action-representation.md) |
| 跨本体学习 | Cross-Embodiment Learning | 在不同机器人身体和动作空间之间复用经验。 | [cross-embodiment-learning](../05-policy-learning/cross-embodiment-learning.md) |
| 离线强化学习 | Offline Reinforcement Learning | 从固定数据集学习策略，减少在线试错。 | [offline-rl](../05-policy-learning/offline-rl.md) |
| 层级策略 | Hierarchical Policy | 把高层任务决策和低层动作控制分开。 | [hierarchical-policy](../05-policy-learning/hierarchical-policy.md) |
| Flow Policy | Flow Policy | 使用 flow matching 等连续生成过程生成机器人动作。 | [flow-policy](../05-policy-learning/flow-policy.md) |
| 灵巧操作 | Dexterous Manipulation | 涉及多指、触觉和复杂接触的精细操作。 | [dexterous-hands](../08-hardware-and-deployment/dexterous-hands.md) |
| 本体 | Embodiment | 智能系统的身体形态、传感器、动作空间和物理约束。 | [cross-embodiment-learning](../05-policy-learning/cross-embodiment-learning.md) |
| 电机 | Motor | 将电能转换为机械运动的执行部件，是机器人关节、轮子、夹爪和底盘的动力来源。 | [motor-basics](../08-hardware-and-deployment/motor-basics.md) |
| 无刷直流电机 | Brushless DC Motor, BLDC | 通过电子换相驱动的直流电机，常用于机器人关节、轮毂和高功率密度执行机构。 | [motor-basics](../08-hardware-and-deployment/motor-basics.md) |
| 力矩 | Torque | 使物体绕轴旋转的作用量，机器人关节输出能力通常用力矩描述。 | [motor-basics](../08-hardware-and-deployment/motor-basics.md) |
| 编码器 | Encoder | 测量电机或关节位置、速度的传感器，是闭环控制和状态观测的重要来源。 | [motor-basics](../08-hardware-and-deployment/motor-basics.md) |
| 减速器 | Gearbox / Reducer | 通过降低转速来放大输出力矩的机械传动部件，同时可能引入背隙、摩擦和效率损失。 | [motor-basics](../08-hardware-and-deployment/motor-basics.md) |
| 磁场定向控制 | Field-Oriented Control, FOC | BLDC/PMSM 中常用的电流控制方法，用于更平滑、高效地产生力矩。 | [motor-basics](../08-hardware-and-deployment/motor-basics.md) |

## 待补术语

- Contact-Rich Manipulation
