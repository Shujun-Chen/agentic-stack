# Domain Knowledge

> Stable facts about the domains you work in. Not procedures (those go in
> skills), not preferences (those go in `personal/PREFERENCES.md`), not
> time-bound events (those go in `episodic/`). Pure reference material.

## 游戏设计

### 《帮你攒着》项目
- **类型**：经营养成 + 情感叙事
- **平台**：PC (Steam) / 移动端 (iOS/Android)
- **参考**：星露谷物语、动物森友会、去月球、Florence
- **引擎**：Godot 4（推荐）
- **开发周期**：单人9-13个月 / 小团队5-8个月

### 核心设计原则
- 宠物视角的家具设计（误解+努力）
- 玩具收集系统（类似动森化石，每件玩具承载回忆）
- 挡灾系统（思念值消耗，保护主人）
- 终灾抉择（游戏高潮，玩家选择）

### 情感设计
- 核心情感："我可以不在你身边，但我不能停止爱你"
- 泪点设计：宠物的误解+努力+温柔的遗憾
- 隐藏剧情：图恒宇彩蛋（流浪地球2致敬）

### 美术风格
- 像素风/手绘风，暖色调
- Q版动物角色（头:身 = 1:1.5）
- 主人不露脸（保持神秘感，让玩家代入）

## 用户 L2 场景索引（云端 2026-07-09 校对）

> 来源：TencentDB L2 scene blocks（11 个主题）
> 用途：跨 agent 共享"用户在什么领域有什么上下文"

| # | 场景 | 热度 | 一句话 |
|---|------|---:|--------|
| 1 | 职业发展与简历叙事 | 🔥139 | TOEM2 提案 PDF 提交 HR 闭环；ArcusKey 21 天计划定名"入职准备·3 周 21 天独立游戏营销学习"，定位 awesome-marketing（9 条深挖）；进度 0/21 |
| 2 | AI 编程协作与交互方式 | 59 | 4 决策点+7 禁止写入规范；风险操作安全；知识管理 skill/memory/实时查询三分法；subagent 最佳实践；合规风险提示；交付物核实 |
| 3 | 技术工具-Hermes 与 iMessage 方案 | 55 | AI 模型三阶段迁移史（MiMo→MiniMax），Linux 端完成；Mac 端 Gateway 仍用 DeepSeek API；Mac Hermes v0.18.2 无 memory search 子命令 |
| 4 | 个人信息与生活偏好 | 46 | 赫蹏/小马/ubuntu/ArcusKey/陈书君；格拉斯哥 IT 硕士+英语专八+雅思 7.0；慧研 IT Coordinator/合规；Hermes 搭建者；胖布丁 0→1 社区运营；希尔顿金卡；英式英语偏好；英文面试自我介绍规范 |
| 5 | SkillHub 技能管理与 CLI 工作流 | 38 | ArcusKey 21 天计划 P0；学习内容定位 awesome-marketing（Performance Marketing 4 + Case Studies 5）；五线体系其余线维持 |
| 6 | 技术部署与运维心得 | 29 | 1.9G VPS 多 Agent 生态 + Mac/Linux 混合架构；Hermes 跨平台版本差异；Mac TDAI 配置但未实际启用；Mac Gateway 用 DeepSeek API + launchd |
| 7 | 数据采集与爬虫技术 | 14 | 数据采集端架构：Mac 住宅 IP 处理高反爬/登录态，服务器跑 bb-browser/AutoCLI 处理公开数据；AutoCLI 0.3.8 实测 HN/StackOverflow/Dev.to 可用，arxiv/GitHub/Steam 局限；Boss 直聘/《三体》反爬受阻 |
| 8 | 日常运营与内容核查 | 13 | 合规运营日常：内容资产数据一致性核查 + 新人投顾入职合规全流程（含两份合规 checklist）；07-09 为新入职投顾召开合规会议；跨地域合规口径差异管理；订单处理与留痕 |
| 9 | 阅读与认知兴趣 | 10 | 跨学科通用思维模型；智驾技术（余承东宣传 → 智己实车体验）形成从舆论批判到亲身体验的完整审视链；知识管理哲学主张连接公共 wiki 而非封闭个人知识库 |
| 10 | 安全工具与风险审查实践 | 5 | 用户网络安全 L2-L3 靠近 L3；五步安全前置审查制度化闭环；2026-07-02 遭遇个人信息泄露事件 → 安全认知扩展至"个人信息安全"维度 |
| 11 | 创意表达与视频创作 | 3 | vlog 创作实践：受《社交网络》灵感在神农谷拍摄自然与家人素材；使用原声曲但面临城市街景与曲目节奏不匹配问题，与 AI 探讨替代方案 |
| 12 | 职场权益与劳动法律合规 | 2 | 用户自费考取证券从业资格证并确认服务期条款不适用；公司未安排培训 → 自费考试不受 3 年服务期约束；合规从业者对劳动关系中的法律风险开始系统性关注 |

> 注：完整 L2 文件不在本机 scene_blocks/，本次只能拿到摘要。原数据在云端（124.223.210.151）TDAI Gateway session 注入。

## 技术知识

### Godot 4
- 免费开源，2D强大
- GDScript 脚本语言
- 适合独立开发

### 游戏开发工具
- 美术：Aseprite (像素) / Photoshop (UI)
- 动画：Spine 2D / Godot AnimationPlayer
- 音频：FMOD / Godot AudioServer
