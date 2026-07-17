# LESSONS — 蒸馏过的教训
> 渲染自 `lessons.jsonl`。每个 lesson 是被 agent 多次重复犯过的同类型错误，新会话会自动 recall 命中。
---

## lesson_8991e978fc80

**规则**：AI 通道能力事实核查：纠正过的错误记忆必须立即写入长期 lesson，不能反复犯同一错。代表案例：(1) AI 自我指代 = 小助理/Hermes/Hermes Agent，不是 Hess；(2) 微信通道一直支持文件发送（用 [media attachment] / MEDIA: 路径），不是只能发文字；(3) deepseek key 已删除不要凭印象以为还在用；(4) 服务器路径是 ubuntu@124.223.210.151（腾讯云 CVM，SSH key 已免密登录）

**理由**：今天对话中重复犯了：(2) '微信不能发文件' 错误；(3) 'deepseek 还在消耗' 推断错误。两个都是凭印象 / 凭之前错误记忆作答，没核 PREFERENCES / CLAUDE.md / 配置文件。教训：用户纠正过的错误记忆，必须立刻 teach 到 LESSONS.md 并写进 PREFERENCES 边界体系，下次对话 recall 时必须命中。

_confidence=0.6 accepted=2026-07-17_

---

## lesson_622365c0299b

**规则**：Pi 空跑根因：researcher.md 里 output: research.md 让 Pi 走 file-output 模式（结果写文件 + 剥聊天消息）+ pi_rpc_client.py 只抽 message_end 事件不抽 agent_end 事件导致 final_text 截断（修前只抽 13 字符）。修复：① 两份 researcher.md 删 output: research.md 改 inline ② pi_rpc_client.py 加 agent_end 事件处理 + 累加 text 块。Pi 默认 thinking=high + timeout=1800s 时 53s 跑通 249 events 完整流。

**理由**：2026-07-15 端到端真活：CC Opus 4.8 花 30 美元额度修 Pi 抽 final_text 的 bug——加 agent_end 事件 + text 累加。修后 Pi high thinking + 1800s timeout 53s 跑通 4 工具 + 完整 final_text。教训：Pi 复杂任务卡 writing final text 不是 Pi 模型问题，是派单客户端抽 final_text 协议没适配 agent_end 事件——**修客户端比修 Pi 本身更划算**。

_confidence=0.6 accepted=2026-07-15_

---

## lesson_00a6d75cf405

**规则**：Hermes 直调 Exa 调研：mcporter call 'exa.web_search_exa(query: ..., numResults: 5)' 端到端 3-6 秒拿真活。3 搜索并行 6 秒——比 Pi 派单 8.5 分钟快 80 倍，且 0 Opus 成本（M3 跑 mcporter 调用）。

**理由**：2026-07-15 端到端真活：用户问'exa 怎么用'——直接 mcporter call 3 条搜索 6 秒拿真活（Cozy Grove Camp Spirit + 星砂岛 + 多款 cosy demo）——零 Opus 成本——纯 M3。教训：调研类任务优先用 Hermes 直调 Exa，而不是派 Pi/CC——Pi 卡 + CC 贵。Exa + M3 组合是真活主力。

_confidence=0.6 accepted=2026-07-15_

---

## lesson_9249d50415a4

**规则**：Claude Code 路由：调研类 + 写代码 + 复杂多步任务（3+ 搜索综合 + 评分）派 CC Opus 4.8——135s 拿 10+ 款游戏 + 5 强推 + 完整结构化输出（真活端到端验证）。Opus 4.8 跑 exa 调研比 Pi high thinking 8.5 分钟快 4 倍，比 Pi low thinking 180s 空跑快 100 倍。

**理由**：2026-07-15 端到端真活：派 CC Opus 4.8 跑'找近期独立游戏 demo'任务——135s 跑通 + 10 款游戏 + 5 强推 + 完整结构化。教训：复杂调研任务用 CC Opus 4.8 而非 Pi——Pi 跑复杂任务卡 writing final text（Pi 0.80.6 bug）——CC 135s vs Pi 8.5 分钟。

_confidence=0.6 accepted=2026-07-15_

---

## lesson_1334f08b6eae

