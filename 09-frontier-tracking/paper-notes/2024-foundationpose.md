# FoundationPose：新物体统一 6D 位姿估计与跟踪（FoundationPose: Unified 6D Pose Estimation and Tracking of Novel Objects）

## 元信息

- 年份：2024
- 技术链路：感知、6D 位姿、对象中心操作
- 链接：[项目页](https://nvlabs.github.io/FoundationPose/)
- 相关页面：[../papers.md](../papers.md), [../tooling-and-system-stack.md](../tooling-and-system-stack.md), [../../02-perception/visual-perception.md](../../02-perception/visual-perception.md)
- 状态：种子笔记

## 一句话总结

FoundationPose 重要的原因是：很多机器人操作系统需要的是物体姿态，而不只是物体类别或 mask。

## 它解决什么问题

开放词表感知可以告诉机器人“这里有什么物体”，但操作经常需要知道物体的 6D 位姿，也就是位置和朝向。新物体会让这个问题更难，因为系统不能只依赖固定类别训练集。

## 方法

FoundationPose 统一处理新物体的 6D 位姿估计和跟踪。它适合作为抓取、放置、装配或对象中心操作之前的感知模块。

关键接口：

- 输入：RGB 或 RGB-D 观察、物体信息或参考。
- 输出：6D 物体姿态和跟踪信号。
- 下游用途：抓取规划、空间约束、操作规划。

## 证据

- 评测：位姿估计与跟踪 benchmark，以及项目演示。
- 证据类型：论文 / 项目页 / 代码。
- 为什么重要：它可以作为更大具身系统中的对象中心感知模块。

## 优点

- 直接解决 VLM 本身不处理的几何需求。
- 是从视觉感知走向操作规划的重要桥梁。
- 能与语言条件检测、分割系统互补。

## 局限

- 位姿质量可能受遮挡、反光材质、深度噪声和物体几何影响。
- 位姿是操作的必要条件之一，但不足以解决抓取可供性、接触和动力学。
- 真机集成依赖相机标定和坐标系对齐。

## 改变了什么判断

- 对基础支持的影响：感知页需要区分“识别/分割”和“可操作姿态估计”。
- 对发展路径的影响：VLA 系统即使端到端，也可能需要显式 6D pose 或 object-centric state 作为辅助。
- 对前沿判断的影响：可靠 3D 感知和标定仍是具身系统落地瓶颈。

## 问题

- FoundationPose 与 Grounded-SAM、Grounding DINO 如何组合成稳定 pipeline？
- 对透明、反光、柔性物体的可靠性如何？
- 显式 pose 和 VLA latent spatial representation 如何互补？

## 后续

- 补充到感知 pipeline 和工具链页。
- 与 VoxPoser、OmniManip 等空间约束类方法联读。
