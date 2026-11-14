# VistaFen SEO 第一批工单 — 给 Codex（2026-11-09，已批准）

状态：**已部署 2026-11-10。用户 2026-11-09 批准，Codex 已部署到正式站，交付报告见 ~/workspace/user/files/SEO_BATCH1_REPORT_20261110.md；Juno 2026-11-10 已核实两页英文版在线。待办只剩用户在 GSC 对两页英文新页请求索引。**
来源：`vistafen-seo-plan-20261109.md` 第 4 节第一批；缺口清单见 `vistafen-keyword-gap-v1-20261029.md`。
本批只有 2 页，不要多加，不要把第二批（幕墙节点、升降推拉门）提前放进来。

## 通用要求（两页都适用）

- 静态站，不迁 WordPress，不改现有 URL。两页都按现有生成器模式新增（参数页结构见下），上线后加进 `sitemap.xml` 并更新 lastmod。
- 每页：唯一 title / meta description / H1、canonical 自指、EN/AR hreflang 成对。**英文版和阿语版成对上线，不能只发英文。**
- 每页：5–6 条可见 FAQ + FAQPage JSON-LD，Schema 验证 0 错误/警告；BreadcrumbList 按现有模式。
- 每页：询盘入口不变 — 邮箱 primewindows@vistafen.com、WhatsApp +8617722594432（mailto + wa.me 链接保持原样）。
- 图片：只用 VistaFen 自己的产品/系统图，不拿同行图；主图加 alt；WebP + 按尺寸裁切；hero 图以外加 `loading="lazy"`。
- **红线：不写未经确认的性能数值、MOQ、交期、证书范围；不把合作方产品、证书、项目写成 VistaFen 自有；不抄对手文案；不提对手品牌名。**
  下文所有标 `[待确认]` 的项，上线前要么由用户/工厂填上真实值，要么整句删掉、改写成“按项目确认”，**不许编数字顶上去**。
- 部署后：清 Cloudflare 缓存；抽查英文和阿语（RTL）页面无错位；回报改了哪些文件、新页 URL、Schema 验证结果。

---

## 第 1 页：UAE 项目供应商商业页（最接近询盘，先做）

- 主词：`aluminium windows and doors supplier for UAE projects`
- 次级词：aluminium window and door supplier UAE；aluminium windows supplier for UAE projects；project window supplier；custom aluminium windows and doors from China
- 建议 URL（按现有模式，Codex 如生成器要求不同格式可调整，但一旦发布就固定）：`https://vistafen.com/index.html?page=supply-uae-projects`，阿语版加 `&lang=ar`
- Title（约 60 字符）：`Aluminium Windows & Doors Supplier for UAE Projects | VistaFen`
- Meta description（约 155 字符）：`VistaFen supplies custom aluminium windows, doors and curtain wall systems for UAE villas and projects — from drawings and opening schedules to factory production and delivery. Send your drawings for a project review.`
- H1：`Aluminium Windows and Doors for UAE Projects — Supplied to Your Drawings`

### 页面结构（按顺序写，不要调换询盘入口的位置）

1. **首屏（给谁、解决什么）**：一句话定位——面向建筑师、开发商、总包、采购团队的中国工厂直供；不是零售、不做散户上门安装。
   链接：Systems 总览、Contact。
2. **我们供什么（系统清单，内链回系列页）**：casement、sliding window、sliding door、folding door、curtain wall、commercial door、entry door、skylight。
   每项一句话 + 链接，不写系列号当标题，不堆参数。
3. **项目流程（6 步，配一张流程图/步骤表）**：
   ① 发图纸和 opening schedule → ② VistaFen 审图、确认系统与性能目标 → ③ 系统确认与报价范围 →
   ④ 生产 → ⑤ 包装、海运、清关 → ⑥ 交付、现场配合资料。
   每步写清“这一步需要客户给什么、VistaFen 给回什么”。
4. **UAE 气候适配（写 VistaFen 自己的角度）**：高温、强 UV、沿海盐雾、沙尘密封、空调冷量保持；Low-E 玻璃、热断桥、EPDM 密封、粉末喷涂/阳极氧化的选择逻辑。
   不写具体 U 值、盐雾小时数等数字，除非已确认。内链到第 2 页（热断桥指南）和 resource 的 glass / climate 页。
5. **报价要发什么（表格，最重要的一节）**：项目地点、opening schedule、图纸、尺寸、目标系统、性能目标、时间节点。
   写明“资料越全，报价越快越准”，不要写“24 小时出价”这类未确认的承诺。
6. **FAQ（6 条，可见 + JSON-LD，答案用自己的口径写，不要抄 DERCHI / SAINTY 的原句）**：
   1. 你们供 UAE 项目的最小起订量是多少？——[待确认：按系统填 MOQ；未确认前写“按系统和项目量定，发图纸后确认”]
   2. 从确认到交付大概多久？——[待确认：生产周期 + 海运周期分开写；未确认前写“按系统和数量定”]
   3. 你们在 UAE 做本地安装吗？——[待确认：VistaFen 的供应范围是否含安装；未确认前写“工厂供货为主，安装由客户本地团队负责，VistaFen 提供图纸与配合资料”，不要宣称本地安装]
   4. 能按我们的图纸定制尺寸和颜色吗？——可以，定制范围写已确认的（尺寸、颜色、饰面），未确认的不列。
   5. 证书和测试报告怎么提供？——沿用 Resources 页口径：证书发给指定制造商，每单核查覆盖范围；测试报告按项目提供。
   6. 怎么开始？发什么资料？——复述第 5 节清单 + 邮箱/WhatsApp 入口。
