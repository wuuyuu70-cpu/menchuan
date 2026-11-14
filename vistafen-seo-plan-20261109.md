# VistaFen SEO 方案 — 照搬 HY 服务器站的方法（2026-11-09）

## 0. 方法一句话

HY 站的方法不是“天天改站、买工具、一次发很多页”，而是这六条，VistaFen 原样照搬，只换类目：

1. **关键词缺口（免费路子，不买 Semrush）**：找对手有排名、自己没有的词，按意图分流。
2. **意图分流**：型号/系列词 → 加厚现有页；how-to / 对比 / 问题词 → 写指南；供应商/项目词 → 做商业落地页。
3. **加厚标准**：每页一套固定标准（见第 5 节），不是想到哪写到哪。
4. **双周一批**：每批最多 1–2 篇新内容 + 1 次老页加厚，攒一批、一次部署、一次验收。
5. **GSC 定方向**：每月看一次真实曝光/点击/排名（11–30 名的词最值得推），2–4 周后复查，不凭感觉改。
6. **证明红线**：没确认的库存、兼容、性能数值一律不写；不抄对手；不把合作方的产品、证书、项目写成自己的。

流量不作保证。VistaFen 的转化和 HY 一样，只认一件事：**邮箱 / WhatsApp 询盘**（primewindows@vistafen.com / +8617722594432），
曝光和点击只是过程指标。

## 1. 现状基线（2026-11-09）

- 上线：2026-10-19，158 个英阿页面；静态站（HTML/CSS/JS，RackNerd VPS + Nginx + Cloudflare），**不是 WordPress，没有 wp-admin**。
  改内容 = 改源文件 + 重新生成 + 部署到 `/var/www/vistafen/current`，工单给 Codex。不要迁 WordPress。
- 结构：全站是 `index.html?page=...` 参数页（`?page=product&id=casement-60`、`?page=systems&group=curtain-wall`、`?page=application&id=villas` 等），
  Google 渲染成本比静态页高，排队会慢一些。
- GSC（2026-10-28 截图）：12 已索引，148 未索引，其中 147 个“已找到、目前尚未建立索引”（新站爬取排队，不是错误），1 个重定向。
  Sitemap 2026-10-25 提交成功，发现 158 页。按 10-29 的判断：大头 2–6 周进，偏慢的那头，长尾 1–3 个月，且不一定到 0。
- 内容现状：产品系列页已有（casement、sliding window/door、folding、curtain wall、commercial door、skylight、interior、panoramic、entry），
  application 页已有（villas、urban、commercial、coastal），resource 页只有 glass / climate / supply。
  **缺口在指南 + 供应商流程，不在产品系列数量。**Resources 页实测只有通用问答，没有深度指南。
- 关键词缺口 v1（2026-10-29，免费版）：`vistafen-keyword-gap-v1-20261029.md`，已建双周跟进 cron
  `vistafen-keyword-gap-biweekly`，下一期约 2026-11-12。
- 性能（2026-10-21 工单）：PageSpeed 移动端 LCP 5.8s，目标 LCP < 2.5s、性能分 ≥ 90。**本方案写稿时未确认该工单是否已部署，见第 11 节待确认。**
- 目标市场：英/阿双语，面向工程商、开发商、经销商、建筑师；海湾（UAE / Saudi）是重点应用场景，
  主拼写用英国 `aluminium`，正文可自然带美国 `aluminum` 变体。

## 2. 关键词架构（三层，和 HY 的“型号页 + 指南”对应）

| 层 | VistaFen 对应 | 主词（示例） | 作用 |
|---|---|---|---|
| 1. 总主题 | 首页 + Systems 总览 | aluminium windows and doors | 定主题，不一开始硬抢 `aluminium windows` 头部词 |
| 2. 商业落地页（4 页） | Windows / Doors / Façades（curtain wall）/ Supply（供应商流程） | aluminium window systems；aluminium doors and sliding doors；aluminium curtain wall systems；aluminium window and door supplier | 承接采购意图，是询盘入口 |
| 3. 系列 + 指南长尾 | 现有系列页加厚 + 新指南 | thermal break aluminium windows；aluminium curtain wall details；lift and slide door system；aluminium windows for villas / high-rise buildings；aluminium window details DWG | 系列页讲“能卖什么”，指南讲“怎么选、怎么审”，互相内链 |

**VistaFen 和 HY 的一个关键不同**：HY 的型号词是真实零件号（DXD9H、P22892-001），买家会按号搜；
VistaFen 的系列号（casement-60、curtain-wall-100）不是买家搜索词，**不要为系列号单独建页、不要指望它带来流量**。
系列页的价值是：承接“系统类型 + 性能 + 应用”这类词，并把指南流量导向询盘。

## 3. 缺口分流（照搬 HY 的意图路由）