**规则**：派单路由（2026-07-15 立）：① 调研/查数据 → Exa（Hermes 直调 mcporter，0 Opus）② 写代码/改文件 → CC Opus 4.8 ③ 复杂思考 → Hermes 直答（M3 max effort）④ Pi = **后备**——只在 CC 挂了/限流/sandbox 拦截/exa 限流时用，**不主动派单**。

**理由**：2026-07-15 端到端真活验证：用户明确'Pi 是后备'——理由是 Pi 跑复杂任务（high/max thinking + 3 条 exa）会卡 5-8 分钟甚至 300s 空跑——而 Hermes 直 curl Exa 6 秒拿 3 搜索真活。教训：派单路由要按'端到端真活'测试排序，不是按模型'理论能力'排序。Exa + M3 组合快 30x 且零 Opus 成本。

_confidence=0.6 accepted=2026-07-15_

---

## lesson_b2e0d2a19b00

**规则**：AI 自我指代：用户叫我'小助理'/'Hermes'/'Hermes Agent'——**不是 Hess**（Hess 是姓氏不是 AI 名）——避免拼错。

**理由**：2026-07-15 端到端真活：用户在对话中明确指出'我从来没叫过你 Hess'，立即修正 PREFERENCES 加入'AI 自我指代'规则。教训：AI 不能臆造用户没叫过的称呼——'Hess' 是模型自创简称——**用户可能从未认可这个简称**。修复：PREFERENCES Communication 段加 '我叫 小助理/Hermes/Hermes Agent，不是 Hess'。

_confidence=0.49 accepted=2026-07-15_

---

## lesson_dca6672692e1

**规则**：派单触发词（避免歧义）：'让 Pi 调研 X' / '派 Pi 跑 X' / '调 Pi 查 X' 显式派 Pi；'让 Claude 改 X' / '派 CC 写 X' / '调 Claude 跑 X' 显式派 CC。避免单独说'派 X'（'派'在中文是'分配/给'，主体不清会歧义）。老大不说主体时按任务特征自主路由（参考 ~/.hermes/skills/devops/pi-rpc-dispatch/SKILL.md 老大触发词章节）。

**理由**：2026-07-14 老大反馈'对话内容多所以是不是派 Pi 更合适'——根因是 Hermes 主对话承载了所有回显，包括 Pi/CC 跑完的长 raw output。改进方向：派单者只回'做到了 + 1-2 行证据'，raw 留文件不灌对话。

_confidence=0.6 accepted=2026-07-14_

---

## lesson_0643fb2bee36

**规则**：agent-reach (Panniantong/Agent-Reach) v1.5.0 已装激活：mcporter v0.9.0 全局 + ~/config/mcporter.json 配 Exa baseUrl。Hermes + CC 都注册了 skill（~/.claude/skills/agent-reach/ + ~/.agents/skills/agent-reach/）。CC 跑 mcporter 受沙箱拦截（dispatch.py 15:03 加了 bypassPermissions 但沙箱在 harness 层不是 CC 层），绕法是派 Pi（无沙箱、Pi 走 minimax M3 RPC 模式）。Mac 直连 YouTube 受限需代理；V2EX/知乎 RSS 不稳。

**理由**：2026-07-14 端到端验过：Exa 搜 Adyen 4 个真岗 + 拉 JD 全文；Pi 派单 30.17s 跑通 EXIT=0；GitHub curl 5.4KB OK。CC 6 次被拦后改派 Pi 即通。详见 ~/.hermes/skills/devops/pi-rpc-dispatch/SKILL.md 派单章节 + 对比文档 references/tool-comparison-adyen.md。

_confidence=0.6 accepted=2026-07-14_

---

## lesson_36969cc79717

**规则**：派单路由表：调研类任务默认派 Pi + agent-reach + Exa（精度高 30-40s）；单次宽搜/时效问答走 Hermes 直调 MiniMax web_search（Anthropic 协议 + web_search_20250305 工具，1 次 API）；写代码/改文件派 CC（superpowers 强项）；闲聊/思考 Hermes 直答不派单。

**理由**：2026-07-14 B 验证：MiniMax web_search 问天气 OK 但查 Adyen 漏 4 岗；Exa 反之。路由表分工具分场景避免重复踩坑。详见 ~/.hermes/skills/devops/pi-rpc-dispatch/SKILL.md 工具路由表 + minimax-token-plan/SKILL.md web_search 章节。

_confidence=0.6 accepted=2026-07-14_

---

## lesson_c75bdd20fc3d

