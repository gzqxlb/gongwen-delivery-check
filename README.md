# gongwen-delivery-check
chinese-official-writing 技能的交付门禁目前需等 WorkBuddy 支持本地插件加载时才能用，因此，目前采用人工等效流程（固化流程到MEMORY.md等）


chinese-official-writing 技能的交付门禁目前需等 WorkBuddy 支持本地插件加载时才能用，因此，目前采用人工等效流程，即成稿后自动跑一次 prose_lint.py 做机械检查，再做"只审不改"的语义复核。（把门禁的价值用人工方式兑现，而且 prose_lint.py 那部分 AI 可以直接嵌进你的写作流程(chinese-official-writing)里，不用你记任何命令。)

门禁 Hook 是宿主（运行框架）的生命周期插件，跟用哪个模型无关。

chinese-official-writing 技能的 host-capabilities.json 里，9 个宿主有 6 种不同的支持状态——Codex 和 CodeBuddy 是完整验证，Kimi Code 只能拦一次 Stop，OpenCode 无头模式直接旁路，OpenClaw 则根本没有 Hook。

启用的是"给 WorkBuddy 这个宿主装上门禁"，装好之后，混元、其他任何模型都受益。​ 这正是"跨模型拉齐质量"的正解。

具体流程：
将“gongwen-gbt9704-skill”技能的描述收窄到纯排版场景（只留"排版成Word/生成docx/套红头/GB-T 9704"之类）。
同时，在“MEMORY.md”等中将“起草用 chinese-official-writing、排版用 gongwenformat-pro、交付质检用 gongwen-delivery-check”三个技能关联起来。即当我调用“chinese-official-writing”写材料的时候，自动启动“gongwenformat-pro + gongwen-delivery-check”技能。

提示： **gongwenformat-pro	目前为按需触发** （只有你要 Word / docx / GB-T 9704 正式文件时才排版）
理由：起草一份纯文本交办的短材料时强行排版会多出无用的 Word 文件。

详见：
1.任务：“模型 与 SKILL 的区别”
2.关联：“中文公文写作 Skill”，https://github.com/gongyu0918-debug/chinese-official-writing-skill
3.关联：“公文排版 Skill ”，https://github.com/mizzlelover/gongwen-gbt9704-skill
