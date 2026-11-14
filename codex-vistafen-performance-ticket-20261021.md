# VistaFen 性能优化工单 — 给 Codex（2026-10-21）

## 背景（PageSpeed Insights 移动端实测，2026-10-21 10:41，Moto G + 低速 4G 节流）
- 性能 72 / 无障碍 92 / 最佳做法 100 / SEO 100
- **LCP 5.8s（红，主要问题）** / FCP 2.5s / Speed Index 5.2s / TBT 0ms / CLS 0.013
- 目标：**LCP < 2.5s，性能分 ≥ 90**；TBT、CLS 不许变差

## 要改的 4 项（按优先级）

### 1. 图片传送优化（Lighthouse 预估省 527 KiB，最重要）
- 首屏 hero 大图（建筑图，即 LCP 元素）转 **WebP**（保留 JPG 兜底），质量 75–82，不许肉眼可见变糊
- 按断点出图：移动端用 ≤800px 宽版本，桌面端用 ≤1920px；用 `srcset`/`sizes` 或 `<picture>`，**禁止拿桌面大图给手机端**
- 其余产品图/列表图同样转 WebP + 按展示尺寸裁切；全部图片加 `loading="lazy"`（hero 图除外，见第 2 条）
- 全站图片总传输量目标：首页 ≤ 1.2 MB

### 2. LCP 图片优先加载
- hero 图加 `fetchpriority="high"`，并在 `<head>` 加 `<link rel="preload" as="image">`（指向移动端实际加载的那张图）
- hero 图不许 lazy

### 3. 消除渲染阻塞（预估省 1,650 ms）
- 非首屏 CSS 异步加载或合并精简；关键 CSS 内联到 `<head>`
- 非必要 JS 移到页尾或加 `defer`；首屏不执行的脚本一律不阻塞

### 4. 缓存策略（预估省 211 KiB）
- 静态资源（图片/CSS/JS/字体）设 `Cache-Control: max-age=31536000, immutable`（带版本指纹的文件）或在 Cloudflare 侧设 Browser Cache TTL + Edge Cache TTL
- HTML 不长缓存

## 约束（不许动）
- 只做压缩/格式/加载顺序/缓存，**不换图、不改版式、不改文案、不改页面结构**
- 英文站和阿拉伯站（RTL）都要生效，阿拉伯页面不能因为改 CSS/JS 加载方式出现错位
- 询盘链路不动：表单 mailto（primewindows@vistafen.com）和 wa.me/8617722594432 链接保持原样

## 验收
- 改完在 PageSpeed Insights 重跑移动端：首页 LCP < 2.5s、性能 ≥ 90；再抽查 1 个产品页同样达标
- 肉眼对比首页改版前后截图：视觉零差异（允许的唯一差异是没有差异）
- 回报：改了哪些文件、hero 图改前/改后体积、重跑后的四项指标截图
