# 阅读顺序

写 Part2 小节时按这个顺序加载，不要只丢一个文件给模型。

1. `SKILL.md` — 总合同
2. `catalog/objects.yaml` — 合法对象 ID
3. `catalog/symbol_binding.yaml` — 锁定中文名与默认符号
4. `catalog/bindings.yaml` — SO101 盖章实例名（G, t_S, x_T…）
5. `catalog/formula_bind.md` — 公式模板与必须看见的对象
6. `catalog/encoding.md` — UTF-8 / 文件名 / 字体
7. `shots/accept.md` — 图是否过关
8. `prompts/part2_prompt_v4.md` — 课文结构（ASCII 名，避免乱码）

输出顺序：`shot.yaml` → `lesson_yuque_v1.md` → `---` → `shot_order.md`

历史文件：`prompts/Part2_课程层级设计Prompt_v3.md`、`v3.1.md`。新写用 v4。
