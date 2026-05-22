# 06 Planning And Control

规划与控制解决的问题是：如何把目标变成机器人可以执行的动作序列。

## 先读

- [cognition-and-control.md](cognition-and-control.md)：认知、控制和行动闭环。
- [task-planning.md](task-planning.md)：任务规划。
- [motion-planning.md](motion-planning.md)：运动规划。
- [skill-library.md](skill-library.md)：技能库。
- [failure-recovery.md](failure-recovery.md)：失败检测和恢复。

## 分层理解

- 任务规划：先做什么，后做什么。
- 运动规划：如何避障并到达目标位姿。
- 技能选择：调用抓取、放置、导航、开门等技能。
- 低层控制：控制电机、关节、末端执行器。
- 反馈修正：失败后重新感知和调整。

## 为什么不能只靠大模型

语言模型适合表达目标和分解步骤，但真实机器人还需要满足物理约束、实时性、安全边界和控制稳定性。

## Open Questions

- 高层 LLM/VLM 与低层控制器的接口应该是什么？
- 技能库和端到端策略会如何融合？
- 长程任务失败后，系统如何自动恢复？
