# Action Chunking Transformer

## It Solves What

Action Chunking Transformer（ACT）关注一个很实际的问题：机器人控制如果一步一步预测动作，误差会快速累积；如果一次预测一段动作，策略可能更平滑、更稳定。

## Plain Explanation

把机器人动作想成一句话。逐字生成容易卡顿，一次生成一个短句会更连贯。ACT 的核心直觉类似：给定当前观察，预测未来一小段动作 chunk，而不是只预测下一帧动作。

## Common Methods

- 使用 Transformer 编码视觉和机器人状态。
- 输出一个动作序列片段。
- 在执行时滚动预测：执行一部分，再根据新观察重新预测。
- 常和模仿学习、遥操作数据一起使用。

## Why It Matters In Embodied AI

- 对精细操作和双臂操作有启发。
- 让行为克隆不只是单步回归。
- 和 diffusion policy、flow policy 一起构成“动作序列生成”方法谱系。

## Typical Failure Modes

- chunk 太短，仍然容易抖动。
- chunk 太长，对环境变化反应慢。
- 数据中如果示范不一致，模型会学到不稳定动作。
- 对长程任务仍需要高层规划或任务状态管理。

## Advanced Notes

- ACT 的关键不是 Transformer 本身，而是动作 chunking 对控制稳定性的影响。
- 它适合和“失败恢复”一起思考：chunk 执行中如何检测偏离并重规划？

## Open Questions

- 动作 chunk 长度如何自适应任务难度？
- ACT 和生成式动作模型如何融合？
- 双臂、人形和灵巧手任务中，chunking 是否需要分层？
