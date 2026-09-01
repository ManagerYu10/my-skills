# my-skills

个人 Agent Skill 仓库，沉淀反复用得上的写作与协作技能。每个技能是一个自包含目录，
放 `SKILL.md`（指令与元数据）加可选的 `references/`（按需加载的长参考）。

同一份 `SKILL.md` 同时供 Claude Code 和 Codex 使用；`agents/openai.yaml` 只是 Codex 侧的
展示与调用配置，不影响技能内容本身。

## 技能索引

| # | 技能 | 做什么 | 什么时候触发 | 参考文件 |
| --- | --- | --- | --- | --- |
| 1 | [weekly-review-authoring](skills/weekly-review-authoring/SKILL.md) | 先建证据清单再写周报，把周报写成职业证据而不是活动流水账 | 写周报、整理本周进展、Review 周报草稿 | [写作标准](skills/weekly-review-authoring/references/weekly-review-standard.md) |
| 2 | [architecture-plan-authoring](skills/architecture-plan-authoring/SKILL.md) | 按讲述时长冻结正文预算，先串文字主线再用图压缩表达 | 架构规划、技术规划、方案汇报、路线提案 | [交付物模式](skills/architecture-plan-authoring/references/deliverable-modes.md)、[审查量表](skills/architecture-plan-authoring/references/review-rubric.md) |

## 两个技能的分工

都是写作技能，但解决的问题不同，不要混用：

- **周报**面向自己和主管。核心是结果、证据、影响和支援请求，
  验收标准是「离职后这条能不能不重新考古就写进简历」。
- **架构规划**面向听众。核心是一条能被口头复述的因果链，
  正文长度由有效讲述时长反推，验收标准是「讲述者能不能脱稿复述主线并回答质疑」。

两者共享一条纪律：**不把未验证的判断写成事实**。周报里体现为区分已验证事实、
本人判断和待验证假设；架构规划里体现为「零上下文读者测试」——
隐藏聊天记录和作者解释，只让审阅者读当前正文。

## 安装

技能目录直接软链或复制到 Agent 的技能目录即可，不需要构建步骤。

```bash
git clone https://github.com/ManagerYu10/my-skills.git
cd my-skills

# Claude Code（用户级）
ln -s "$PWD/skills/weekly-review-authoring"     ~/.claude/skills/
ln -s "$PWD/skills/architecture-plan-authoring" ~/.claude/skills/

# Codex
ln -s "$PWD/skills/weekly-review-authoring"     ~/.codex/skills/
ln -s "$PWD/skills/architecture-plan-authoring" ~/.codex/skills/
```

只装某一个就只链那一行。项目级安装把链接放进 `<repo>/.claude/skills/` 即可。

## 来源与边界

- 两个技能均由本人编写。公开前做过脱敏：去掉了真实姓名、本机绝对路径和内部项目代号。
- 周报的六模块字段名和架构规划的三色配色**保留为默认模板**，
  都可以整体替换成你所在组织的字段和品牌色；替换字段不影响其余写作标准。
- 方法论部分未做删减。
- 这些技能是按本人的工作场景打磨的，不是通用最佳实践。直接套用前先看它假设了什么。

## License

[MIT](LICENSE)
