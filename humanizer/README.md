# Humanizer: 去除中英文 AI 写作痕迹

一个专门用于识别和去除文档中 AI 生成痕迹的 Claude Code skill,支持中英文文档。

## 功能特点

- ✅ **支持中英文** - 同时处理中文和英文文档
- ✅ **全面检测** - 识别 24+ 种 AI 写作模式
- ✅ **保留意义** - 去除 AI 味的同时保持核心信息
- ✅ **注入灵魂** - 不只是删除问题,还要添加人类个性
- ✅ **两轮优化** - 草稿 + 反 AI 检查 + 最终版本

## 使用方法

### 触发方式

在 Claude Code 中,当你需要去除文档的 AI 味时,可以:

1. **直接请求**:
   ```
   帮我去除这段文字的 AI 味
   ```

2. **指定文件**:
   ```
   去除 article.md 的 AI 味
   ```

3. **批量处理**:
   ```
   去除 docs/ 目录下所有文档的 AI 味
   ```

### 输出格式

Skill 会提供:
1. **草稿重写** - 第一轮修改
2. **AI 特征分析** - 剩余的 AI 痕迹
3. **最终重写** - 第二轮优化后的版本
4. **修改摘要** - 主要改动说明

## 检测的 AI 模式

### 中文特有模式

1. **成语堆砌** - 不言而喻、毋庸置疑、举足轻重等
2. **空洞排比** - 不仅...而且...更...
3. **过度修饰** - 深刻的、显著的、卓越的等
4. **介词堆砌** - 在...背景下、在...情况下等
5. **假大空总结** - 展望未来、前景广阔、任重道远
6. **"有效"泛滥** - 有效地、有力地、切实地等

### 英文通用模式

7. **重要性夸大** - pivotal, testament, crucial, vital
8. **-ing 短语** - highlighting, underscoring, reflecting
9. **宣传语言** - groundbreaking, nestled, breathtaking
10. **模糊归因** - experts say, industry reports
11. **AI 词汇** - Additionally, delve, showcase, landscape
12. **系动词回避** - serves as, stands as (而不是 is)
13. **否定排比** - It's not just X; it's Y
14. **三段式法则** - 强制分成三组
15. **破折号过度** - 过多使用 em dash (—)
16. **聊天痕迹** - I hope this helps, Let me know
17. **知识截止** - as of my last update
18. **谄媚语气** - Great question! You're absolutely right!
19. **填充短语** - In order to, Due to the fact that
20. **过度限定** - could potentially possibly might
21. **空洞结尾** - The future looks bright

## 示例

### 中文示例

**之前 (AI 味重):**
> 在当今这个日新月异的时代,人工智能技术的发展可谓是突飞猛进,不言而喻地成为了推动社会进步的重要力量。该技术不仅显著提升了开发效率,而且有效优化了代码质量,更深刻地改变了软件开发的工作模式。

**之后 (人类味):**
> AI 这两年发展很快。我们公司去年开始用 ChatGPT 写文档,确实快了不少,但质量不稳定。现在的做法是先让 AI 生成初稿,然后人工检查修改。

**主要改动:**
- 删除成语堆砌 (日新月异、突飞猛进、不言而喻)
- 删除排比句式 (不仅...而且...更...)
- 删除空洞修饰 (显著、有效、深刻)
- 添加具体细节 (去年、我们公司)
- 承认问题 (质量不稳定)

### 英文示例

**之前 (AI 味重):**
> AI-assisted coding serves as an enduring testament to the transformative potential of large language models, marking a pivotal moment in the evolution of software development. These groundbreaking tools are reshaping how engineers ideate, iterate, and deliver, underscoring their vital role in modern workflows.

**之后 (人类味):**
> AI coding assistants can make you faster at boring tasks. Not everything. Definitely not architecture. They're great at boilerplate but also great at sounding right while being wrong.

**主要改动:**
- 删除重要性夸大 (testament, pivotal moment, vital role)
- 删除宣传语言 (groundbreaking, transformative)
- 删除系动词回避 (serves as → can make)
- 删除 -ing 短语 (underscoring, reshaping)
- 添加个人观点和具体性

## 资源文件

- `resources/chinese-patterns.md` - 中文 AI 写作模式速查表
- `resources/english-patterns.md` - 英文 AI 写作模式速查表

## 注意事项

### 适用场景

✅ **适合使用:**
- 博客文章、技术文档
- 营销文案、产品描述
- 学术论文、研究报告
- 任何需要"人味"的文字

❌ **不适合使用:**
- 法律文件 (需要精确措辞)
- 代码注释 (可能需要技术术语)
- 已经是人类写的文本 (可能过度修改)

### 最佳实践

1. **先检查再应用** - 查看草稿,确认修改合理
2. **保留专业术语** - 技术文档可能需要某些"AI 词汇"
3. **考虑受众** - 正式文档可能需要保留一些正式表达
4. **人工审核** - 最终版本仍需人工审核

## 原理

基于维基百科的 [Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing) 页面,该页面由 WikiProject AI Cleanup 维护,记录了从数千个 AI 生成文本实例中观察到的模式。

核心洞察:
> LLM 使用统计算法来猜测接下来应该出现什么。结果倾向于适用于最广泛情况的统计上最可能的结果。

中文部分基于对中文 AI 写作特征的观察和总结。

## 版本历史

- **1.0.0** (2026-02-27): 初始版本,支持中英文 AI 写作模式检测和修复

## 贡献

欢迎提交 Issue 或 Pull Request 来改进这个 skill:
- 添加新的 AI 写作模式
- 改进检测算法
- 提供更多示例

## 许可

MIT License - 详见仓库根目录 LICENSE 文件

## 相关资源

- [Wikipedia: Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing)
- [Original Humanizer Skill by @blader](https://github.com/blader/humanizer)
- [Claude Code Documentation](https://docs.anthropic.com/claude/docs/claude-code)
