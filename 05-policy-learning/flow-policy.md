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

## Flow Matching vs 自回归：核心对比

这是当前具身领域最活跃的架构争论。两者对"动作是什么"有不同的 inductive bias：

| 维度 | 自回归（Autoregressive） | Flow Matching（连续） |
|------|------------------------|---------------------|
| 动作表示 | 离散 token，量化误差不可避免 | 连续输出，无量化损失 |
| 控制频率 | 难以支持 >10Hz 精细控制 | 支持 50Hz 高频关节控制 |
| 长轨迹精度 | 逐步预测，误差随步数累积 | 直接生成完整轨迹 |
| 训练基础设施 | 可直接复用 LLM 全套工具链 | 需要单独搭建生成模型框架 |
| Scaling 经验 | 继承大模型多年积累 | 相对较新，经验积累少 |
| 灵巧操作 | 离散化后难以表达细粒度动作 | 天然适合连续关节空间 |

**Flow Matching 优势的物理直觉**：机器人关节角度、末端位姿都是连续量，强制离散化会丢失精度。Flow Matching 直接学习连续空间上的流，inductive bias 更匹配。

**自回归优势的工程直觉**：整套 LLM 训练 infra（数据并行、混合精度、长程上下文）可以直接用，scaling 的路径已被验证。

### 融合趋势

两条路线并非绝对对立，最新进展试图取长补短：

- **FAST tokenizer**（Physical Intelligence，2024 年底）：改进动作 tokenization 方法，让自回归也能更精确地表示连续动作，训练速度提升约 5 倍。
- **一致性训练 + Flow Matching**（UW 团队）：实现近似 1 步生成，大幅降低推理延迟，使实时控制成为可能。

当前 π0（Physical Intelligence）等代表工作选择 Flow Matching 作为动作头；亮源新创等选择自回归为主。社区共识倾向于 Flow Matching 更适合连续控制，但自回归的工程优势使其仍有竞争力，尤其在大规模预训练阶段。

## Open Questions

- Flow policy 和 diffusion policy 在不同任务上如何取舍？
- 生成式动作模型能否满足高频控制？
- 它更适合作为端到端策略，还是低层动作头？
- FAST tokenizer 等改进是否能弥合自回归在连续动作上的精度差距？
- 随着具身模型规模扩大，两种范式的 scaling 效率差距是否会收敛？
