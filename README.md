# zgg-find-ecommerce-skills

**电商 Skill 导航** · 帮中文电商用户查找、比较和安装开源 AI Skills。

> 上游项目：[@zarockfat/zgg-find-ecommerce-skills](https://github.com/zarockfat/zgg-find-ecommerce-skills)，本仓库收录其技能本体（SKILL.md + 161 技能目录快照 + 检索脚本）。

---

## 它解决什么问题

| 痛点 | 表现 | 怎么解 |
|---|---|---|
| **找不到** | 不知道开源社区有没有对应技能 | `references/catalog.json` 内置 161 个技能目录快照，离线可查 |
| **不会挑** | 搜出来一堆，不知道哪个靠谱 | 目录带平台/任务分类与仓库信息，按需求过滤比较 |
| **装不明白** | 找到了不知道怎么装进自己的 Agent | SKILL.md 内置安装方式说明与能力边界声明 |

**产出物**：候选技能清单（按平台/任务匹配）→ 对比与推荐 → 安装方式。

---

## 怎么用

```text
Step 1  说清需求：平台（Amazon / TikTok Shop / Shopee / Shopify / Temu / 1688 …）+ 任务（选品 / Listing / 内容 / 广告 / 客服 / 库存 …）
Step 2  Agent 查询 references/catalog.json，给出候选与对比
Step 3  确认后按 SKILL.md 里的安装方式装进你的 Agent 环境
```

也可以直接跑检索脚本（Node.js ≥ 18）：

```bash
node scripts/search.mjs "TikTok Shop 广告"
```

配套可视化浏览页面：`assets/ecommerce-skills.html`（浏览器直接打开）。

---

## 边界

> **本技能只做「找技能」，不做业务**——不生成 Listing、不分析广告、不拆评论；找到具体技能后，实际业务执行交给对应技能。

- 目录快照**未覆盖全网**，零结果时如实说明，不要硬凑；
- 安装任何第三方技能前，请自行过一遍安全与合规检查；
- 目录更新检查：`node scripts/updates.mjs`。

---

## 目录结构

```text
zgg-find-ecommerce-skills/
├── SKILL.md            ← 技能入口（触发条件 + 工作流）
├── version.json        ← 上游版本号
├── references/         ← 161 技能目录快照（catalog/release/website）
├── scripts/            ← 检索 / 更新检查 / 欢迎页脚本（.mjs）
└── assets/             ← 可视化浏览页面
```
