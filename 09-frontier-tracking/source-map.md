# Source Map

这个页面定义外部材料的收集和归档规则。目标是帮助初学者避免被信息流带跑，而是把材料放回具身智能的技术环节里理解。

## 信息源分工

| 来源类型 | 适合发现什么 | 风险 | 处理方式 |
| --- | --- | --- | --- |
| 代码与项目页面 | 开源项目、代码实现、数据工具、工程接口 | 热度不等于质量，说明文档可能过期 | 记录可运行性、活跃度、许可和真实机器人接口 |
| 社区讨论 | 新论文讨论、作者观点、demo、实验室动态 | 信息碎片化，容易只展示成功样本 | 只作为线索，回到论文、项目页或代码验证 |
| 中文长文和问答 | 中文解释、产业观察、学习路径、概念科普 | 观点混杂，引用链可能不清楚 | 提取问题和解释方式，事实要二次确认 |
| 搜索入口 | 官方页面、论文、博客、课程、机构动态 | 噪声高，排序不等于可信度 | 优先打开官方、论文、代码、机构页面 |
| 论文与引用库 | 论文原文、引用关系、相关工作 | 新论文未必可靠 | 放入 papers，再决定是否精读 |
| 官方发布 | 产品、模型、数据集、benchmark、组织动态 | 可能偏宣传 | 对照论文、代码、评测或第三方复现 |

## 收集流程

1. 发现材料后，先放入 [inbox.md](inbox.md)。
2. 用 [templates/source-item.md](templates/source-item.md) 记录来源、类型、为什么重要。
3. 如果是代码或项目，同步到 [open-source.md](open-source.md)。
4. 如果是论文，同步到 [papers.md](papers.md)。
5. 如果是数据集或 benchmark，同步到 [datasets-and-benchmarks.md](datasets-and-benchmarks.md)。
6. 如果材料改变技术判断，同步到对应技术环节目录或 [../12-roadmaps/technical-route-map.md](../12-roadmaps/technical-route-map.md)。

## 初学者判断清单

- 这是事实、观点、宣传，还是 demo？
- 有没有论文、代码、数据或实机评测支撑？
- 它解决的是哪个环节：感知、表征、数据、策略、规划控制、仿真评测、硬件部署？
- 它的任务是在仿真中、实验室中，还是接近真实部署？
- 它的失败模式有没有公开？
- 这条信息 3 个月后是否可能过期？

## 推荐搜索关键词

- embodied AI survey
- robotics foundation model
- vision language action model
- robot learning dataset
- robot manipulation benchmark
- sim2real robotics
- diffusion policy robotics
- world model robotics
- humanoid robot learning
- robot learning tutorial
- VLA RT-X Octo pi0
