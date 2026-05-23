# 开源项目

| 项目 | 类型 | 作用 | 技术栈 | 活跃度 | 链接 | 备注 |
| --- | --- | --- | --- | --- | --- | --- |
| LeRobot | framework / dataset / tool | 机器人学习数据、训练、硬件接口和策略复现 | Python, PyTorch, HF Hub | 高 | 待补链接 | 重点观察数据格式、硬件抽象和 VLA/IL/RL 策略实现 |
| OpenVLA | model | 开源 VLA 模型和项目生态 | VLM, robotics policy | 待复查 | 待补链接 | 需要补代码、论文和复现情况 |
| Octo | model | 通用机器人策略 | Transformer policy | 待复查 | 待补链接 | 与 Open X-Embodiment 数据强相关 |
| RoboTwin 2.0 | 仿真器 / 基准 / 数据生成器 | 双臂操作仿真、数据合成、训练评测闭环 | SAPIEN, dual-arm simulation, evaluation tooling | 高 | [项目页](https://robotwin-platform.github.io/) | 适合连接“仿真-数据-策略-评测”全流程，双臂方向值得持续观察 |
| ManiSkill | simulator / benchmark | 操作任务仿真和 benchmark | Python, GPU simulation | 待复查 | [项目页](https://maniskill.ai/) | 放入仿真和评测双重跟踪 |
| RLBench | benchmark / environment | 机器人学习 benchmark | CoppeliaSim, PyRep | 待复查 | 待补官方链接 | 适合补历史基准 |

## 观察维度

- 是否可复现。
- 是否有真实机器人接口。
- 是否活跃维护。
- 是否有社区和生态。
- 是否能作为本仓库后续实验基础。

## 收录原则

开源项目优先依据官方代码仓库、官方项目页和论文原文收录。新增项目时优先补充 `作用`、`可复现性`、`真实机器人接口` 和 `数据/模型许可`。
