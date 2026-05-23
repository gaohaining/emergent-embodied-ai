# VoxPoser：用于机器人操作的可组合 3D Value Map（VoxPoser: Composable 3D Value Maps for Robotic Manipulation with Language Models）

## 元信息

- 年份：2023
- 技术链路：LLM 规划、3D 操作、空间约束
- 链接：[arXiv](https://arxiv.org/abs/2307.05973), [项目页](https://voxposer.github.io/)
- 相关页面：[../papers.md](../papers.md), [../../06-planning-and-control/task-planning.md](../../06-planning-and-control/task-planning.md), [../../03-representation/spatial-representation.md](../../03-representation/spatial-representation.md)
- 状态：种子笔记

## 一句话总结

VoxPoser 是语言推理和机器人运动之间的一座桥：它把语言条件下的意图转成 3D value map 和约束，让运动规划器可以使用。

## 它解决什么问题

大语言模型可以描述“应该做什么”，但机器人操作需要空间目标、约束和避障执行。关键缺口在于：如何把语言计划变成可用于 3D 运动规划的接口。

## 方法

系统从语言和视觉信息中组合 3D value map 和 constraint map。这些地图指导运动规划器朝满足指令的位置和关系移动。

关键接口：

- 输入：语言指令、场景观察、物体 grounding。
- 中间表示：3D value map 和空间约束。
- 输出：可供规划器使用的操作目标。

## 证据

- 评测：桌面操作任务。
- 证据类型：论文 / 项目页 / 代码。
- 为什么重要：它代表了一条不同于纯端到端 VLA 控制的模块化路线。

## 优点

- 通过空间地图让语言到动作的过程更可解释。
- 显式使用对象、约束、目标和规划结构。
- 适合作为 VLM/LLM 与经典运动规划结合的代表参考。

## 局限

- 依赖感知和物体 grounding 质量。
- 复杂接触丰富操作可能需要比静态 value map 更丰富的动力学表示。
- 当语言指令没有明确空间关系时，系统仍会继承 LLM 的歧义。

## 改变了什么判断

- 对基础支持的影响：语言模型可以通过 3D 中间表示接入机器人控制，而不必直接输出动作。
- 对发展路径的影响：模块化 LLM + 感知 + 规划路线仍有研究价值，不应被 VLA 叙事完全盖住。
- 对前沿判断的影响：可解释空间约束可能是长期部署中比端到端动作更容易调试的接口。

## 问题

- 3D value map 与 VLA 内部空间表示能否融合？
- 接触、力和可变形物体如何进入这种表示？
- 它和 OmniManip 这类 object-centric spatial constraint 路线有什么共同接口？

## 后续

- 与 FoundationPose、Grounding DINO、Open3D 等感知工具链建立连接。
- 将稳定结论迁移到空间表示和任务规划主题页。
