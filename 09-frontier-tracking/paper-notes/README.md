# 论文精读笔记

这个目录只放值得精读、会被反复引用的论文笔记。

不要给每篇进入 [../papers.md](../papers.md) 的论文都创建单独文件。一般论文只需要在 `papers.md` 中保留一行索引；当一篇论文满足下面条件之一时，再创建独立笔记：

- 它是某条技术路线的代表作。
- 它会被多个主题页、路线图或案例研究引用。
- 它改变了对数据、模型、评测或部署路线的判断。
- 一行摘要无法承载它的方法、证据、局限和开放问题。

## 命名

使用 `年份-论文短名.md`，全部小写 kebab-case。

示例：

- `2024-openvla.md`
- `2023-diffusion-policy.md`
- `2023-voxposer.md`

## 推荐结构

参考 [../../99-templates-and-notes/templates/paper-note.md](../../99-templates-and-notes/templates/paper-note.md)，但不需要机械填满每一项。优先写清楚：

- 这篇论文属于哪条技术链路。
- 它解决了什么问题。
- 方法的关键接口是什么。
- 证据来自仿真、真实机器人、benchmark、代码、数据集还是 demo。
- 它的局限和后续追问是什么。

## 当前精读入口

| 论文 | 方向 | 笔记 |
| --- | --- | --- |
| OpenVLA | VLA / 开源模型 | [2024-openvla.md](2024-openvla.md) |
| Diffusion Policy | 动作生成 | [2023-diffusion-policy.md](2023-diffusion-policy.md) |
| VoxPoser | LLM + 3D 操作 | [2023-voxposer.md](2023-voxposer.md) |
| FoundationPose | 感知 / 位姿估计 | [2024-foundationpose.md](2024-foundationpose.md) |