7. **询盘 CTA**：`Discuss your project` 按钮 + 邮箱 + WhatsApp，三者都要，不要只留表单。

### 待确认清单（本页上线前必须清掉或改写成“按项目确认”）

- [ ] MOQ（按系统）
- [ ] 生产周期、包装、海运周期（分开写）
- [ ] 是否含 UAE 本地安装 / 现场服务范围
- [ ] 哪些系列已有 UAE / 海湾项目经验（有就写，无就删掉这句，不编项目）

---

## 第 2 页：热断桥指南（thermal break aluminium windows）

- 主词：`thermal break aluminium windows`
- 次级词：what is a thermal break in aluminium windows；thermal break vs non-thermal break；PA66 thermal break；thermal break windows for hot climates / villas
- 建议 URL（按现有 resource 模式，Codex 如生成器要求不同格式可调整，但一旦发布就固定）：`https://vistafen.com/index.html?page=resource&id=thermal-break`，阿语版加 `&lang=ar`
- Title：`Thermal Break Aluminium Windows: How They Work & When You Need Them | VistaFen`
- Meta description（约 155 字符）：`What is a thermal break in aluminium windows, how a PA66 strip cuts heat transfer, and when it matters most in hot climates. A project buyer's guide from VistaFen.`
- H1：`Thermal Break Aluminium Windows: How They Work & When You Need Them`

### 页面结构（VistaFen 自己的角度：海湾市场讲空调冷量，不是欧洲防寒）

1. **什么是热断桥（一句话 + 截面示意图）**：PA66 隔热条把铝型材的室内外两部分隔开，切断金属传热路径。
   示意图用自己的截面图，没有就不放图、不借用 AluK / Naview 的图。
2. **在热气候下它起什么作用**：重点讲三点——① 减少空调冷量通过窗框外泄；② 减少太阳得热传入室内；③ 降低内表面结露风险。
   不要写成“冬天保暖”为主，欧洲对手页才是那个角度。
3. **热断桥 vs 非热断桥（对照表，定性为主）**：

   | 对比项 | 有热断桥 | 无热断桥 |
   |---|---|---|
   | 传热路径 | PA66 条隔断，传热大幅降低 | 铝材直接导热 |
   | 空调能耗影响 | 有利于保持室内冷量 | 冷量流失更快 |
   | 内表面结露风险 | 较低（配合合适玻璃） | 较高 |
   | 成本 | 较高 | 较低 |
   | 适用场景 | 空调房间、大玻璃、别墅/高层 | 非空调空间、遮蔽露台、温和气候 |

   **U 值一栏不要出现在表里**，除非用户/工厂给了 VistaFen 系列的实测值。对手的 U 值（无断桥约 5.7–7.0、有断桥 1.4–2.8 W/m²K）**不要抄进本页当 VistaFen 的数值**；
   如需讲 U 值概念，单独写一句“U 值越低传热越少，具体以 VistaFen 系列的实测值为准”，不给数字。
4. **下单前要确认的 4 件事**：隔热条材质与宽度（PA66）、玻璃搭配（Low-E / 中空 / 氩气）、密封与五金、测试报告与证书范围。
   每项写“问供应商要什么”，不要写 VistaFen 未确认的等级。
5. **VistaFen 哪些系列带热断桥（只列已确认的）**：[待确认：列出带热断桥的系列名 + 链接到对应系列页；未确认的系列不列、不写“全系标配”]
6. **FAQ（6 条，可见 + JSON-LD）**：
   1. 所有的铝窗都需要热断桥吗？——按场景分：空调房间/大玻璃建议要，非空调空间可以不要。
   2. 热断桥能完全杜绝结露吗？——不能，玻璃、密封、室内湿度都有影响；只能降低风险。
   3. 热断桥窗一定节能吗？——框只是其中一部分，玻璃、尺寸、朝向、安装都要配合。
   4. PA66 和聚氨酯隔热条有什么区别？——只讲原理区别，不写 VistaFen 未用的材料当卖点。
   5. 热断桥会影响窗的强度或最大尺寸吗？——[待确认：按 VistaFen 系列写；未确认前写“按系列和配置定”]
   6. 怎么判断供应商给的是不是真的热断桥？——看截面、隔热条材质证明、测试报告，不要只看宣传语。
7. **结尾内链 + CTA**：链回 casement / sliding window 系列页、UAE 供应商页（第 1 页）、resource 的 glass 页；结尾放邮箱 + WhatsApp。

### 待确认清单（本页上线前必须清掉或改写）

- [ ] 带热断桥的系列清单（系列名 + 链接）
- [ ] 如有 VistaFen 系列实测 U 值，填上系列名 + 数值 + 测试标准；没有就整节不写数字
- [ ] 截面示意图（有自己的图就用，没有就不放，不借图）

---

## 验收（Codex 部署后回报）

1. 两页 URL（英文 + 阿语）、改了哪些源文件、是否已进 sitemap.xml。
2. Schema 验证结果（FAQPage + BreadcrumbList，0 错误/警告）。
3. 肉眼抽查：英文和阿语页面无错位；询盘入口（邮箱 + WhatsApp）可点；内链无死链。
4. 上文“待确认清单”每一项：填了真实值，还是已改写成“按项目确认”——逐项回报，不要只说“已处理”。

## 部署后用户要做的事（Juno 不代做）

1. 在 GSC 里对两页手动请求编入索引（只请求这两页，不要全站重提）。
2. 2–4 周后看 GSC：两页的曝光/点击/平均排名，再定第二批（幕墙节点指南 + 升降推拉门尺寸指南，约 11-26）。
3. 第二批开始前，提供 GSC 截图或数字，Juno 不猜排名。
