# Learning Roadmap

## Phase 1: 基础地图

- 明确具身智能、机器人学习、多模态模型、控制和仿真的关系。
- 阅读基础综述和代表性系统论文。
- 建立术语表和路线图。

## Phase 2: 技术栈拆解

- 数据：遥操作、机器人数据集、人类视频。
- 模型：VLA、diffusion policy、world model、层级策略。
- 系统：仿真、控制、安全、部署。
- 评测：benchmark、实机任务、失败模式。

## Phase 2.5: VLA 专题阅读

参考 [../09-frontier-tracking/repo-watchlist.md](../09-frontier-tracking/repo-watchlist.md) 中的 VLA 和 Physical AI 仓库，按以下顺序读：

1. VLM 和视觉表征基础：CLIP、SigLIP、DINOv2、R3M。
2. 机器人策略基础：行为克隆、diffusion policy、ACT、RT-1。
3. VLA 代表系统：RT-2、OpenVLA、Octo、RT-X、pi0。
4. 动作表示：连续动作、离散 token、flow matching、action tokenizer。
5. 世界模型和 WAM：预测未来状态、video-action、world-action model。
6. 部署约束：延迟、量化、失败恢复、安全和人工接管。

## Phase 3: 前沿跟踪

- 每周跟踪论文、公司、开源项目和 benchmark。
- 每月更新路线判断。
- 每季度做主题综述。

## Phase 4: 实验或产品化连接

- 选择一个可复现实验。
- 建立最小数据和评测流程。
- 记录系统瓶颈和可扩展性。
