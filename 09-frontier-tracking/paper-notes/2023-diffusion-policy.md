# Diffusion Policy：基于动作扩散的视觉运动策略学习（Diffusion Policy: Visuomotor Policy Learning via Action Diffusion）

## 元信息

- 年份：2023
- 技术链路：动作生成、视觉运动策略、模仿学习
- 链接：[arXiv](https://arxiv.org/abs/2303.04137), [项目页](https://diffusion-policy.cs.columbia.edu/)
- 相关页面：[../papers.md](../papers.md), [../../05-policy-learning/diffusion-policy.md](../../05-policy-learning/diffusion-policy.md)
- 状态：种子笔记

## 一句话总结

Diffusion Policy 让“生成一段动作序列”成为机器人操作策略中的主流建模方式之一。

## 它解决什么问题

机器人动作分布常常是连续、高维、多模态的。简单回归容易把多个可行动作平均掉，产生不稳定或物理上别扭的动作。

## 方法

这篇论文把机器人动作生成建模为条件去噪扩散过程。它不是直接预测单步动作，而是在观察和任务条件下生成一段短时域动作序列。

关键接口：

- 输入：视觉观察、机器人状态、任务条件。
- 输出：短时域动作序列。
- 执行方式：通常结合 receding horizon control，随着新观察不断重新规划。

## 证据

- 评测：操作 benchmark 和真实机器人任务。
- 证据类型：论文 / 项目页 / 代码。
- 为什么重要：它证明生成式建模不只适用于图像或语言，也可以成为实用的机器人动作头。

## 优点

- 比朴素回归更适合处理多模态动作分布。
- 能生成较平滑的动作片段，适合操作任务。
- 成为后续 Flow Policy 和 VLA 动作头研究的重要参照。

## 局限

- 迭代采样会带来推理延迟。
- 仍然依赖高质量示范和任务覆盖。
- 它本身不解决高层语义理解，通常只是更大系统里的动作生成方法。

## 改变了什么判断

- 对基础支持的影响：动作可以被看成条件生成问题，而不是单步回归。
- 对发展路径的影响：后续 VLA、pi0、Flow Policy 都可以围绕“动作生成头”比较。
- 对前沿判断的影响：实时性和安全约束是生成式策略能否上真机的核心问题。

## 问题

- 在同等延迟预算下，Diffusion Policy 和 Flow Policy 如何比较？
- 动作 chunk 的长度如何影响稳定性和失败恢复？
- 在长程任务里，扩散动作头需要怎样和高层规划器结合？

## 后续

- 与 [../../05-policy-learning/flow-policy.md](../../05-policy-learning/flow-policy.md) 做对照。
- 补充真实机器人部署中的延迟和控制频率经验。
