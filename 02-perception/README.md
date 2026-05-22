# 02 Perception

感知解决的问题是：机器人如何从传感器信号中理解环境。

## 初学者先读

- [visual-perception.md](visual-perception.md)：视觉感知。
- [depth-and-point-cloud.md](depth-and-point-cloud.md)：深度和点云。
- [tactile-and-proprioception.md](tactile-and-proprioception.md)：触觉和本体感知。
- [multimodal-understanding.md](multimodal-understanding.md)：多模态理解。

## 感知输入

- RGB 图像和视频。
- 深度图和点云。
- 触觉、力觉和力矩。
- 机器人本体状态，例如关节角、速度、末端位姿。
- 语言指令和任务上下文。

## 感知输出

- 物体类别、位置和姿态。
- 场景布局和空间关系。
- 可抓取区域、可通行区域、障碍物。
- 任务相关状态，例如“杯子是否已经被抓住”。

## 初学者常见问题

- 视觉识别对了，不代表机器人就能抓对。
- 2D 图像理解不等于 3D 空间理解。
- 感知结果需要服务动作，而不是只服务分类准确率。
