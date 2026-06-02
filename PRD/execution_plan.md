# 清韻工夫茶 - Shopify 独立站执行计划 (Execution Plan)

> 本文档基于已确认的 PRD 与设计概念图进行原子级开发任务拆解。
> 当前状态：进入首页与列表页的代码开发执行阶段。

## 1. 首页 (Home Page) 改造
### 1.1 Hero Section 定制 (2-10 分钟)
- **目标**：优化首屏海报区（Hero），使其文本使用 Noto Serif SC 居中或合理布局，应用半透明香槟金/深灰叠加，去除不必要的暗沉边框，按钮样式调整为极简（去背景，仅保留香槟金边框和文字）。
- **文件**：`templates/index.json` (调整配置) 或 `sections/hero.liquid` / 基础按钮 CSS。
- **验证**：预览 Shopify 首页，确认首屏文字具有优雅的衬线体，按钮风格为“香槟金边框+通透底”。

### 1.2 产品列表区 (Featured Collection) UI 优化 (5-10 分钟)
- **目标**：重构 `product-list` 样式。移除卡片的默认灰色背景，改为纯白或透明，商品图片周围不留多余内边距（Edge-to-edge）。标题字体改为衬线体并居中，价格信息跟随居中。
- **文件**：`blocks/_product-card.liquid` 或其相关的 snippet (`_product-card-gallery`, `product-title`, `price`)，以及 `base.css`。
- **验证**：首页的商品流卡片展示干净无边框，居中对齐，排版间距合理。

### 1.3 “品牌故事”图文模块 (Image with Text) 增加 (5-10 分钟)
- **目标**：在 `index.json` 中配置并激活一套左右图文混排的模块，插入占位茶文化图片，文字描述使用 Noto Serif SC 标题和 Inter 正文，排版留白变大。
- **文件**：`templates/index.json`。
- **验证**：首页在推荐商品下方出现极简的图文模块，且支持后台自定义内容。

## 2. 商品列表页 (Collection Page) 改造
### 2.1 列表页 Banner 优化 (5-10 分钟)
- **目标**：去除多余底色或图片覆盖，确保集合名称（Collection Title）使用 `h1` 衬线字体展示在纯米白背景上，极简优雅。
- **文件**：`sections/main-collection-banner.liquid` 或相应 json 配置。
- **验证**：访问 `/collections/all`，顶部清爽通透。

### 2.2 筛选器与排序控件 (Filters & Sorter) 简化 (5-10 分钟)
- **目标**：去除边框，使其呈现为极简的下划线样式或轻量下拉菜单。
- **文件**：`blocks/filters.liquid` / `sections/main-collection-product-grid.liquid` / CSS。
- **验证**：下拉筛选控件样式与全局风格统一，无杂乱外边框。

## 3. 商品详情页 (Product Page) 改造
### 3.1 详情页 Gallery (画廊) 调整 (5-10 分钟)
- **目标**：左侧主图及缩略图布局去边框，采用类似画报级的贴边排版。
- **文件**：`blocks/_product-media-gallery.liquid` 或 `sections/main-product.liquid`。
- **验证**：进入任意商品页，查看左侧图片区是否干净。

### 3.2 购买区 (Buy Box) 信息重排 (5-10 分钟)
- **目标**：右侧信息使用统一的间距，商品标题增大并使用 Noto Serif SC，价格使用香槟金/深灰强调，加入购物车按钮采用通栏（100%宽）且底色与文字颜色高亮对比（香槟金主色）。
- **文件**：`blocks/buy-buttons.liquid`, `blocks/product-title.liquid` / CSS。
- **验证**：进入详情页，右侧购买流程顺畅且符合现代极简风格。

## 4. 响应式与交互体验优化 (5-10 分钟)
- **目标**：确保所有页面的移动端（手机模式下）边距至少有 20px，字体大小不突兀；抽屉式购物车 (Cart Drawer) 弹出时的按钮颜色同步为香槟金。
- **文件**：`base.css`。
- **验证**：使用 Chrome 开发者工具模拟移动端测试所有流程。
