# Learning Roadmap

## Phase 1: 基础地图

- 明确具身智能、机器人学习、多模态模型、控制和仿真的关系。
- 阅读基础综述和代表性系统论文。
- 建立术语表和路线图。

建议阅读：

- [../00-start-here/what-is-embodied-ai.md](../00-start-here/what-is-embodied-ai.md)
- [../01-system-overview/system-loop.md](../01-system-overview/system-loop.md)
- [../01-system-overview/task-types.md](../01-system-overview/task-types.md)
- [../01-system-overview/how-to-read-a-system.md](../01-system-overview/how-to-read-a-system.md)

## Phase 2: 技术栈拆解

- 数据：遥操作、机器人数据集、人类视频。
- 模型：VLA、diffusion policy、world model、层级策略。
- 系统：仿真、控制、安全、部署。
- 评测：benchmark、实机任务、失败模式。

建议按技术环节读：

- 感知：[../02-perception/perception-pipeline.md](../02-perception/perception-pipeline.md)
- 表征：[../03-representation/spatial-representation.md](../03-representation/spatial-representation.md), [../03-representation/action-representation.md](../03-representation/action-representation.md)
- 数据：[../04-data/data-lifecycle.md](../04-data/data-lifecycle.md), [../04-data/teleoperation.md](../04-data/teleoperation.md)
- 策略：[../05-policy-learning/behavior-cloning.md](../05-policy-learning/behavior-cloning.md), [../05-policy-learning/diffusion-policy.md](../05-policy-learning/diffusion-policy.md), [../05-policy-learning/vision-language-action.md](../05-policy-learning/vision-language-action.md)
- 规划控制：[../06-planning-and-control/task-planning.md](../06-planning-and-control/task-planning.md), [../06-planning-and-control/motion-planning.md](../06-planning-and-control/motion-planning.md), [../06-planning-and-control/failure-recovery.md](../06-planning-and-control/failure-recovery.md)
- 仿真评测：[../07-simulation-and-evaluation/benchmark-design.md](../07-simulation-and-evaluation/benchmark-design.md)
- 硬件部署：[../08-hardware-and-deployment/safety-and-operations.md](../08-hardware-and-deployment/safety-and-operations.md)

## Phase 2.5: VLA 专题阅读

按论文和官方项目页的顺序，建议这样读：

1. VLM 和视觉表征基础：CLIP、SigLIP、DINOv2、R3M。
2. 机器人策略基础：行为克隆、diffusion policy、ACT、RT-1。
3. VLA 代表系统：RT-2、OpenVLA、Octo、RT-X、pi0。
4. 动作表示：连续动作、离散 token、flow matching、action tokenizer。
5. 世界模型和 WAM：预测未来状态、video-action、world-action model。
6. 部署约束：延迟、量化、失败恢复、安全和人工接管。

## Phase 3: 前沿跟踪

- 每周跟踪论文、公司、开源项目和 benchmark。
- 每月更新路线判断。
- 每季度做主题综述。

## Phase 4: 实验或产品化连接

- 选择一个可复现实验。
- 建立最小数据和评测流程。
- 记录系统瓶颈和可扩展性。

建议输出：

- 一个案例拆解。
- 一篇论文笔记。
- 一个术语表扩展。
- 一个你认为最关键的技术瓶颈判断。
