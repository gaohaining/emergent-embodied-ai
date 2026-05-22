# 03 Representation

表征解决的问题是：如何把复杂的真实世界转成模型和控制器能处理的形式。

## 初学者先读

- [state-and-scene.md](state-and-scene.md)：状态、场景和对象表示。
- [action-representation.md](action-representation.md)：动作表示。
- [world-models.md](world-models.md)：世界模型。

## 为什么表征重要

同一个任务可以用不同方式表示：

- 用像素表示环境。
- 用对象和关系表示环境。
- 用 3D 点云或地图表示环境。
- 用连续控制量表示动作。
- 用离散动作 token 表示动作。

表征会直接影响数据效率、泛化能力、控制稳定性和可解释性。
