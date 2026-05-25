# 总览地图

## 一句话版本

具身智能研究的是：智能系统如何通过身体在真实或仿真环境里感知、行动、试错、学习，并完成任务。

## 一个最小例子

假设你想让机器人“把桌上的杯子放进水槽”。

系统至少要解决这些问题：

1. 看见桌子、杯子、水槽和障碍物。
2. 理解“放进水槽”这个目标。
3. 知道杯子在哪里，水槽在哪里，机械臂当前在哪里。
4. 规划如何靠近、抓取、移动、放下。
5. 控制电机执行动作。
6. 如果杯子滑了、被挡住了、抓歪了，要能发现并修正。
7. 用数据和反馈让下一次做得更好。

这就是本仓库的目录顺序。

## 技术环节对应表

| 问题 | 对应目录 | 基础理解 |
| --- | --- | --- |
| 机器人看到了什么？ | [02-perception](../02-perception/README.md) | 从图像、深度、触觉等信号中识别环境 |
| 世界和动作怎么表示？ | [03-representation](../03-representation/README.md) | 把连续复杂世界变成模型能处理的状态、对象和动作 |
| 训练数据从哪来？ | [04-data](../04-data/README.md) | 遥操作、仿真、人类视频、机器人自采集 |
| 策略怎么学？ | [05-policy-learning](../05-policy-learning/README.md) | 从示范、奖励或大规模数据中学会动作 |
| 如何执行任务？ | [06-planning-and-control](../06-planning-and-control/README.md) | 把目标拆成步骤，并控制机器人完成 |
| 怎么判断好坏？ | [07-simulation-and-evaluation](../07-simulation-and-evaluation/README.md) | 在仿真和真实环境里评测成功率、泛化和安全 |
| 怎么真实落地？ | [08-hardware-and-deployment](../08-hardware-and-deployment/README.md) | 处理硬件、安全、延迟、成本和维护 |

## 常见误区

- 误区 1：只看大模型，忽略硬件和控制。
- 误区 2：只看 demo，不看评测设置和失败样本。
- 误区 3：把仿真成功当成真实世界成功。
- 误区 4：把单任务成功率当成通用能力。
- 误区 5：一上来就追所有论文，结果没有主线。

## 最小学习路线

1. 读懂 [what-is-embodied-ai.md](what-is-embodied-ai.md)。
2. 看 [../01-system-overview/README.md](../01-system-overview/README.md)。
3. 每个技术环节先读 README，不急着读细节。
4. 再从 [../10-case-studies/README.md](../10-case-studies/README.md) 选一个系统拆解。
5. 最后用 [../09-frontier-tracking/papers.md](../09-frontier-tracking/papers.md) 选论文精读。

## 7 天入门路径

如果你只有一周，可以这样读：

| 天 | 目标 | 阅读 |
| --- | --- | --- |
| Day 1 | 建立全局地图 | [what-is-embodied-ai.md](what-is-embodied-ai.md), [../01-system-overview/system-loop.md](../01-system-overview/system-loop.md) |
| Day 2 | 看懂任务类型和系统证据 | [../01-system-overview/task-types.md](../01-system-overview/task-types.md), [../01-system-overview/how-to-read-a-system.md](../01-system-overview/how-to-read-a-system.md) |
| Day 3 | 理解感知和表征 | [../02-perception/perception-pipeline.md](../02-perception/perception-pipeline.md), [../03-representation/action-representation.md](../03-representation/action-representation.md) |
| Day 4 | 理解数据为什么关键 | [../04-data/data-lifecycle.md](../04-data/data-lifecycle.md), [../04-data/teleoperation.md](../04-data/teleoperation.md) |
| Day 5 | 理解策略学习 | [../05-policy-learning/behavior-cloning.md](../05-policy-learning/behavior-cloning.md), [../05-policy-learning/vision-language-action.md](../05-policy-learning/vision-language-action.md) |
| Day 6 | 理解规划、控制和失败恢复 | [../06-planning-and-control/robot-kinematics-basics.md](../06-planning-and-control/robot-kinematics-basics.md), [../06-planning-and-control/task-planning.md](../06-planning-and-control/task-planning.md), [../06-planning-and-control/failure-recovery.md](../06-planning-and-control/failure-recovery.md) |
| Day 7 | 理解评测和部署 | [../07-simulation-and-evaluation/benchmark-design.md](../07-simulation-and-evaluation/benchmark-design.md), [../08-hardware-and-deployment/safety-and-operations.md](../08-hardware-and-deployment/safety-and-operations.md) |

读完这 7 天，不需要记住所有名词，但应该能判断一篇材料主要属于哪个技术环节，以及它的证据强不强。
