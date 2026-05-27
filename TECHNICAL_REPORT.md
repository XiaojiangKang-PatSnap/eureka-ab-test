# Eureka Life Sciences A/B 测试页面 — 技术研发报告

**版本**: v2.0  
**最后更新**: 2026-05-27  
**状态**: 设计系统对齐完成，分析报告已交付

---

## 一、项目概述

### 1.1 背景

针对 Eureka Life Sciences 落地页（生产页 [eureka.patsnap.com/ls-landing](https://eureka.patsnap.com/ls-landing)），创建 10 个差异化版本用于 A/B 测试。生产页面向多种买家角色采取共识叙事，对单一角色的转化深度受限——10 个变体的目标是在内容、结构与信息密度三个维度上，针对不同受众做专项优化。

### 1.2 目标（v2.0 调整后）

- ✅ **统一到公司设计系统**：全部 10 个版本对齐 PatSnap Design System v5.12，移除自创主题与装饰性视觉
- ✅ **通过内容差异化角色**：差异不再依赖颜色/字体/渐变，而是依赖内容选择、版块顺序与信息密度
- ✅ **响应式 & 性能**：保留原有响应式适配；移除冗余样式，所有变体共享 `styles/` 层
- ✅ **可分享的分析交付物**：输出详细分析报告（REPORT.html）与快速参考摘要（REPORT-SUMMARY.html）
- ✅ **打包成可独立分发包**：`sentable/` 目录可压缩后直接发给评审方

---

## 二、架构设计

### 2.1 当前文件结构

```
d:/DevPool/eureka-ab-test/
├── Design System - PatSnap AI 5.12.md   # 公司设计系统规范（输入）
├── TECHNICAL_REPORT.md                   # 本文档
├── REPORT.html                           # 详细分析报告（≈1200 行）
├── REPORT-SUMMARY.html                   # 表格式快速参考（≈440 行）
├── styles/                               # 共享样式层（设计系统单一来源）
│   ├── variables.css                     # 设计令牌（明/暗双模式）
│   ├── reset.css                         # 基础重置 + focus-visible
│   └── components.css                    # 组件原语（btn/card/tag/...）
├── version-a.html  → version-j.html      # 10 个 A/B 变体
├── components/                           # （遗留）早期共享组件 HTML
├── components.html                       # （遗留）组件预览页
├── sentable/                             # 可分发包
│   ├── REPORT-SUMMARY.html               #   快速参考（建议入口）
│   ├── REPORT.html                       #   详细分析
│   ├── styles/                           #   样式层副本
│   └── version-a.html → version-j.html   #   10 个变体
└── sentable.zip                          # 压缩后的分发包
```

### 2.2 设计系统对齐（最重要的架构变化）

v1.0 中每个版本自定义主题、字体、渐变；v2.0 全部收敛到 PatSnap Design System v5.12。差异化通过**内容**而非**视觉**承载。

| 项 | v1.0 | v2.0（当前） |
|----|------|------|
| 字体 | Poppins / Noto Serif / Inter 混用 | **仅 Inter**（中文环境下回退到 PingFang SC） |
| 字重 | 300/400/500/600/700 | **仅 400 与 600** |
| 主色 | 5 套主题色（蓝/紫/橙/学术深蓝/极简蓝） | **仅 `#0764E9`** PatSnap Blue |
| 渐变 | 大量文字与背景渐变 | **零装饰渐变** |
| 圆角 | 8 / 12 / 16 / 24px / 9999px 混用 | **4px 按钮 · 8px 卡片 · 12px 横幅** |
| 阴影 | 自定义装饰阴影 | **令牌化** `--shadow-card` 等 |
| 文本主色 | `#1e293b` / `#1f2937` / `#000` | **`#020A1A`**（永不纯黑） |
| 等宽字体 | 各异（IBM Plex Mono / Consolas） | **JetBrains Mono / Fira Code** |
| 暗色模式 | 各自实现 | **使用规范令牌**（`#020A1A` 页面 / `#0D1B2E` 卡片 / `#142236` 提升） |
| Hero 标题 | `clamp(2.2rem, 5vw, 4rem)` 高至 64px | **不超过 36px / lh48**（移动端 28px） |
| 按钮形状 | 9999px 全圆角 | **4px 矩形** |

### 2.3 角色与变体的新映射

视觉趋同后，每个版本通过**版块选择 + Hero 组成 + CTA 措辞**承载角色身份。

| 版本 | 目标角色 | 版面定位 | Hero 元素 | 主 CTA |
|----|----|----|----|----|
| A | 计算化学家 / 药物化学家 | **暗色模式**（系统暗色令牌） | SAR 分布图 + ADMET 网格 | Start free trial |
| B | 早期生物科技 R&D 负责人 | 亮色 | Live agent 活动列表 | Try free for 14 days |
| C | 学术 PI / 个人研究者 | 亮色，居中 | 同行评审验证陈述 | Request research access |
| D | VP R&D / BD 负责人 | 亮色 | $2.4M 节省面板 + 2 项指标 | Schedule ROI assessment |
| E | 时间紧迫的中漏斗买家 | 亮色，极简 | 标题 + 2 CTA | Start free trial |
| F | 工程师 / 数据科学家 / 集成工程师 | 亮色 + 暗色代码块 | 实时 curl + JSON 响应 | Get API key |
| G | 怀疑型企业买家 | 亮色 | 居中陈述 + 客户 logo 墙 | Book a demo |
| H | 数据科学家 / 竞争情报分析 | 亮色 + 仪表盘 | 4-card 仪表盘网格 | Schedule demo |
| I | 移动场景用户 / BD 出差 | 亮色，移动优先 | 紧凑 Hero + 快捷操作 | Start free trial |
| J | 大学图书馆 / 学术采购 | 亮色 | 出版物 + 引用块 | Request academic access |

---

## 三、技术实现要点

### 3.1 共享样式层

全部变体共用 3 个 CSS 文件，无重复造轮子：

- **variables.css**：设计令牌（颜色、间距、圆角、阴影、字体、断点）+ `.theme-dark` 类切换暗色
- **reset.css**：基础重置 + `:focus-visible` 焦点环（来自系统规范）
- **components.css**：`.btn` / `.card` / `.tag` / `.alert` / `.topnav` / `.hero` / `.feature-grid` / `.stats-row` / `.testimonial` / `.cta-banner` / `.footer` / `.logo-wall` 等组件原语

### 3.2 响应式断点

| 断点 | 宽度 | 关键变化 |
|----|----|----|
| Mobile | < 768px | 单列、隐藏顶部导航链接、卡片网格降为 1 列 |
| Tablet | 768–1024px | 双列网格、移动端 Hero 字号降至 28px |
| Desktop | 1024–1280px | 三列特性网格、完整导航 |
| Wide | > 1280px | 完整布局、最大宽度 1440px 居中 |

### 3.3 暗色模式实现

只有版本 A 使用暗色（计算化学家身份信号）。通过 `<html class="theme-dark">` 切换；CSS 变量在 `.theme-dark` 作用域内被覆盖，组件无需重写。所有暗色色值来自系统规范（`#020A1A` / `#0D1B2E` / `#142236`），不再是自创色。

### 3.4 字体加载

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600&family=JetBrains+Mono:wght@400;600&display=swap" rel="stylesheet">
```

仅加载实际使用的两种字重（400 / 600），符合系统规范。

### 3.5 图标策略

全部使用**线性轮廓 SVG**，描边宽度 1.75px，符合系统规范的 1.5–2px 区间。图标统一放在 `--color-brand-subtle` 背景的 4px 圆角方块中，在暗色变体里使用对应的暗色令牌。

---

## 四、合规性

### 4.1 设计系统合规矩阵

| 规则 | 要求 | 全部变体 |
|----|----|----|
| 主色 | `#0764E9` | ✅ |
| 页面背景 | `#F4F5F7` 亮色 / `#020A1A` 暗色 | ✅ |
| 卡片背景 | `#FFFFFF` 亮色 / `#0D1B2E` 暗色 | ✅ |
| 主文本色 | `#020A1A`，永不纯黑 | ✅ |
| 字体 | 仅 Inter，仅 400/600 | ✅ |
| 等宽字体 | JetBrains Mono / Fira Code | ✅ |
| Hero 字号上限 | 36px / lh 48px | ✅ |
| 按钮圆角 | 4px | ✅ |
| 卡片圆角 | 8px | ✅ |
| 卡片阴影 | `0px 1px 2px rgba(2,10,26,0.04), 0px 4px 12px rgba(2,10,26,0.06)` | ✅ |
| Hover 边框 | `#82C3FF` | ✅ |
| 焦点环 | `0 0 0 3px rgba(7,100,233,0.25)` | ✅ |
| 间距网格 | 4px 基准 | ✅ |
| 图表色板 | 10 色（仅版本 H 使用） | ✅ |
| 语义颜色 | 蓝=动作 / 绿=成功 / 橙=警告 / 红=错误 | ✅，无重新定义 |

### 4.2 安全与企业合规标识

变体 A 包含合规标识行（FDA 21 CFR Part 11 / ISO 27001 / SOC 2 Type II / GDPR / RBAC / Audit Trail）。其他变体根据角色需要选择性展示。

---

## 五、交付物

### 5.1 网页变体（10 个）

`version-a.html` → `version-j.html`，全部对齐设计系统、共享 `styles/` 层。

### 5.2 详细分析报告

[REPORT.html](REPORT.html) ≈ 1200 行，包含：

1. 执行摘要
2. 生产页基线分析（产品/定价/角色/JTBD）
3. 10 个变体的存在理由（生产页的 3 个结构性折中 + 3 个差异化轴）
4. 角色 × 场景矩阵
5. **逐版本深度分析**（每个版本 ≈900 字：角色画像 / 存在理由 / 用户场景 / 内容理由 / 部署建议 / 失效场景）
6. A/B 测试设计建议（角色路由方案 vs 单变量隔离方案）
7. 附录（设计系统合规矩阵 / 生物医药术语表 / 文件索引）

### 5.3 表格式快速参考

[REPORT-SUMMARY.html](REPORT-SUMMARY.html) ≈ 440 行，8 个表格章节：变体索引 / 部署地图 / 成功指标 / 角色匹配矩阵 / 版块映射 / 推荐测试 / 设计系统合规 / 文件索引。

### 5.4 可分发包

`sentable/` 目录（已压缩为 `sentable.zip`）包含：
- REPORT-SUMMARY.html（建议入口）
- REPORT.html
- styles/（样式副本）
- 10 个变体

接收方解压后用浏览器打开 `REPORT-SUMMARY.html` 即可，无需安装、无需 CLI。仅依赖 Google Fonts CDN。

---

## 六、A/B 测试建议（核心结论）

### 6.1 不要采用 10 路平均分流

两个原因：
- **统计功效**：10 路分流意味着每个变体收到 1/10 的流量，达到显著性所需周期增至 10 倍
- **变量耦合**：每个变体相对生产页同时改了多处（Hero / 版块顺序 / CTA 文案 / 内容侧重），无法归因

### 6.2 推荐方案

| 优先级 | 测试 | 受众 | 目标 |
|----|----|----|----|
| 首发 | 生产页 vs E | 品牌词搜索 | 价格前置是否提升自助转化 |
| 第二 | 生产页 vs B | LinkedIn 生物科技广告 | 创业语调是否提升年轻生物科技转化 |
| 第二波 | 生产页 vs C vs G | 晚期漏斗（≥2 次访问） | 哪种证据类型更适合晚期买家 |
| 第二波 | 生产页 vs A vs B | 自然搜索 | 专项化是否优于共识叙事 |
| 第二波 | 生产页 vs F | HN / dev.to / GitHub | 代码优先 Hero 是否提升开发者激活 |
| 第二波 | 生产页 vs I | 移动设备流量 | 移动优先是否提升移动转化 |

### 6.3 指标分层

| 阶段 | 变体 | 主指标 | 护栏指标 |
|----|----|----|----|
| 自助试用 | A · B · E · I | 注册 → 24h 内首次运行 agent | 跳出率 / 滚动深度 |
| 企业 demo | D · G | demo 预约 → CRM 商机 | demo 缺席率 |
| 开发者激活 | F | API key → 首次认证请求 | 首请求时长 |
| 数据分析激活 | H | demo 预约 → 仪表盘激活 | demo 缺席率 |
| 学术 / 机构 | C · J | 访问申请 / 机构许可询问 | 跳出率 |

---

## 七、技术栈

| 类别 | 选型 | 说明 |
|----|----|----|
| 前端 | 原生 HTML / CSS | 无框架依赖，零构建步骤 |
| 字体 | Inter (400/600) + JetBrains Mono (400/600) | 通过 Google Fonts CDN |
| 图标 | 内联 SVG，1.75px 描边 | 符合系统 1.5–2px 描边规范 |
| 动画 | CSS transition（仅 Hover / Focus） | 移除原 v1.0 的装饰动画 |
| 暗色模式 | CSS 变量 + `.theme-dark` 类作用域 | 仅版本 A 使用 |
| 分发 | 静态文件 + zip 压缩包 | 接收方仅需浏览器 |

---

## 八、状态与后续

### 8.1 已完成

- ✅ 设计系统令牌层（variables.css）
- ✅ 共享组件原语层（components.css）
- ✅ 10 个变体重写并对齐设计系统
- ✅ 详细分析报告（REPORT.html）
- ✅ 表格式快速参考（REPORT-SUMMARY.html）
- ✅ 独立分发包（sentable/ + sentable.zip）

### 8.2 待办（按优先级）

- [ ] 接 A/B 测试平台（如 GrowthBook / Optimizely）
- [ ] 在 Cloudflare Worker 或 CDN 边缘实现按流量来源路由
- [ ] 接入分析追踪（按变体维度看 funnel）
- [ ] 国内域名版本：将字体回退到 PingFang SC、Microsoft YaHei
- [ ] 灰度发布与回滚机制

### 8.3 不在范围

- 后端集成（变体均为静态页面，CTA 链接可直接复用现有路由）
- A/B 工具的具体配置（建议交给增长团队）
- 翻译/本地化（当前为英文版；中文版需基于设计系统的国内字体栈）

---

## 九、相关文档

- [Design System - PatSnap AI 5.12.md](Design%20System%20-%20PatSnap%20AI%205.12.md) — 公司设计系统规范（输入）
- [REPORT.html](REPORT.html) — 详细分析报告
- [REPORT-SUMMARY.html](REPORT-SUMMARY.html) — 表格式快速参考
- [生产页基线](https://eureka.patsnap.com/ls-landing) — 对比基准

---

*Eureka Life Sciences — Precision AI for Drug Discovery*
