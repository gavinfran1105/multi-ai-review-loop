# multi-ai-review-loop

讓多個 AI（Claude、Codex、Gemini、Grok…）一起開發同一個專案時不打架的協定，做成一個 [Agent Skill](https://agentskills.io)（SKILL.md）。

- **角色固定**：一個寫入者、一個唯讀審查者、只給意見的顧問、只有人能拍板。
- **用檔案交接**：工作單、待審訊息、審查結論、決策紀錄，都有範本。
- **審到通過為止**：審查者要獨立驗證、獨立探測、檢查測試有沒有判別力；**BLOCK 必須附具體合成情境**，說不出情境的不能擋。
- **低優先度事項**用代號（L-1、L-2…）跨回合追蹤，不擋本輪。
- **安全**：審查者唯讀、測試用合成資料、commit／push／刪除只在人明說後做。

這套流程來自實際專案，兩個 AI 之間跑過數百輪審查後整理而成。

## 內容

| 路徑 | 說明 |
|---|---|
| `skills/multi-ai-review-loop/SKILL.md` | 協定本體 |
| `skills/multi-ai-review-loop/templates/工作單.md` | 交給執行者的工作單 |
| `skills/multi-ai-review-loop/templates/待審訊息.md` | 寫入者送審 |
| `skills/multi-ai-review-loop/templates/審查結論.md` | 審查者的結論格式 |
| `skills/multi-ai-review-loop/templates/決策.md` | 人的決策紀錄 |

## 安裝

把 `skills/multi-ai-review-loop/` 複製到：

- Claude Code：`~/.claude/skills/`
- Codex：`~/.agents/skills/`

或：`npx skills add gavinfran1105/multi-ai-review-loop`

兩邊都裝同一份，寫入者和審查者才有共同依據。

## English

A protocol (as an Agent Skill) for running several AI coding agents on one project: one writer, one read-only reviewer, advisors who only advise, and a human who alone decides. Agents hand off through Markdown files (work orders, review requests, review verdicts, decision log). Reviews loop until they pass; a BLOCK must come with a concrete synthetic scenario. Templates are in Traditional Chinese.

## 授權

MIT
