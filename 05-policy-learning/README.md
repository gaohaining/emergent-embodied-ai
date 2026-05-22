# 05 Policy Learning

策略学习解决的问题是：机器人如何从数据、示范或交互中学会选择动作。

## 先读

1. [robot-learning-basics.md](robot-learning-basics.md)：机器人学习基础。
2. [models.md](models.md)：模型架构和策略学习。
3. [behavior-cloning.md](behavior-cloning.md)：行为克隆。
4. [diffusion-policy.md](diffusion-policy.md)：扩散策略。
5. [vision-language-action.md](vision-language-action.md)：视觉语言动作模型。
6. [reinforcement-learning.md](reinforcement-learning.md)：强化学习在机器人中的位置。

## 常见路线

- Behavior Cloning：直接模仿专家动作。
- Imitation Learning：从示范中学习策略。
- Reinforcement Learning：通过奖励和试错学习。
- Offline RL：从已有数据中学习，减少真实试错。
- Diffusion Policy：用扩散模型生成动作轨迹。
- VLA：从视觉、语言和状态生成动作。

## 常见误区

- 训练 loss 低不代表真实机器人成功率高。
- 单任务策略强不代表多任务泛化强。
- 大模型会理解语言，但不一定会稳定控制动作。
- 真实机器人上的失败恢复比一次成功更重要。

## 一个最小策略学习问题

给定：

- 观察：相机图像、机器人状态、语言指令。
- 目标：把物体放到指定位置。
- 数据：人类遥操作示范。

学习：

- 从当前观察和目标输出下一步动作。

评测：

- 在新物体、新位置、新光照下是否仍能完成任务。
