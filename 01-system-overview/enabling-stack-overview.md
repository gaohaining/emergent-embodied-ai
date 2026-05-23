# 基础支撑栈概览

## 分层视图

1. 硬件层：机器人本体、传感器、执行器、边缘计算。
2. 数据层：遥操作、仿真、人类视频、机器人自主采集、多任务数据集。
3. 表征层：视觉、语言、空间、物体、动作和状态表征。
4. 策略层：模仿学习、强化学习、VLA、世界模型、技能库。
5. 系统层：任务规划、控制、安全约束、监控、回滚、运维。
6. 评测层：benchmark、实机任务、长期部署指标。

## 从外部仓库吸收的横向分类

- Foundation models：VLM backbones、视觉表征、语言和多模态模型。
- Robot policy：VLA、diffusion policy、ACT、visuomotor policy、hierarchical policy。
- Action representation：连续动作、离散动作 token、轨迹、flow matching、world-action model。
- Data engine：遥操作、跨本体数据、数据格式、数据清洗、episode 管理。
- Simulation and benchmark：仿真训练、合成数据、任务环境、回归测试。
- Deployment：实时控制、压缩量化、安全、人机协作和监控。

## 观察框架

分析一个系统时，优先回答：

- 用了什么机器人平台？
- 数据从哪里来，规模多大，质量如何？
- 模型输入输出是什么？
- 动作表示和控制频率是什么？
- 是否支持新场景、新物体和新指令泛化？
- 是否有公开评测、代码、数据或实机视频？
- 成本、可靠性和部署条件是什么？
