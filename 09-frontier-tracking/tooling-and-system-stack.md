# 工具链与系统栈

这一页把从社区索引仓库中筛出来、适合长期维护的开源工具与系统栈集中放在一起。它们通常不是“某个具身模型”的论文主角，但在真实项目里极高频出现，决定系统能否跑通、对齐、复现和迭代。

定位：
- 不追求收全。
- 只记录对具身智能工程闭环有明显价值的工具。
- 优先放官方项目页、官方仓库或论文页。

---

## 3D 感知与几何

| 工具 | 类型 | 解决什么问题 | 为什么值得跟踪 | 链接 |
| --- | --- | --- | --- | --- |
| Open3D | 3D 数据处理库 | 点云、网格、配准、可视化 | 具身项目里最常见的 3D 工程底座之一，适合原型和数据处理 | [GitHub](https://github.com/isl-org/open3d) |
| PCL | 点云库 | 点云滤波、分割、配准、几何处理 | 历史悠久，很多 ROS/机器人系统仍依赖它 | [Project](https://pointclouds.org/) |
| TEASER++ | 鲁棒配准 | 带外点的 3D 配准 | 在噪声大、对应点不干净时比传统 ICP 更稳 | [GitHub](https://github.com/MIT-SPARK/TEASER-plusplus) |
| FoundationPose | 6D 位姿估计 | 从 RGB 或 RGB-D 估计物体姿态 | 适合把“看到物体”接到“可抓取/可操作” | [Project](https://nvlabs.github.io/FoundationPose/) |
| Depth Anything | 深度估计 | 单目深度预测 | 低门槛补足几何先验，适合快速验证感知链路 | [Project](https://depth-anything.github.io/) |

## 标定、检测与感知拼装

| 工具 | 类型 | 解决什么问题 | 为什么值得跟踪 | 链接 |
| --- | --- | --- | --- | --- |
| EasyHeC | 手眼标定 | 自动 hand-eye calibration | 很适合真实机械臂项目起步时建立相机坐标系到机器人坐标系的映射 | [Project](https://ootts.github.io/easyhec/) |
| AprilTag | 视觉标记 | 精准定位与外参辅助 | 标定、抓取、相机定位里都很常见 | [GitHub](https://github.com/AprilRobotics/apriltag) |
| ArUco | 视觉标记 | 快速 fiducial marker 检测 | OpenCV 生态友好，工程上很顺手 | [OpenCV Docs](https://docs.opencv.org/4.x/d5/dae/tutorial_aruco_detection.html) |
| Grounding DINO | 开放词表检测 | 文本条件目标检测 | 开放世界场景里很适合做物体候选发现 | [GitHub](https://github.com/IDEA-Research/GroundingDINO) |
| Grounded-SAM | 检测+分割组合 | 文本找到对象再做精分割 | 非常适合快速搭“语言指令 -> 物体 mask”管线 | [GitHub](https://github.com/IDEA-Research/Grounded-Segment-Anything) |

## 机器人中间件与规划执行

| 工具 | 类型 | 解决什么问题 | 为什么值得跟踪 | 链接 |
| --- | --- | --- | --- | --- |
| ROS 2 | 机器人中间件 | 节点通信、驱动封装、系统集成 | 真实机器人系统几乎绕不开的工程底座 | [Project](https://www.ros.org/) |
| MoveIt 2 | 运动规划与执行框架 | 机械臂运动规划、碰撞检测、任务执行 | 连接感知、逆解、规划和执行的标准工程栈 | [GitHub](https://github.com/moveit/moveit2) |
| cuRobo | GPU 机器人运动生成 | 快速运动规划、IK、轨迹优化 | 对低延迟和大规模采样规划很有吸引力 | [Project](https://curobo.org/) |
| Nav2 | ROS 2 导航栈 | 地图、定位、路径规划与导航执行 | 如果后面扩展移动操作或导航，这会变成关键基础设施 | [Project](https://nav2.org/) |

## 仿真、训练与基准平台

| 工具 | 类型 | 解决什么问题 | 为什么值得跟踪 | 链接 |
| --- | --- | --- | --- | --- |
| SAPIEN | 仿真平台 | 操作任务仿真、资产与物理交互 | 操作方向的重要基础设施，RoboTwin 2.0 建在它之上 | [Project](https://sapien.ucsd.edu/) |
| Isaac Lab | 仿真训练框架 | 机器人强化学习、导航、操作实验 | 在导航、人形、sim2real 训练里影响力很大 | [Project](https://isaac-sim.github.io/IsaacLab/) |
| Genesis | 通用物理引擎/仿真平台 | 大规模并行物理模拟 | 近年热度高，值得持续看其真实机器人适配能力 | [GitHub](https://github.com/Genesis-Embodied-AI/Genesis) |
| MuJoCo Playground | 教学与实验平台 | 快速试跑控制/强化学习任务 | 适合轻量验证控制和策略想法 | [Project](https://playground.mujoco.org/) |
| legged_gym | 腿足机器人训练框架 | 四足/腿足 locomotion RL | 如果后面补人形和腿足路线，这是高频入口 | [GitHub](https://github.com/leggedrobotics/legged_gym) |
| RoboTwin 2.0 | 仿真+数据+benchmark | 双臂任务的数据合成、训练与评测 | 适合新读者快速走通“数据-训练-评测”生命周期 | [Project](https://robotwin-platform.github.io/) |

## 值得带走的判断

- 很多系统成败不在“选哪个 VLA”，而在 3D 感知、标定、规划执行和仿真工具链是否稳定。
- Open3D、ROS 2、MoveIt 2、SAPIEN、Isaac Lab 这类项目不一定最时髦，但最可能成为长期复现基础。
- Grounding DINO、Grounded-SAM、FoundationPose、Depth Anything 这一类基础模型，更适合被理解成“感知积木”，而不是完整具身系统。
- RoboTwin 2.0 这类平台的价值，在于把仿真、数据、策略和 benchmark 串成闭环，很适合补初学者的工程直觉。

## 后续可迁移方向

1. 把 Open3D / MoveIt 2 / cuRobo / Nav2 的稳定知识迁移到 `06-planning-and-control/` 和 `08-hardware-and-deployment/`。
2. 把 Grounding DINO / Grounded-SAM / FoundationPose / Depth Anything 的稳定知识迁移到 `02-perception/`。
3. 把 SAPIEN / Isaac Lab / Genesis / RoboTwin 2.0 的比较迁移到 `07-simulation-and-evaluation/`。
