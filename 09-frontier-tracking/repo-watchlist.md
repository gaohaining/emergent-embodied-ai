# Primary Source Workflow

这个页面说明本仓库如何优先从论文、官方项目页、代码仓库、数据集页面和 benchmark 页面整理材料。

目标不是收集外部“资源列表”，而是保证这里的内容尽量回到一手来源。

## 优先来源

- 论文原文：方法、实验设置、指标、局限和相关工作。
- 官方项目页：任务定义、演示、补充实验、模型与数据下载入口。
- 官方代码仓库：训练脚本、数据格式、推理接口、依赖和可复现性。
- 数据集页面：规模、标注方式、许可、机器人平台和采集流程。
- benchmark 页面：任务划分、评测协议、成功标准和已知局限。
- 官方博客或实验室发布：适合补时间线、版本关系和产品化上下文，但关键事实仍优先回到论文或代码确认。

## 适合优先补的方向

- VLA：OpenVLA、RT-2、Octo、pi0、TraceVLA、SpatialVLA。
- World Model / WAM：World Models、Dreamer、DayDreamer、DreamZero、GigaWorld-Policy。
- 动作生成：Diffusion Policy、FlowPolicy、VFP、ACT。
- 仿真与 benchmark：RoboTwin 2.0、ManiSkill、RLBench、CALVIN、LIBERO、BEHAVIOR。
- 工程工具链：Open3D、FoundationPose、Grounding DINO、ROS 2、MoveIt 2、cuRobo、Isaac Lab、SAPIEN。

## 使用方式

1. 先找论文或官方项目页，确认问题定义和证据。
2. 再看官方代码仓库，确认接口、依赖、训练和推理路径。
3. 如果是数据集或 benchmark，再看官方数据页与评测页。
4. 社区讨论、中文长文和综述只作为发现线索，不作为最终事实来源。
5. 整理后把材料分流到：
   [papers.md](papers.md)、[open-source.md](open-source.md)、[datasets-and-benchmarks.md](datasets-and-benchmarks.md)、[community-insights.md](community-insights.md)。

## 公开仓库原则

- 尽量链接一手来源，而不是链接二手整理仓库。
- 用自己的话总结，不镜像外部列表结构。
- 对可能快速变化的内容标注复查时间。
- 当社区观点和论文结论不一致时，优先保留分歧，而不是强行合并成单一判断。
