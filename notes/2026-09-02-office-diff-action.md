# Why Office Documents Need Reviewable Diffs

> 中文在前，English follows.

## 中文：从“附件变了”到“变化可审查”

很多工程和管理工作并不发生在代码里，而是沉淀在 Word 报告、方案和 PowerPoint 汇报中。文件一旦进入 Git，版本是保存下来了，但审查体验仍然很差：评审者通常只知道“这个二进制文件发生了变化”，却看不到哪一页、哪一段、哪张图被改动。

这正是 [Office Diff Action](https://github.com/zhuyep/office-diff-action) 想解决的问题：把 Office 文件的变化转成可以进入 Pull Request 工作流的审查证据。

### 我把问题拆成了三层

1. **文字层**：提取段落、表格和幻灯片文本，回答“内容改了什么”。
2. **视觉层**：渲染前后版本并生成对比图，回答“版式和页面看起来怎么变了”。
3. **结构层**：记录页数、幻灯片数和关键对象变化，帮助自动化流程做判断。

单独依靠任何一层都不够。文字 Diff 看不出版式错位，截图看不清细小措辞变化，结构统计也不能代替人工审查。更可靠的方式，是把它们并列呈现，让评审者自己追溯证据。

### 为什么先做 GitHub Action

这个问题最自然的入口不是另造一套文档平台，而是接入团队已经在使用的 Pull Request：文件提交后自动运行，生成报告和制品，审查者不需要安装额外客户端。

首个版本刻意保持边界：支持 DOCX 和 PPTX，输出静态报告，不承诺“理解”文档含义，也不替代人工批准。把边界说清楚，比制造一个无所不能的 AI 叙事更重要。

### 做开源项目得到的三个提醒

- README 不是项目完成后的包装，而是产品入口。
- 示例、错误信息和默认配置决定了用户能否在十分钟内获得第一次成功。
- Star 是结果指标；真正能积累信任的是持续可验证的发布、真实问题和及时回应。

目前项目发布到 `v0.1.1`。接下来会优先围绕真实 PR 使用体验完善报告呈现、字体替代提示和可复现示例，而不是无边界扩张功能。

---

## English: from “the attachment changed” to reviewable evidence

A large amount of engineering and management work lives outside source code—in Word reports, specifications, and PowerPoint decks. Git can store those versions, but reviewers still receive a poor signal: a binary file changed, with little indication of which page, paragraph, table, or visual layout was affected.

[Office Diff Action](https://github.com/zhuyep/office-diff-action) turns those changes into evidence that fits a pull-request review.

### Three complementary layers

1. **Text** extracts paragraphs, tables, and slide text to show what the content says differently.
2. **Visuals** render before-and-after pages to reveal layout and appearance changes.
3. **Structure** records page, slide, and object-level changes for automation and triage.

No single layer is sufficient. A text diff misses broken layouts; screenshots hide subtle wording changes; structural counts cannot replace human review. The useful product is the combination, with evidence that remains inspectable.

### Why start with a GitHub Action

The natural integration point is the pull request teams already use. A document change triggers the workflow, produces a report and artifacts, and asks reviewers to adopt no new desktop tool.

The first release intentionally keeps a narrow contract: DOCX and PPTX input, static review evidence, and no claim that automation understands or approves the document. Clear boundaries are more trustworthy than an oversized AI story.

### Three open-source lessons

- The README is part of the product, not packaging added after the work is done.
- Examples, error messages, and defaults determine whether a user reaches first success in ten minutes.
- Stars are a lagging indicator; trust comes from reproducible releases, real issues, and responsive maintenance.

The project is currently at `v0.1.1`. Near-term work will focus on real pull-request ergonomics, font-substitution visibility, and reproducible examples instead of expanding the feature surface indiscriminately.

