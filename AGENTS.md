# 项目协作说明

## 用户信息

- 用户名字：红豆。
- 职业：程序员。
- 用户自述：很猛，而且喜欢新技术。
- 本文件使用中文，按清晰的标题和条目维护。

## 项目概况

- 当前项目是「巷里小馆」江南风味餐厅的单页展示网站。
- 项目目录名为 `codex-shop`，但当前代码实现的是餐厅首页，没有购物车或商品交易功能。
- npm 包名：`xiangli-restaurant-homepage`；项目为私有包，采用 ES Modules。
- 页面以中文为主，包含少量英文装饰文案。
- 当前没有后端、接口请求、数据库、路由库或全局状态管理库；菜品等内容直接写在组件中。

## 技术栈与运行命令

- Vue 3（`package.json` 声明 `^3.5.13`），使用 Vue 单文件组件，逻辑采用 `<script setup>`。
- Vite 6（声明 `^6.1.0`），通过 `@vitejs/plugin-vue`（声明 `^5.2.1`）处理 Vue 组件。
- 使用 JavaScript 和原生 CSS，当前没有 TypeScript 或 UI 组件库。
- 使用 npm，已有 `package-lock.json`，更新依赖时保持锁文件同步。
- 安装依赖：`npm install`；按锁文件安装可使用 `npm ci`。
- 本地开发：`npm run dev`。
- 生产构建：`npm run build`，输出目录为 `dist/`。
- 预览构建结果：`npm run preview`。
- 当前没有配置测试、代码检查或格式化脚本；不要假设存在 `npm test` 或 `npm run lint`。

## 主要文件与职责

- `index.html`：页面标题、中文语言标识、描述、主题色、字体加载及应用挂载节点。
- `vite.config.js`：Vite 配置，目前仅启用 Vue 插件。
- `src/main.js`：创建 Vue 应用，导入全局样式，挂载到 `#app`。
- `src/App.vue`：按顺序组合页头、首屏、品牌故事、菜单、空间介绍、到店信息和页脚。
- `src/styles.css`：全站样式、颜色与字体变量、布局、交互效果和响应式规则。
- `src/components/SiteHeader.vue`：品牌、锚点导航、预订入口及移动端导航展开状态。
- `src/components/HeroSection.vue`：首屏标题、主图、菜单与故事入口。
- `src/components/StorySection.vue`：品牌故事，锚点 `#story`。
- `src/components/MenuSection.vue`：时令菜品卡片，锚点 `#menu`；菜品数组在该组件中维护。
- `src/components/SpaceSection.vue`：餐厅环境介绍，锚点 `#space`。
- `src/components/VisitSection.vue`：营业时间、地址、电话预订，锚点 `#visit`。
- `src/components/SiteFooter.vue`：品牌与版权信息。

## 现有交互与内容边界

- 导航通过页面内锚点跳转，首页锚点 `#top` 位于主内容节点。
- 移动端导航使用 Vue `ref` 管理展开状态，点击导航链接或预订入口后收起。
- 电话预订使用 `tel:` 链接，没有在线预订表单或提交接口。
- 「查看完整菜单」目前跳转到到店信息 `#visit`，没有独立完整菜单页面。
- 首屏的 `01 / 04` 是静态装饰文字，当前没有轮播实现。
- 地址、电话、营业时间与菜品价格都是页面现有文案，未经实际经营信息核实，不应当作已验证事实。

## 视觉与资源

- 整体风格为温暖、自然的江南餐厅展示页，使用米白背景、绿色主色和橙棕色强调。
- 主要色彩在 `src/styles.css` 的 `:root` 中维护：`--paper`、`--ink`、`--muted`、`--green`、`--orange`、`--line`。
- 字体使用 Noto Serif SC 与 DM Sans，已配置本地字体回退；在线字体从 Google Fonts 加载。
- 页面图片通过 `images.unsplash.com` 的远程链接加载，图片与在线字体的展示受网络可用性影响。
- 响应式断点为 `900px` 和 `640px`；小屏下导航折叠、菜品单列、主要内容纵向排列。

## 修改与验证建议

- 修改相应版块时优先定位对应组件；全局视觉调整集中检查 `src/styles.css`。
- 保持导航链接与版块锚点一致，保留现有图片替代文本和移动导航的无障碍属性。
- 修改页面功能或样式后运行 `npm run build`；涉及布局时同时检查桌面和移动端显示，涉及导航时检查展开、收起和锚点跳转。
- `node_modules/`、`dist/` 和 `.vite/` 已被忽略，不应直接修改这些目录来实现源码变更。
- `.env`、`.env.*` 与 `*.local` 等本地配置已被忽略，部分示例环境文件除外；不要将密钥写入源码或本文件。
- 后续更新本文件时，以实际源码和配置为依据，区分已实现能力与计划功能。

