# Offline Reinforcement Learning

## It Solves What

离线强化学习（Offline RL）试图只用已有数据学习策略，减少真实机器人在线试错的成本和风险。

## Plain Explanation

真实机器人不能像游戏一样随便试错。Offline RL 的目标是在不继续探索真实环境的情况下，从过去收集的数据里学出更好的策略。

## Common Methods

- 从固定数据集学习价值函数或策略。
- 限制策略不要偏离数据分布太远。
- 和模仿学习结合，先模仿再优化。
- 用 conservative 目标减少过度乐观估计。

## Why It Matters In Embodied AI

- 真实机器人数据昂贵，不能浪费。
- 能利用失败、成功和人工接管日志。
- 适合把历史部署数据转成策略改进。

## Typical Failure Modes

- 数据覆盖不到的动作会被错误高估。
- 奖励定义不清楚，学到的策略不可用。
- 数据集偏差会被策略放大。
- 离线指标好，不代表实机闭环好。

## Advanced Notes

- Offline RL 的价值取决于数据多样性和奖励/成功标签质量。
- 在机器人中，它更可能成为数据飞轮的一环，而不是独立解决方案。

## Open Questions

- 机器人日志如何自动生成可靠奖励？
- Offline RL 和 VLA 预训练如何结合？
- 失败数据是否能显著提升 offline policy 的安全性？
