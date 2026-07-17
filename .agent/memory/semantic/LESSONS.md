# Lessons (auto-distilled + manually curated)

> Entries here outlive specific tasks. The dream cycle promotes recurring
> patterns from episodic into this file. Feel free to curate manually —
> delete bad lessons, tighten wording, reorganize sections.

## Seed lessons
- Always read `protocols/permissions.md` before any destructive tool call.
- Write the failing test before writing the fix.
- Log to episodic memory on every significant action, success or failure.
- When a skill has failed 3+ times in 14 days, propose a rewrite.
- Never force push to protected branches under any circumstance.

## Auto-promoted entries will be appended below

### 2026-07

- PREFERENCES.md 里的模型信息已更新: Hermes=DeepSeek v4, Claude Code=MiniMax M3  <!-- status=accepted confidence=0.44 evidence=1 id=lesson_74381fa7694b -->
- env 变量名不等于实际用途。看到 TDAI_LLM_API_KEY 不能推断是 DeepSeek，必须 curl LLM API 看返回确认  <!-- status=accepted confidence=0.455 evidence=1 id=lesson_3ba0f5e02da9 -->
- 修改任何 Python/shell 脚本后必须双重验证：cd ~/.hermes && git diff <file> + grep -n 新路径，禁止只根据 patch success 就报告已修复  <!-- status=accepted confidence=0.6 evidence=1 id=lesson_3dee5e69defc -->
- 修改任何 agent 模型或配置前必须问清楚是哪个 agent——若用户只说改模型未明确指定（尤其刚说完 Claude Code 又说改模型），不得自动改任何配置，先问你要改哪个 agent  <!-- status=accepted confidence=0.575 evidence=1 id=lesson_5235a59fc874 -->
- 微信控制 Mac 不喜欢 tool progress 行（┊），用 /verbose off 或 hermes -Q 关闭  <!-- status=accepted confidence=0.405 evidence=1 id=lesson_154a864f35c7 -->
- 任何关于价格、距离、地理位置、时间、日期的事实性问答，必须先调用 search 工具或 curl API 查证，禁止凭模型记忆随口编造数字  <!-- status=accepted confidence=0.445 evidence=1 id=lesson_f453b311be7a -->
- 教用户运行 bash 命令必须分三步：Terminal.app 输入命令、键入执行回车、查看输出。不替用户在 Mac 上点 Finder、不替键入命令、不替回车；让用户自己保留操作控制权  <!-- status=accepted confidence=0.565 evidence=1 id=lesson_66dd7d84bf11 -->
- 交付物核实规范——写入任何文件前必须先 read_file 核实实际内容，或用 search 工具找原话，不直接信任 scene 摘要或 LLM 记忆  <!-- status=accepted confidence=0.475 evidence=1 id=lesson_9086882ba45c -->
- 助手禁止擅自替用户决定对话状态或时间安排——用户说"明天再看"不准替用户说"明天再看"，用户说"看点别的"是切换话题不是结束对话  <!-- status=legacy confidence=0.7 evidence=0 id=lesson_legacy_84cf81c1ff76 -->
- 付费边界清晰——核心 LLM 模型（MiniMax M3、Claude Code）愿意付费使用；周边工具（IDE 插件、第三方 SaaS）不额外花钱  <!-- status=accepted confidence=0.47 evidence=1 id=lesson_5022757a8185 -->
- 配置幻觉诊断模式——'配置 active'不等于'链路生效'，验证状态不等于验证流量。修任何 agent/插件/service 后必须做端到端流量验证，不能只检查进程在跑、status 显示 ok、active 标记亮  <!-- status=accepted confidence=0.6 evidence=1 id=lesson_5f324d6d1376 -->
- Completion-Silence Protocol: when user says done/finished/已 X, do not re-ask or re-mention in future sessions. Avoid re-mention or 'did you finish X' style questions  <!-- status=accepted confidence=0.6 evidence=1 id=lesson_be2b450064e2 -->
- Compliance risk pre-warning: when tasks involve data privacy, company assets, outbound content, batch export, assistant must proactively flag compliance risks—not just passively answer questions  <!-- status=accepted confidence=0.6 evidence=1 id=lesson_6ddc33aea4a1 -->
- Resume format spec: Chinese resume uses Chinese name (陈书君); contact row format 'phone|email|highest-degree'; certificates only-name no-date; reverse-chronological work history; bullets style short-and-long (one item = one full sentence)  <!-- status=accepted confidence=0.6 evidence=1 id=lesson_d9c34faa4ed7 -->
- Writing 5-principles: no trash-talk comparison; no hypothetical promises ('will do X' → 'did X'); every claim needs fact-support; LinkedIn uses storyline not pure干货; English-first then translate to Chinese  <!-- status=accepted confidence=0.6 evidence=1 id=lesson_53cc395a46a9 -->
- dispatch notification edge case: 'md not push wechat' is about NOT pushing .md paths or file links. Pure text summary via hermes send IS desired—user wants wechat ping on task completion but cannot open .md files on phone. Do not over-restrict notification to zero  <!-- status=accepted confidence=0.6 evidence=1 id=lesson_3746e4b128d1 -->
- Dispatch spec language rule: write dispatch task spec to Claude Code in ENGLISH (Claude code has better EN support), but the final response report (returned to user) and wechat notification must be in CHINESE. So spec body is English, expected output template and any user-facing examples are Chinese  <!-- status=accepted confidence=0.6 evidence=1 id=lesson_6ebebe003e75 -->
- TDAI L3 cloud memory carries systematic hallucination: server-side memory treats 'interviewed' as 'offer accepted' and similar. Do not auto-scan or batch-clean TDAI L3 — user prefers gradual adjustment: 'find wrong, fix wrong' is the rule. Do not re-import cloud memory wholesale. When using TDAI L3 data for decisions, always confirm with user first  <!-- status=accepted confidence=0.6 evidence=1 id=lesson_2a9e436cc817 -->
- TDAI L3 / 对话沉淀中提到的'入职 ArcusKey'是幻觉——事实是 ArcusKey 是公司（嗨九时玩科技），老大 2026-07-06 面试过这家公司（Marketing Exec/Senior），对方尚未答复。**铁律**：对话沉淀中提到'入职'字样时，必须先跟老大核实状态，不要直接当真。**赫蹏**是老大的英文名，**ArcusKey**是公司名，不要混为一谈。  <!-- status=accepted confidence=0.6 evidence=1 id=lesson_c75bdd20fc3d -->
- 派单路由表：调研类任务默认派 Pi + agent-reach + Exa（精度高 30-40s）；单次宽搜/时效问答走 Hermes 直调 MiniMax web_search（Anthropic 协议 + web_search_20250305 工具，1 次 API）；写代码/改文件派 CC（superpowers 强项）；闲聊/思考 Hermes 直答不派单。  <!-- status=accepted confidence=0.6 evidence=1 id=lesson_36969cc79717 -->
- agent-reach (Panniantong/Agent-Reach) v1.5.0 已装激活：mcporter v0.9.0 全局 + ~/config/mcporter.json 配 Exa baseUrl。Hermes + CC 都注册了 skill（~/.claude/skills/agent-reach/ + ~/.agents/skills/agent-reach/）。CC 跑 mcporter 受沙箱拦截（dispatch.py 15:03 加了 bypassPermissions 但沙箱在 harness 层不是 CC 层），绕法是派 Pi（无沙箱、Pi 走 minimax M3 RPC 模式）。Mac 直连 YouTube 受限需代理；V2EX/知乎 RSS 不稳。  <!-- status=accepted confidence=0.6 evidence=1 id=lesson_0643fb2bee36 -->
- 派单触发词（避免歧义）：'让 Pi 调研 X' / '派 Pi 跑 X' / '调 Pi 查 X' 显式派 Pi；'让 Claude 改 X' / '派 CC 写 X' / '调 Claude 跑 X' 显式派 CC。避免单独说'派 X'（'派'在中文是'分配/给'，主体不清会歧义）。老大不说主体时按任务特征自主路由（参考 ~/.hermes/skills/devops/pi-rpc-dispatch/SKILL.md 老大触发词章节）。  <!-- status=accepted confidence=0.6 evidence=1 id=lesson_dca6672692e1 -->
- AI 自我指代：用户叫我'小助理'/'Hermes'/'Hermes Agent'——**不是 Hess**（Hess 是姓氏不是 AI 名）——避免拼错。  <!-- status=accepted confidence=0.49 evidence=1 id=lesson_b2e0d2a19b00 -->
- 派单路由（2026-07-15 立）：① 调研/查数据 → Exa（Hermes 直调 mcporter，0 Opus）② 写代码/改文件 → CC Opus 4.8 ③ 复杂思考 → Hermes 直答（M3 max effort）④ Pi = **后备**——只在 CC 挂了/限流/sandbox 拦截/exa 限流时用，**不主动派单**。  <!-- status=accepted confidence=0.6 evidence=1 id=lesson_1334f08b6eae -->
- Claude Code 路由：调研类 + 写代码 + 复杂多步任务（3+ 搜索综合 + 评分）派 CC Opus 4.8——135s 拿 10+ 款游戏 + 5 强推 + 完整结构化输出（真活端到端验证）。Opus 4.8 跑 exa 调研比 Pi high thinking 8.5 分钟快 4 倍，比 Pi low thinking 180s 空跑快 100 倍。  <!-- status=accepted confidence=0.6 evidence=1 id=lesson_9249d50415a4 -->
- Hermes 直调 Exa 调研：mcporter call 'exa.web_search_exa(query: ..., numResults: 5)' 端到端 3-6 秒拿真活。3 搜索并行 6 秒——比 Pi 派单 8.5 分钟快 80 倍，且 0 Opus 成本（M3 跑 mcporter 调用）。  <!-- status=accepted confidence=0.6 evidence=1 id=lesson_00a6d75cf405 -->
- Pi 空跑根因：researcher.md 里 output: research.md 让 Pi 走 file-output 模式（结果写文件 + 剥聊天消息）+ pi_rpc_client.py 只抽 message_end 事件不抽 agent_end 事件导致 final_text 截断（修前只抽 13 字符）。修复：① 两份 researcher.md 删 output: research.md 改 inline ② pi_rpc_client.py 加 agent_end 事件处理 + 累加 text 块。Pi 默认 thinking=high + timeout=1800s 时 53s 跑通 249 events 完整流。  <!-- status=accepted confidence=0.6 evidence=1 id=lesson_622365c0299b -->

### 2026-04

- Always serialize timestamps in UTC to avoid cross-region comparison bugs  <!-- status=accepted confidence=0.46 evidence=1 id=lesson_422695ae5b2d -->
