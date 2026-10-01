# 通用世界观正则导入文件

文件：`UniversalCharacterSystem_Universal_Import.json`

这是 SillyTavern 风格的正则替换导入文件，负责“显示层”，不是世界书或 MVU 引擎本身。导入后请按以下顺序测试：

1. 导入 JSON 文件。
2. 先只启用「通用世界观 · 开场面板」。
3. 在聊天中发送：

```text
<world-opening>
title:测试角色
subtitle:通用世界观测试
status:平静
relationship:初识
quote:你好，欢迎回来。
scene:角色正在等待回应。
</world-opening>
```

4. 能显示面板后，再启用「通用世界观 · 回复面板」「完整状态面板」「角色档案」。
5. 隐藏系统控制标签的两条规则最后启用；如果你需要看到调试信息，可以暂时关闭它们。

## 可用标签

- `<world-opening>...</world-opening>`：开场面板
- `<world-reply>...</world-reply>`：回复面板
- `<world-status>...</world-status>`：数值、状态、系统信息
- `<world-profile>...</world-profile>`：角色档案

## 状态字段示例

```text
<world-status>
title:当前世界状态
affection:78%
trust:64%
obedience:42%
emotion:平静（62）
desire:36%（兴奋）
purity:52%
depravity:18%
status:疲惫 LV12 | 焦虑 LV8
development_detail:胸部 20% | 嘴唇 12%
sensitive_detail:耳朵 35（触觉型） | 手部 22（记忆型）
hypnosis_status:关闭
gacha_status:关闭
event:无
npc:无
special_day:普通日
</world-status>
```

## 重要限制

- 正则替换只负责查找、隐藏和渲染；它不会自动计算数值、触发事件、运行抽卡或保存变量。
- 数值、事件、NPC、抽卡和其他世界观规则必须由角色卡提示词、世界书或 MVU 变量系统驱动。
- 如果你的客户端把 HTML 当普通文字显示，请关闭该客户端的 Markdown/HTML 限制，或改用客户端支持的展示方式。
- 所有涉及亲密、欲望、催眠或身体开发的角色必须明确设定为成年人；不得将未成年人用于性化、强迫或露骨内容。

## 字段解析规则

每行使用第一个英文冒号分隔：`字段:内容`。多值字段使用竖线：`状态A|状态B|状态C`。字段名不区分大小写，但建议使用示例中的小写字段名。
