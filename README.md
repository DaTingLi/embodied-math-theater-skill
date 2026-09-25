# embodied-math-theater-skill

具身运控课 Part2 数学剧场 Skill v1.1 + Prompt v4。

仓库：https://github.com/DaTingLi/embodied-math-theater-skill

## 这包解决什么

- 点、自由向量、位置向量、坐标系、刚体、主动旋转、被动换系不再每节临时发明。
- **每个画面对象必须绑定公式符号和锁定中文名**。公式有的，画面必须有；画面有的，课文必须用同一中文串。
- 中文全链路 UTF-8 无 BOM，媒体文件名 ASCII，避免乱码。
- 与 Prompt v4 组合：v4 管课文结构，本 Skill 管对象、符号、镜头。

## 写 Part2 必用

1. `SKILL.md` + `catalog/`
2. `prompts/Part2_课程层级设计Prompt_v4.md`

v3 保留作历史。新写 2.0-2.19 用 v4。

读取顺序见 `INDEX.md`。

## 最短用法

1. 读 `SKILL.md`、`catalog/objects.yaml`、`catalog/symbol_binding.yaml`。
2. 读 Prompt v4，填花括号变量。
3. 先输出 `shot.yaml`（对象 ID + zh + symbol + formula），再输出课文与讲图顺序。
4. 公式符号必须出现在 bindings；找不到就停。

## 本地检查

```bash
python scripts/check_encoding.py
python scripts/validate_shot.py examples/2.08_point_reframe.yaml
```

## 许可

MIT。
