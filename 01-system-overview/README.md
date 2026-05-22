# 01 System Overview

这个目录帮助读者先看懂“一个具身智能系统长什么样”，再进入各个技术环节。

## 推荐阅读

1. [system-loop.md](system-loop.md)：感知、行动、反馈和学习闭环。
2. [task-types.md](task-types.md)：具身智能常见任务类型。
3. [how-to-read-a-system.md](how-to-read-a-system.md)：如何读懂一个系统、论文或项目。
4. [enabling-stack-overview.md](enabling-stack-overview.md)：支撑栈总览。
5. [capability-ladder.md](capability-ladder.md)：从远程控制到持续学习的能力阶梯。
6. [enabling-stack-index.md](enabling-stack-index.md)：早期支撑栈索引。

## 一个系统的核心闭环

```text
目标或指令
→ 感知环境
→ 建立状态和任务表示
→ 选择或生成动作
→ 控制机器人执行
→ 观察结果
→ 修正动作或继续学习
```

## 先抓住的三个问题

- 输入是什么：图像、语言、深度、触觉、本体状态？
- 输出是什么：低层电机控制、末端轨迹、动作 token、子任务？
- 反馈是什么：成功、失败、奖励、视觉变化、人类纠错？
