# humanizer-lanbo-skill

一个专门用于中文文案去 AI 味的 Agent Skill。

适用场景：

- 公众号短文去 AI 味
- 小红书文案去 AI 味
- 短视频口播去 AI 味
- 朋友圈文案去 AI 味
- 私域营销文案去 AI 味
- ChatGPT 生成中文文案后的人话改写

## 文件结构

```text
humanizer-lanbo-skill/
├── SKILL.md                         # 核心 skill 文件，Claude/Codex 都可识别
├── AGENTS.md                        # Codex 项目级兜底说明
├── README.md                        # 使用说明
├── references/
│   ├── ai_flavor_rules.md           # AI 味现象级规则库
│   ├── final_review_checklist.md    # 最终审查清单
│   └── examples.md                  # 示例库
├── scripts/                         # 预留，可以后加自动检查脚本
└── assets/                          # 预留，可以后加模板或样本文案
```

## Claude Code 使用方式

把整个 `humanizer-lanbo-skill` 文件夹放到 Claude Code 可读取的 skills 目录或当前项目中。

使用时可以直接说：

```text
使用 humanizer-lanbo-skill，帮我把下面这篇文案去 AI 味，只输出正文。
```

## Codex 使用方式

Codex 支持以 `SKILL.md` 为核心的 skill 文件夹，也支持 `AGENTS.md` 作为项目级指导。

用法一：把整个文件夹放到项目里，让 Codex 读取。

用法二：把 `AGENTS.md` 放到项目根目录，作为常驻规则；同时保留 `SKILL.md` 和 `references/`，需要时让 Codex 显式读取。

示例：

```text
读取 humanizer-lanbo-skill/SKILL.md，按这个 skill 帮我改下面这篇文案，只输出改完后的正文。
```

## 使用注意

- 这个 skill 默认只输出改完后的正文。
- 如果想看它为什么这么改，需要额外说“解释你改了哪里”。
- 这个 skill 的核心不是替换词，而是识别 AI 味现象，并逐句做母语感审查。