| 搜索意图 | 路由 | VistaFen 例子 |
|---|---|---|
| 系统类型 / 性能词 | 加厚现有系列页，不新建 | thermal break casement window、sliding window system profile、curtain wall system |
| how-to / 对比 / 问题词 | 新指南 | thermal break 是什么、幕墙节点怎么做、气密水密风压等级怎么读 |
| 供应商 / 项目词 | 新商业落地页 | aluminium windows and doors supplier for UAE projects、project window supplier、custom aluminium windows from China |
| 应用场景词 | 加厚现有 application 页，不新建 | aluminium windows for villas、for high-rise buildings、coastal（盐雾/UV/沙尘） |
| 资料 / 图纸词 | 资料索引页（可索引，下载走询盘） | aluminium window details DWG、curtain wall section、project submittal checklist |

不追的词：对手品牌名（Reynaers、Schüco 等，只偷主题不偷品牌）、retail 价格词（prices / near me / for sale）、
VistaFen 无法证明的性能数值词。

对标分组（v1 已定，不改）：系统品牌组 Reynaers / Schüco / Aluprof / AluK / Alumil（技术指南主题来源）；
中国供海湾项目组 DERCHI / SAINTY / Rolay（商业词来源）。难度只凭公开信号判断（对手体量、内容厚度、SERP 是否被原厂文档占满），
**没有可靠量级数据的词一律写“量级未知”，价值凭采购意图判断，不编搜索量、不编难度分。**

## 4. 批次排期（双周一批，每批最多 1–2 篇新内容 + 1 次老页加厚）

v1 第一批原先列了 3 个（2 指南 + 1 商业页），按 HY 节奏拆成两批执行，不要一次发 3 篇。

| 批次 | 时间（约） | 内容 | 备注 |
|---|---|---|---|
| 0. 收尾 | 现在–11-12 | **不发新页**。只做：确认性能工单是否已部署；核心页（首页、Systems、curtain wall、contact）在 GSC 手动请求索引；确认 primewindows@vistafen.com 测试邮件能收到 | 147 页还在排队，先让索引追上来 |
| 1 | 11-12 | 商业页：aluminium windows and doors supplier for UAE projects；指南：thermal break aluminium windows | 最接近转化的一批先做；热断桥写海湾角度（防空调冷量外泄），不是欧洲防寒 |
| 2 | 11-26 | 指南：aluminium curtain wall details；指南：lift and slide door system sizing, hardware and glass | 幕墙页只写自己系列能做的节点/尺寸；滑门只写自己系列的最大尺寸/重量 |
| 3 | 12-10 | 指南：air, water and wind performance testing explained；加厚：villas application 页（玻璃、遮阳、开启方式） | 性能数值只写已确认的系列，未确认的只讲方法、不写等级 |
| 4 | 12-24 | 指南：aluminium windows for high-rise buildings；加厚：coastal application 页 | 看第 3 批的 GSC 数据后再定是否调换顺序 |
| 5+ | 2027-01 起 | project submittal checklist、DWG / section 资料索引页、fire-rated / acoustic / solar shading（先确认系列是否覆盖，覆盖不了的不写） | 每批前先看 GSC，再定做指南还是做商业页 |

每批流程（和 HY 一样）：Juno 给大纲/工单 → 用户点头锁定 → Codex（建站开发）一次部署 → 用户在 GSC 请求核心页索引 →
2–4 周后看 GSC 曝光/点击/平均排名 → 再定下一批。**不要在批次中间插单，合并进已锁定的批次。**

## 5. 页面加厚标准 — VistaFen 版“DXD9H 标准”

HY 的型号页标准是：专属标题+描述、6 条可见 FAQ + FAQPage JSON-LD、主图 alt、只写已确认的兼容表、Schema 0 错误。
VistaFen 的系列页 / 指南页照此改写：

**系列页（每页必备）：**
- 唯一 title / meta description / H1，不与别的系列页重复；title 带系统类型 + 关键性能词，不堆系列号。
- 参数表：框深、玻璃厚度、最大尺寸/重量、开启方式、五金、饰面——**只写工厂已确认的**，没确认的留空待确认，不套用对手数字。
- 5–6 条可见 FAQ + FAQPage JSON-LD，问题取自真实询盘/搜索（例如“这个系列能不能做超大尺寸？”“沿海项目要什么饰面？”）。
- 主图 alt、截面图/节点图（有就放，没有就不编）；每页都有询盘入口（邮箱 + WhatsApp）。
- 内链：系列页 ↔ 对应指南、application 页、Supply 商业页，互相导流。

