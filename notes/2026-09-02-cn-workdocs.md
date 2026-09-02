# From Scattered Notes to Decision-Ready Documents

# 从零散材料到可决策文档

## 中文

很多 AI 写出的中文工作材料，问题不是“不正式”，而是“太像正式材料”。

它会自动补齐没有提供的数字，把会上的个人建议写成已形成的决定，把“可以帮忙”写成“明确由某人负责”，再用“持续推进、形成合力、进一步提升”把这些缺口包装起来。文字看上去完整，却比原始速记更不可靠。

这是我做 [CN WorkDocs](https://github.com/zhuyep/cn-workdocs) 的原因。

它不是一个继续扩充文种和模板的“全能写作器”，而是一套证据感知的工作方法：

1. 把来源陈述、权威记录、已核事实、推断、建议和未知分开；
2. 缺失信息标记为 `[待补]`，已有但未核实的陈述标记为 `[待核]`；
3. 把抽象的“加强协同”还原为责任人、动作、时间、交付物和验收条件；
4. 在交付前扮演怀疑者，查找无依据结论、逻辑跳跃和被包装起来的信息缺口。

项目首先支持调研分析、方案计划、工作总结、会议纪要和领导讲话五类文档。我刻意不宣称它能保证法定公文合规，也不把主观写作质量伪装成一个可以完全自动评分的数字。

30 秒安装：

```bash
npx skills add zhuyep/cn-workdocs --skill cn-workdocs -g -a codex -y
```

如果它帮你避免了一次“把未确认内容写成定论”，可以给项目一个 Star。比 Star 更有价值的，是提交一个脱敏后的失败案例，让这套方法在真实材料中变得更可靠。

## English

Many AI-generated workplace documents fail because they look complete while quietly inventing certainty. A suggestion becomes a decision, an offer to help becomes an assigned owner, and a rough estimate becomes a verified fact.

[CN WorkDocs](https://github.com/zhuyep/cn-workdocs) is an open Agent Skill built around the opposite principle: preserve the evidence boundary first, then improve structure and language. It separates supplied statements from verified facts, exposes missing inputs, turns vague actions into executable conditions, and runs an adversarial review before delivery.

It currently focuses on five Chinese workplace-document families: research reports, proposals, work summaries, meeting minutes, and leadership speeches. It does not claim to replace statutory document rules, authoritative templates, or qualified human review.

If it prevents one unsupported claim from reaching a real decision, consider starring the repository. A sanitized failure case is even more useful: it gives the project something concrete to improve and test.
