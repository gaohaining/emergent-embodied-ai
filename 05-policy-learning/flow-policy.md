# Flow Policy

## It Solves What

Flow policy 或 flow matching 路线关注如何用连续生成过程生成机器人动作。它和 diffusion policy 一样属于生成式动作策略，但推理路径和训练目标不同。

## Plain Explanation

扩散策略像“从噪声慢慢去噪成动作”，flow matching 更像“学习一条从噪声流向动作的连续路径”。两者都试图避免简单回归带来的平均动作问题。

## Common Methods

- 学习从简单分布到动作分布的流。
- 生成连续动作或动作序列。
- 结合视觉、语言和机器人状态作为条件。
- 用于 VLA 或低层策略的动作生成头。

## Why It Matters In Embodied AI

- 可能比多步 diffusion 推理更高效。
- 适合表示复杂、多峰动作分布。
- 和通用机器人控制模型关系紧密。

## Typical Failure Modes

- 生成动作仍可能违反安全和动力学约束。
- 数据不足时容易学到不稳定动作。
- 长程任务仍需要规划、记忆和恢复。

## Advanced Notes

- 需要关注推理延迟、控制频率和动作平滑性。
- 不能只比较离线 loss，要看实机闭环表现。

## Open Questions

- Flow policy 和 diffusion policy 在不同任务上如何取舍？
- 生成式动作模型能否满足高频控制？
- 它更适合作为端到端策略，还是低层动作头？