**规则**：TDAI L3 / 对话沉淀中提到的'入职 ArcusKey'是幻觉——事实是 ArcusKey 是公司（嗨九时玩科技），老大 2026-07-06 面试过这家公司（Marketing Exec/Senior），对方尚未答复。**铁律**：对话沉淀中提到'入职'字样时，必须先跟老大核实状态，不要直接当真。**赫蹏**是老大的英文名，**ArcusKey**是公司名，不要混为一谈。

**理由**：已经犯过 2 次：(1) 简历生成时把 'ArcusKey offer 已接受' 写进简历 (2) 刚才把对话沉淀中 'Linux 端 ArcusKey 上下文同步' 误解为 '已入职'。两次都是没跟老大确认就信了对话沉淀。教训：所有对话沉淀 / TDAI L3 的'入职' / 'offer' / '状态变更'类信息，必须先跟老大确认，不能直接当真。

_confidence=0.6 accepted=2026-07-10_

---

## lesson_2a9e436cc817

**规则**：TDAI L3 cloud memory carries systematic hallucination: server-side memory treats 'interviewed' as 'offer accepted' and similar. Do not auto-scan or batch-clean TDAI L3 — user prefers gradual adjustment: 'find wrong, fix wrong' is the rule. Do not re-import cloud memory wholesale. When using TDAI L3 data for decisions, always confirm with user first

**理由**：User explicit: 'slowly adjust is fine, find wrong then fix'. Auto-scanning wastes tokens, batch re-import risks losing correct entries, and assuming TDAI L3 is ground truth causes me to relay false facts to user (already happened: 'ArcusKey offer accepted')

_confidence=0.6 accepted=2026-07-10_

---

## lesson_6ebebe003e75

**规则**：Dispatch spec language rule: write dispatch task spec to Claude Code in ENGLISH (Claude code has better EN support), but the final response report (returned to user) and wechat notification must be in CHINESE. So spec body is English, expected output template and any user-facing examples are Chinese

**理由**：User explicit preference: Claude Code reads English better; but the user (老大) reads Chinese in notifications and final reports. Spec writer (Hermes) translates task intent to English for Claude, and Claude should write final report in Chinese per the report template in spec

_confidence=0.6 accepted=2026-07-10_

---

## lesson_3746e4b128d1

**规则**：dispatch notification edge case: 'md not push wechat' is about NOT pushing .md paths or file links. Pure text summary via hermes send IS desired—user wants wechat ping on task completion but cannot open .md files on phone. Do not over-restrict notification to zero

**理由**：User explicit: 'after task complete result summary push short text to wechat' is the precise rule. 'md file dont push' is about file paths, not text

_confidence=0.6 accepted=2026-07-10_

---

## lesson_53cc395a46a9

**规则**：Writing 5-principles: no trash-talk comparison; no hypothetical promises ('will do X' → 'did X'); every claim needs fact-support; LinkedIn uses storyline not pure干货; English-first then translate to Chinese

**理由**：Stable content output preference; especially for LinkedIn writing and English job applications

_confidence=0.6 accepted=2026-07-09_

---

## lesson_d9c34faa4ed7

**规则**：Resume format spec: Chinese resume uses Chinese name (陈书君); contact row format 'phone|email|highest-degree'; certificates only-name no-date; reverse-chronological work history; bullets style short-and-long (one item = one full sentence)

**理由**：Fixed preference from multiple resume iterations; resume edits must comply

_confidence=0.6 accepted=2026-07-09_

---

## lesson_6ddc33aea4a1

**规则**：Compliance risk pre-warning: when tasks involve data privacy, company assets, outbound content, batch export, assistant must proactively flag compliance risks—not just passively answer questions

**理由**：User is a compliance officer at Huiyan Zhitou, sensitive to compliance; assistant must warn ahead

_confidence=0.6 accepted=2026-07-09_

---

## lesson_be2b450064e2

**规则**：Completion-Silence Protocol: when user says done/finished/已 X, do not re-ask or re-mention in future sessions. Avoid re-mention or 'did you finish X' style questions

**理由**：User dislikes assistant re-mentioning completed items; user already mentally archived

_confidence=0.6 accepted=2026-07-09_

---

## lesson_5f324d6d1376

**规则**：配置幻觉诊断模式——'配置 active'不等于'链路生效'，验证状态不等于验证流量。修任何 agent/插件/service 后必须做端到端流量验证，不能只检查进程在跑、status 显示 ok、active 标记亮

