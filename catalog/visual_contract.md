# 视觉合同

## 颜色
- 世界/任何 FRAME：x 红 y 绿 z 蓝
- POINT / 章面中心：白或亮黄，比轴粗、比轴前
- FREE_VECTOR 默认青
- DISPLACEMENT 默认同一青，但两端有点
- RESIDUAL 品红
- 真实运动实线，预测虚线
- WRENCH 橙
- VEL_ARROW 青，不与 WRENCH 同色
- CONTACT 法向白+橙力
- TASK_MARKER 目标轴可略透明，但仍是红绿蓝

## 单位与数字
- 数据卡显示值用于正文手算
- 脚本用未舍入值
- SLATE 写单位；视角变化不得改数字
- DISPLAY_STRETCH 必须在图注声明「拉长的是画面」

## 一图一关系
禁止一张图同时：
- 主动转物体 + 被动转轴
- 位置任务 + 姿态任务的两套残差（拆两张）
- 路径几何 + 时间参数化（PATH 与 TRAJECTORY 拆开）

## 字幕与画面
图注出现的每一个名词 ∈ must_see ⊆ objects.yaml。
对不上就改图或改图注。

## 世界轴
相机只改变观察，不改变 `{W}`。不得把相机运动写成盖章动作。
