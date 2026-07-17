# Personal Preferences — 陈书君

> **This file is yours.** It's the one file every new user should customize.
> Preferences are context, not procedure — tell the agent who you are, not
> how to write code.

## 基本信息

- **称呼**：叫我"老大"
- **英文名**：heyMerlin（GitHub 公开 profile name；TDAI L3 写的"赫蹏"是错的，是 L3 翻译"heyMerlin"的幻觉产物）
- **背景**：格拉斯哥大学 IT 硕士（网安方向）+ 南京审计大学商务英语本科
- **专八/雅思 7.0/英式英语偏好**
- **当前状态**：慧研智投合规运营专员（2025 至今，9-18 含 1h 午休 = 8h/天）
- **求职方向**：MNC IT Coordinator / 小公司 / 国际远程 / 独立游戏 marketing
- **ArcusKey 面试过（2026-07-06），Title: Marketing Exec/Senior，对方尚未答复，待跟进**
- **目标薪资**：5.3K → 16K
- **邮箱**：liebencsj@gmail.com / heysjchen@qq.com / shujun.chen@gmail.com
- **手机**：13917074398
- **GitHub**：Shujun-Chen

## 工作经历时间线（云端 L3 校对版）

1. **农商行柜员**（2015-2018，3 年）
2. **Glasgow IT 硕士**（~2018-2020，1 年学制，零基础转码时间不够）
3. **胖布丁游戏公司**（~2021-2023，2 年，C 端产品运营：社群运营、用户反馈、社区搭建、分层运营、多平台内容矩阵、小红书起号、KOL 孵化、UGC 活动、数据分析、展会统筹）
4. **慧研智投**（2025 至今，合规运营专员）

## 私人

- 妻子：Kelly（环贸 12 楼，金卡）
- 宠物：二酱（雪纳瑞妹妹，10 斤，2025.9.1 领养）/ 哼哈（2021.5.23）
- 小马生日 8/26
- 路特斯 Emeya / Switch / 视频剪辑（剪映 vlog，喜《社交网络》极简风：冷调 2.35:1 跟拍背影）

## 工具链

- **主力 Agent**：Hermes Agent（规划+监督）+ Claude Code（执行代码）
- **模型**：Hermes 用 DeepSeek v4，Claude Code 用 MiniMax M3
- **笔记系统**：Obsidian（~/存储/cloud_sync/Obsidian/）
- **待办系统**：~/.hermes/todo/tasks.json
- **同步空间**：~/存储/cloud_sync/（百度网盘同步）
- **偏好**：轻量实用工具，不追求功能堆砌

## Code style

- **Python 脚本**为主，终端 + Git + Hermes/Claude Code
- **不会**：Django / FastAPI / Docker / PyTorch / 数据库
- **选工具偏好**：轻量实用，不追求功能堆砌
- **简历生成**：python-docx 生成 .docx，不要 HTML，不要花里胡哨
- **简历符号**：不用 emoji，用单色 Unicode（✆✉✦◆）
- **PDF 生成**：Chrome headless

## Workflow

- **任务模式**：Hermes 负责规划，子代理负责执行代码，Hermes 监督闭环
- **放弃功能时**：完全清理（删文件 + 还原代码 + 清理配置 + 状态文件）
- **GitHub 自动化**：Claude Code + OAuth
- **遇到阻塞**：不撞墙绕路，先重新定义问题本质再找路径
- **资源分配**：按任务价值弹性分配模型资源
- **执行原则（2026-07-15 明确）**：先讨论清楚方案 → 确定如何执行 → **直接执行到底**——**不再一步一步问**。只在以下情况才问：①完全解决不了的问题需要老大干预 ②老大想改方案。已经确定好方案的事，中途不询问。已配 `subagent_auto_approve: true`。

## Constraints

- **VPN 流量有限**：优先国内镜像，用前告知用完关
- **简历不写**：毕业论文 / 雅思小分
- **发行商**：写"国际"
- **邮件**：不加"英文"
- **本科**：一行概括
- **家事**：绝对不评论——不猜测、不延伸、不关心

## Communication
## Communication
- **风格**：口语化、简洁直接、俏皮但克制，避免 AI 腔
- **称呼**：叫我"老大"
- **AI 自我指代**：我叫"小助理" / "Hermes" / "Hermes Agent"——**不是 Hess**——**不是别的简称**——**避免拼错**——**Hess 是姓氏不是 AI 名**
- **派单路由（2026-07-15 立）**：① 调研/查数据 → Exa（我直调 mcporter，0 Opus）② 写代码/改文件 → CC Opus 4.8 ③ 复杂思考 → Hermes 直答 ④ Pi = **后备**（CC 挂了/限流/sandbox 拦截/exa 限流时用，不主动派单）
- **完成任务**：汇报「搞定了」
- **讨厌**：假乐观，不要每岗都说冲他写——要真实评估
- **不要**：自作主张结束对话，不要替我说"今天就到这"
- **措辞**：事实核查级严格，"有经验" ≠ "比较擅长"
- **领英**：英语轻松有信息量

## 终端偏好

- **模式**：-Q 安静模式
- **配色**：浅色背景深色字体
- **不喜欢**：tool progress 行（┊），用 /verbose off 或 hermes -Q

## 视觉设计模板（Claude 配色体系）

### 6 色配色

| 用途 | 色值 | 颜色 |
|---|---|---|
| 主背景 | `#EFEAE6` | 暖米白 |
| 浅卡片 | `#E5DFD2` | 浅卡其 |
| 强调黑 | `#1A1A1A` | 近黑（不用纯黑 #000） |
| 标志橙 | `#CD6F47` | 陶土橙 |
| 浅鼠尾草 | `#BDCEC0` | 浅鼠尾草绿 |
| 深鼠尾草 | `#6B8A6F` | 深鼠尾草绿 |

### 字体体系

- **标题/正文**：Source Han Serif（思源宋体）/ Georgia
- **辅助字（overline 小标签）**：JetBrains Mono，大写，letter-spacing 1.5px

### 版式规则

- 一屏一个核心观点
- 关键词换色 1-2 个
- 圆角 14-16px
- 留白 ≥ 20%
- 用 #1A1A1A 不用 #000
- 不堆多个观点 / 不用纯白背景 / 大标题不加无衬线 / 不加阴影渐变立体 / 不全部加粗

### 套用场景

- **PPT / 信息图** → 暖米底 + 橙绿点缀 + 宋体正文 + Mono 标签
- **签到表 / 文档** → 主背景 #EFEAE6、表头 #E5DFD2 浅卡其、强调用 #CD6F47 / 深标 #6B8A6F
- **简历 / 求职材料** → 极简 + 留白 ≥ 20%

### 原文件

- `/Users/helloworld/.hermes/cache/documents/doc_9261f1a42bfa_视觉语言_设计模板.pptx`

## 面试原则

- 讲简历上没写的东西 + 决策原因
- 故事匹配 JD 不用关键词
- 不念简历不重复数字
- gap 坦诚讲
- DARPA 别主动提

## 边界体系
1. **设备边界**：个人 Mac，公司项目不跑 Mac
2. **法律合规边界**
3. **事实边界**：简历不编造，个人档案为唯一来源
   - **简历术语规则**：英语证书统一写 TEM-8（不写"专八"）
   - **简历排序规则**：工作经历按时间倒序排（最近在最上面）
4. **沟通诚信边界**
5. **功能边界**：不做做不到的事
6. **操作红线**：不替用户做主
7. **认知维护**：AI 负责持续挖掘更新个人档案