**理由**：Mac TDAI 插件 status 显示 active 但 L0 数据 17 天空窗——状态正常但写入 pipeline 根本没接。同类案例：mimocode 付费 provider 已购但实际未使用。教训：status/config 是必要不充分条件

_confidence=0.6 accepted=2026-07-09_

---

## lesson_5022757a8185

**规则**：付费边界清晰——核心 LLM 模型（MiniMax M3、Claude Code）愿意付费使用；周边工具（IDE 插件、第三方 SaaS）不额外花钱

**理由**：用户对核心工具愿付费，对周边工具有成本意识；订阅/付费前先评估必要性

_confidence=0.47 accepted=2026-07-09_

---

## lesson_9086882ba45c

**规则**：交付物核实规范——写入任何文件前必须先 read_file 核实实际内容，或用 search 工具找原话，不直接信任 scene 摘要或 LLM 记忆

**理由**：scene 摘要会失真，直接使用会产生幻觉；必须用工具实际读原文件 / 搜原话

_confidence=0.475 accepted=2026-07-09_

---

## lesson_66dd7d84bf11

**规则**：教用户运行 bash 命令必须分三步：Terminal.app 输入命令、键入执行回车、查看输出。不替用户在 Mac 上点 Finder、不替键入命令、不替回车；让用户自己保留操作控制权

**理由**：用户明确说过'教 bash 三步走'，是稳定的教学偏好

_confidence=0.565 accepted=2026-07-09_

---

## lesson_f453b311be7a

**规则**：任何关于价格、距离、地理位置、时间、日期的事实性问答，必须先调用 search 工具或 curl API 查证，禁止凭模型记忆随口编造数字

**理由**：用户对编造数字极其反感，宁可说不知道也别瞎给。举例：以前问 7B 实际是问 Miloco 算力，模型直接编了显存数

_confidence=0.445 accepted=2026-07-09_

---

## lesson_154a864f35c7

**规则**：微信控制 Mac 不喜欢 tool progress 行（┊），用 /verbose off 或 hermes -Q 关闭

**理由**：微信消息体里 progress 行污染输出

_confidence=0.405 accepted=2026-07-09_

---

## lesson_5235a59fc874

**规则**：修改任何 agent 模型或配置前必须问清楚是哪个 agent——若用户只说改模型未明确指定（尤其刚说完 Claude Code 又说改模型），不得自动改任何配置，先问你要改哪个 agent

**理由**：避免误改：用户在不同上下文切换时容易指代不清，硬规则要求每次明确

_confidence=0.575 accepted=2026-07-09_

---

## lesson_3dee5e69defc

**规则**：修改任何 Python/shell 脚本后必须双重验证：cd ~/.hermes && git diff <file> + grep -n 新路径，禁止只根据 patch success 就报告已修复

**理由**：archive-resume.py 连续 7 次虚假修复从 7/1 到 7/8 教训，patch success 不等于真改，必须用 git 跟踪 diff 加 grep 验证路径生效

_confidence=0.6 accepted=2026-07-09_

---

## lesson_3ba0f5e02da9

**规则**：env 变量名不等于实际用途。看到 TDAI_LLM_API_KEY 不能推断是 DeepSeek，必须 curl LLM API 看返回确认

**理由**：今早 17:30 Claude Code 修了 TDAI 的 key，从 DeepSeek 换到 MiniMax M3，但 .env 里 DEEPSEEK_API_KEY 还在——我误读以为 TDAI 跑 DeepSeek。教训：必须实调 API 看 endpoint + model 名

_confidence=0.455 accepted=2026-07-09_

---

## lesson_74381fa7694b

**规则**：PREFERENCES.md 里的模型信息已更新: Hermes=DeepSeek v4, Claude Code=MiniMax M3

**理由**：老大 2026-07-04 纠正了 PREFERENCES.md 里的过时信息(MiMo v2.5-pro 改为 DeepSeek v4 + MiniMax M3),避免后续 agent 读取时再次说错

_confidence=0.44 accepted=2026-07-04_

---

## lesson_422695ae5b2d

**规则**：Always serialize timestamps in UTC to avoid cross-region comparison bugs

**理由**：prior incidents with mixed local/UTC timestamps in order ledger

_confidence=0.46 accepted=2026-04-19_

---

