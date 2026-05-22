# 07 Simulation And Evaluation

仿真与评测解决的问题是：如何低成本训练、验证和比较具身智能能力。

## 先读

1. [sim2real.md](sim2real.md)：仿真到现实迁移。
2. [simulation.md](simulation.md)：仿真环境和合成数据。
3. [evaluation-basics.md](evaluation-basics.md)：评测基本问题。
4. [evaluation-stack.md](evaluation-stack.md)：benchmark 和实机评测字段。
5. [benchmark-design.md](benchmark-design.md)：如何设计和阅读 benchmark。

## 仿真的作用

- 低成本收集数据。
- 构造危险或罕见场景。
- 做大规模并行训练。
- 做系统回归测试。

## 评测的作用

- 判断任务是否真正完成。
- 区分 demo 和稳定能力。
- 发现泛化、鲁棒性和安全问题。
- 比较不同模型和系统路线。

## 要警惕

- 仿真成功不等于真实成功。
- benchmark 分数高不等于开放世界能力强。
- 只展示成功视频通常信息不足。
