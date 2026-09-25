# embodied-math-theater-skill

面向具身智能运控课程的 **Grok Skill**：用固定的几何对象目录 + 镜头语法，让 AI 把抽象数学画成可核对的空间事件，并与 Part2 课文 Prompt v3 组合使用。

仓库：https://github.com/DaTingLi/embodied-math-theater-skill

## 这个 Skill 解决什么

课程里最容易漂起来的不是仿真器，而是：

- 点 ≠ 自由向量 ≠ 位置向量
- 主动旋转 ≠ 被动换系
- 姿态误差 ≠ 三个欧拉角相减
- 读回关节角再 FK ≠ TCP 实测精度

Skill 把全课的空间对象锁成目录。AI 不得临时发明新图元。每张图只讲一个关系，并用同一时刻的数字验收。

## 目录

```text
SKILL.md                          # 交给 AI 的主规程
catalog/objects.yaml              # 对象机器可读目录
catalog/OBJECTS.md                # 对象说明（人读）
catalog/coverage.md               # 小节 → 对象覆盖
catalog/visual_contract.md        # 颜色、单位、禁止混用
shots/grammar.md                  # 五拍镜头语法
shots/section_map.md              # 每节必拍的对立
prompts/Part2_课程层级设计Prompt_v3.md
prompts/compose.md                # Skill 怎么和 v3 Prompt 拼在一起
examples/
schemas/shot.schema.json
```

## 与 Prompt v3 怎么一起用

1. 先读 `SKILL.md` 和 `catalog/objects.yaml`。
2. 再贴 `prompts/Part2_课程层级设计Prompt_v3.md` 全文，替换花括号变量。
3. 课文仍按 v3 输出两份：语雀课文 + `讲图顺序.md`。
4. 配图只能从目录实例化对象；`图中必须看见` 里的名字必须是目录 ID 或业务别名。
5. 动画脚本先出 scene JSON，再选渲染器。数学在 `compute` 里算，渲染不重算。

详见 `prompts/compose.md`。

## 工具约定

| 层 | 工具 | 作用 |
|---|---|---|
| 计算 | NumPy；3.2 起允许 Pinocchio | R, T, FK, J, SVD, 残差 |
| 剧场 | MuJoCo 无头录制（优先） | 与课程 1.5 / 5.1 对照窗同一套 body/site |
| 对立叙事 | Manim Community（仅 2.7 / 2.9 / 2.17） | 主动/被动、四种表示、左右扰动 |
| 讲义静帧 | PyVista `off_screen=True` | 椭球、摩擦锥、支撑多边形 |
| 右格曲线 | Matplotlib | 残差、奇异值、跟踪 |
| 系统 TF | RViz | 仅 3.5 ROS2 集成 |

禁止把 GeoGebra / Blender GUI / MATLAB 图窗写进 Skill 运行时。

## 用户原始 9 对象是否够

**对 Part2 的 2.1–2.12：几乎够。**  
**对整门课：不够。** 必须补充直线/轴、平面、残差箭、齐次位姿、雅可比列、可操作性椭球、螺旋、力螺旋、接触、摩擦锥、支撑域、CoP、路径/轨迹、TF 节点、SE(2) 底盘、右格数字板。

详见 `catalog/coverage.md`。
