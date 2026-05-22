# Repo Watchlist

这个页面记录具身智能相关代码仓库和资源列表，以及它们对本知识库结构的借鉴价值。

## 参考仓库清单

| 仓库 | 类型 | 覆盖重点 | 借鉴点 | 跟踪优先级 | 最近复查 |
| --- | --- | --- | --- | --- | --- |
| wadeKeith/Awesome-Embodied-AI | awesome list | surveys, VLA, datasets, simulators, humanoids, robot learning, safety | 大类覆盖完整，适合作为每周材料入口；安全单独成类值得保留 | 高 | 2026-05-22 |
| keon/awesome-physical-ai | awesome list | VLA, world models, robotic foundation models | 分类从 foundations 到 deployment，适合改造成本仓库的路线地图 | 高 | 2026-05-22 |
| robotics-survey/Awesome-Robotics-Foundation-Models | survey companion | foundation models in robotics | 论文综述和仓库互相映射，适合做主题页证据来源 | 高 | 2026-05-22 |
| DravenALG/awesome-vla-wam | awesome list | VLA, WAM, world-action models | 明确区分 VLA 和 WAM，适合跟踪新模型命名和路线分歧 | 高 | 2026-05-22 |
| Noietch/Awesome-Learning-for-Manipulation | paper list | manipulation, VLA, video-action, visuomotor policies | 表格字段紧凑，适合本仓库的论文跟踪表 | 中高 | 2026-05-22 |
| huggingface/lerobot | engineering repo | datasets, policies, hardware interfaces, real robot tooling | 代表开源实操生态，适合跟踪数据格式、训练工具和硬件抽象 | 高 | 2026-05-22 |
| haoranD/Awesome-Embodied-AI | awesome list | embodied AI papers and resources | 早期资源入口，可用于补历史脉络 | 中 | 2026-05-22 |
| MilkClouds/awesome-vla-study | reading guide | structured VLA reading order | 适合补学习路线和精读顺序 | 中 | 2026-05-22 |

## 借鉴后的本仓库分类

综合这些仓库的组织方式，本仓库采用两层结构：

- 稳定知识层：foundations, enabling stack, development path, glossary, roadmaps。
- 动态跟踪层：papers, labs/companies, datasets/benchmarks, open-source, repo watchlist, weekly reviews。

相比纯 awesome list，本仓库额外保留：

- 判断字段：为什么重要、证据强度、局限、会改变什么判断。
- 复查字段：最近复查、状态、后续动作。
- 路线映射：每个材料尽量落到模型、数据、仿真、硬件、评测、部署或发展路径中的一个位置。

## 跟踪 taxonomy

外部仓库中反复出现、值得稳定跟踪的主题：

- Foundations：VLM backbones, visual representations, robot learning basics。
- Architectures：end-to-end VLA, modular VLA, compact VLA, diffusion policy。
- Action Representation：continuous actions, action tokenization, flow matching, world-action models。
- World Models：latent prediction, video/world generation, embodied world models。
- Learning Paradigms：imitation learning, reinforcement learning, offline RL, self-supervised learning。
- Scaling：robot data scaling, cross-embodiment transfer, open-vocabulary generalization。
- Evaluation：manipulation benchmarks, long-horizon tasks, real robot evaluation。
- Deployment：latency, quantization, safety, monitoring, human takeover。
- Ecosystem：datasets, simulators, hardware interfaces, training frameworks。

## 每周使用方式

1. 先看高优先级仓库的 recent updates、commits 或 release。
2. 把新论文、项目或数据集放入 [inbox.md](inbox.md)。
3. 可运行项目同步到 [open-source.md](open-source.md)。
4. 论文同步到 [papers.md](papers.md)。
5. 如果改变路线判断，同步到 [../12-roadmaps/technical-route-map.md](../12-roadmaps/technical-route-map.md) 或 [../12-roadmaps/research-agenda.md](../12-roadmaps/research-agenda.md)。

## 待继续补充

- OpenVLA、Octo、RT-X、RDT、pi0 等具体项目仓库。
- ManiSkill、RLBench、CALVIN、BEHAVIOR、Genesis 等仿真和 benchmark 仓库。
- Humanoid、dexterous manipulation、tactile learning 方向的专门列表。