**指南页（每篇必备）：**
- 写 VistaFen 自己的角度（中国供海湾项目的供应商视角 + 自家系列内链），不抄、不改写对手文章。
- 结构：问题是什么 → 怎么判断 → VistaFen 系列怎么对应 → 要发什么资料才能报价（opening schedule、图纸、性能目标、时间）。
- 有表就给表（例如滑门布局对照表、性能等级对照表），表里数字只用已确认的。
- 结尾链回对应系列页 + Supply 页 + 询盘入口；FAQ 同样 5–6 条 + JSON-LD。

**双语**：每篇英文版上线时，阿语版字段、标题、图片说明要成对，不能只发英文留半页阿语。
发布后检查：Schema 验证 0 错误/警告；Cloudflare 缓存已清；新页已进 sitemap。

## 6. GSC 复盘节奏（和 HY 一样：双周执行、每月定方向）

- **双周（已建 cron，约 11-12 下一期）**：报本批大纲/工单 + 上一批的收录状态，不天天改站。
- **每月 5 号左右（建议增设，和 HY 的月度复盘同节奏）**：看 GSC 效果报告——覆盖率（已索引数）、曝光词、点击、平均排名。
  重点推 **11–30 名的词**（触手可及），已进前 10 的词优先级下调；曝光涨、点击不涨的页先看标题/描述，不急着改内容。
- **每批上线 2–4 周后**：只看该批页面的曝光/点击/排名，再决定下一批是继续指南还是转商业页。
  Google 生效周期 1–4 周，新页第一周没排名是正常的。
- Juno 没有 GSC 直读权限：**每月复盘和每批复查都需要用户提供 GSC 截图或数字**，不要让 Juno 猜排名。

## 7. 技术清单（静态站特有，别按 WordPress 的做法）

- 不改 URL：`index.html?page=...` 参数结构在索引追上来之前不动，改 URL 等于重新排队。
- 每页唯一 title / meta / H1、canonical 自指、EN/AR hreflang 成对；sitemap 每次发新页后更新 lastmod。
- robots.txt：`Allow: /`，只禁 `/pages/`（现状已确认），不要误禁产品页。
- 性能：LCP < 2.5s、性能分 ≥ 90（10-21 工单目标）；图片转 WebP、按断点出图、hero 图不 lazy；静态资源长缓存、HTML 不长缓存。
- 部署后：清 Cloudflare 缓存、抽查英文和阿语（RTL）页面无错位、询盘链路（mailto + wa.me）不变。
- 外链：前 2–6 个月先做站内，内容立住了再谈外链；不买链接，不拿同行产品图当自己的。

## 8. 红线（每批都适用）

- 不写未经确认的性能数值、库存、兼容范围；不能确认的只记录、不上页。
- 不把合作方（mparolas.com 归属仍未澄清）的产品、证书、项目写成 VistaFen 自有；证书页按 Resources 页现有口径写“证书发给指定制造商、每单核查范围”。
- 不抄对手内容，不追对手品牌词，不做 retail 价格词。
- 不一次发 10 篇；147 页排队没清之前，新页更要克制。
- 报告只做分析，不发布、不改站；上线前用户点头才锁定。

## 9. 衡量标准（怎么算“有效”）

- 过程指标：已索引数上涨、核心词进入 11–30 名区间、指南页有曝光。
- 结果指标：**邮箱 / WhatsApp 询盘数**。和 HY 一样，曝光、点击涨了但询盘没涨，不算成功；要回头看是词错了、还是页面没把询盘入口讲清楚。
- 失败信号：两周后已索引数基本不动、或新指南有曝光无点击、或询盘全是 retail 散户——出现任一信号，下一批先停新指南，改做商业页或加厚。

## 10. 需要用户确认 / 提供的（没这些，工单写不下去）

1. 性能工单（10-21，LCP 5.8s）是否已部署、重测结果是多少？
2. 每个系列的已确认参数：框深、玻璃厚度、最大尺寸/重量、U 值、气密/水密/风压等级——按系列给一张表，没确认的标“待确认”，不要口头报。
3. 证书范围：每个系列的证书发给谁、覆盖哪些配置（Resources 页已有“每单核查”的口径，写指南时沿用）。
4. primewindows@vistafen.com 测试邮件是否已收到（收尾待办，仍未闭环）。
5. 每月 5 号复盘时提供 GSC 截图或数字（覆盖率 + 效果报告）。

## 11. 和 v1 / HY 报告的关系

- 本方案是 v1 缺口清单的执行版：v1 定了“缺什么、按什么顺序”，本方案定了“每页做到什么标准、每批发几篇、怎么验收”。
- HY 报告（hy-keyword-gap-v1-20261031.md）的方法、节奏、红线原样沿用；不同的是：VistaFen 没有零件号型号词，系列号不作搜索词；
  VistaFen 是静态站不是 WordPress，部署走源文件 + 重新生成，不走 wp-admin。
