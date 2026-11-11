# @melt-js/demo-vue3

Vue 3 + Vite 5 的 hel 宿主（消费方）示例，消费 [`comps-vue3`](../comps-vue3)。

页面使用 **vue-router（hash 模式）** 把示例拆成多个可切换的页面，顶部导航栏同时显示当前示例的简介，示例区右上角有**下载示例**与**全屏**两个按钮（下载按钮导出一份单文件「HTML + CDN」示例，用于演示 hel 的接法；全屏按钮只放大当前示例的组件预览区，基于 `vue-fullscreen` 的 `pageOnly + teleport` 模式）。

| 项 | 值 |
| --- | --- |
| npm 包名 | `@melt-js/demo-vue3` |
| unpkg 入口 | `https://unpkg.com/@melt-js/demo-vue3/dist/index.html` |
| 端口 | `30020` |
| 消费的远程组件 | `comps-vue3`（开发 `http://localhost:20020` / 生产 unpkg） |
| 路由 | `vue-router@4.6.4`，hash 模式 |
| 全屏 | `vue-fullscreen@5.1.2`，`pageOnly` + `teleport`（不调用浏览器原生全屏） |

## 示例路由

| 路由 | 导航文案 | 内容 |
| --- | --- | --- |
| `#/` | 简介 | demo 概览：依赖、端口、远端地址与示例入口 |
| `#/host` | 主应用 | 宿主自己的计数按钮，用来对照远程组件的行为 |
| `#/remote` | 远程组件 | `preFetchLib` 加载的 `comps-vue3` `HelloWorld` |
| `#/circular-menu` | 圆形菜单 | `CircularMenu`：随页面滚动 / 容器内吸顶两个示例 + 属性面板（wheel 半环、fan 整环，定位可切 relative / sticky / fixed / absolute） |
| `#/magnetic-button` | 磁吸按钮 | `MagneticButton`：默认参数与高强度参数并排对比 + 属性面板（文案 / 强度 / 主色 / 光点） |
| `#/spotlight-button` | 聚光灯按钮 | `SpotlightButton`：紧光斑与宽光斑对比 + 属性面板（文案 / 配色 / 光斑半径） |
| `#/glow-border` | 流光边框 | `GlowBorder`：160 / 240 / 320 三种尺寸对比 + 属性面板（尺寸 / 圆角 / 厚度 / 配色 / 时长 / 光晕） |
| `#/typewriter` | 逐字打印 | `Typewriter`：两行文案 + `restart()` / `finish()` 手动控制 + 属性面板（文案 / 字速 / 延迟 / 循环 / 光标） |
| `#/tilt-card` | 倾斜卡片 | `TiltCard`：6° / 14°(+反光) / 20° 三张卡片对比 + 属性面板（角度 / 放大 / 圆角 / 反光 / 阴影） |
| `#/floating-label-input` | 浮动标签 | `FloatingLabelInput`：默认 / 换主色 / 带初始值三态对比 + 属性面板（文案 / 类型 / 主色 / 高度 / 禁用） |
| `#/password-input` | 密码框 | `PasswordInput`：带标签 / 无标签 / 关掉切换按钮 + 属性面板（文案 / 占位 / 主色 / toggleable / autocomplete） |
| `#/expand-search` | 收缩搜索 | `ExpandSearch`：默认与紧凑两种尺寸，回车派发 `search` + 属性面板（占位 / 主色 / 收起宽度 / 圆角 / 高度 / 清除按钮） |
| `#/cyber-input` | 故障输入框 | `CyberInput`：完整故障效果（页面另配矩阵雨背景）与关掉故障的安静版 + 属性面板（文案 / 霓虹色 / 三个效果开关） |
| `#/corgi-input` | 柯基输入框 | `CorgiInput`：两只不同尺寸的小狗对比 + 属性面板（气泡文案 / 跟随开关 / 眼睛幅度 / 尺寸） |
| `#/grid-loading` | 九宫格 loading | `GridLoading`：默认 / 换色放大 / 带文案三种 + 属性面板（尺寸 / 颜色 / 周期 / 错开 / 间距 / 圆角 / 暂停） |
| `#/gooey-balls-loading` | 元素交融 | `GooeyBallsLoading`：多彩 / 单色 / 关掉 gooey 三态对比 + 属性面板（轨道 / 球径 / 球数 / 周期 / 融合开关） |
| `#/dna-loading` | DNA loading | `DnaLoading`：12 对与 20 对节点、两套配色对比 + 属性面板（行数 / 摆幅 / 周期 / 双色 / 文案） |
| `#/neon-ring-loading` | 霓虹环 | `NeonRingLoading`：自动假进度与受控进度（滑杆驱动）对比 + 属性面板（尺寸 / 四色 / 倍速 / auto / progress） |
| `#/gear-loading` | 齿轮联动 | `GearLoading`：原尺寸 / 缩小加速 / 关掉蒸汽三种 + 属性面板（尺寸 / 倍速 / 进度条 / 蒸汽 / 文案） |
| `#/vortex-loading` | 粒子漩涡 | `VortexLoading`：默认 / 换色相加粒子 / 关拖尾连线三种 + 属性面板（边长 / 数量 / 色相 / 倍速 / 连线 / 拖尾） |
| `#/water-ball-loading` | 水球进度 | `WaterBallLoading`：自动水位与滑杆驱动的受控水位对比 + 属性面板（球径 / 双色 / auto / progress / 时长 / 波浪倍速 / 水滴） |
| `#/hourglass-loading` | 沙漏 | `HourglassLoading`：10s / 90px 快速 / 160px 冷色三档 + 属性面板（宽度 / 周期 / 沙色 / 木框色） |
| `#/cube-wave-loading` | 盒子波场 | `CubeWaveLoading`：5×5 / 换色 / 7×7 大矩阵三种 + 属性面板（边长 / 行列数 / 色相 / 节奏） |
| `#/jelly-loading` | 果冻弹跳 | `JellyLoading`：5 只 / 8 只更快 / 关掉表情三种 + 属性面板（画布宽 / 数量 / 速度 / 错峰 / 表情） |
| `#/domino-loading` | 多米诺 | `DominoLoading`：14 / 20 张更慢 / 关掉进度条三种 + 属性面板（画布宽 / 张数 / 速度 / 进度条 / 文案） |
| `#/slide-auth-panel` | 拟态登录 | `SlideAuthPanel`：登录态与注册态左右互换滑动 + 属性面板（模式 / 主色 / 高度 / 滑动时长 / 两套文案） |
| `#/terminal-auth` | 终端登录 | `TerminalAuth`：荧光绿与青色两套、可切登录/注册 + 属性面板（模式 / 荧光色 / 标题 / 按钮文案 / 强度条 / 日志 / 扫描线） |
| `#/wheel-menu-button` | 轮盘按钮 | `WheelMenuButton`：可拖拽的悬浮轮盘，拖动不误触、轻点展开环形菜单 + 属性面板（尺寸 / 半径 / 配色 / 拖拽阈值 / 贴边留白 / 初始位置） |
| `#/photo-sphere` | 3D 照片球 | `PhotoSphere`：12 张渐变图组成的球体，拖动旋转 / 点击放大 / 本地上传替换 + 属性面板（尺寸 / 缩略图 / 半径 / 自转 / 灵敏度 / 摩擦 / 压缩上限） |
| `#/warp-starfield` | 星际穿越 | `WarpStarfield`：可交互的曲速星流（指针控方向 / 按住加速 / 滚轮调速）+ 低高速两个静态对比 + 属性面板（星数 / 巡航 / 倍率 / 调速区间 / 交互 / HUD / 星云） |
| `#/china-route-map` | 地图轨迹 | `ChinaRouteMap`：中国地图上按经纬度画路线，点地图加点、缩放平移、播放镜头跟随 + 属性面板（时长 / 跟随倍数 / 开关项 / 主色） |
| `#/split-code-preview` | 界面切代码 | `SplitCodePreview`：拖动分割线在渲染结果与源码间切换，右侧代码可编辑并实时重渲染 + 属性面板（split / glitch / 圆角 / 主色） |
| `#/book-flip` | 书本翻页 | `BookFlip`：4 张内页 + 首尾封面，点击 / 按钮 / 键盘翻转，另有小尺寸与自动播放两个对比 + 属性面板（尺寸 / 时长 / 纸色 / 页码 / 自动播放） |
| `#/minecraft-chest` | Minecraft 箱子 | `MinecraftChest`：拖动环视、点击开盖的方块箱，另有去场景只读与小一号预开两个对比 + 属性面板（六种尺寸 / 缩放 / 视角 / 交互 / 音效 / 场景） |
| `#/bilibili-banner` | B站横幅 | `BilibiliBanner`：从 bilibili-banner-master 的 Vue 版本迁移的 23 套节日 banner，每个主题一个按钮切换，多层图片 / 视频跟随指针横向视差 + 属性面板（主题下拉 / 高度 / logo / 底色） |
| `#/film-roll` | 旅行胶卷 | `FilmRoll`：12 格横向胶片，拖动带惯性拉扯与重影、松手吸附，时间轴跳转 + 全屏预览以及两个小尺寸变体 + 属性面板（单格尺寸 / 间距 / 当前格 / 开关项） |
| `#/rope-gallery` | 绳串图片 | `RopeGallery`：7 张照片挂在会晃的绳子上，风强度滑杆接 `v-model:wind`、可拖动拉绳，另有小尺寸 / 大风两个对比 + 属性面板（风强度 / 照片尺寸 / 两端留白 / 开关项） |
| `#/compare-slider` | 图片对比 | `CompareSlider`：原片 / 调色后对比卡，可上传两张图、交换、重置、自动巡航，另有 4:3 与 1:1 两个变体 + 属性面板（位置 / 宽高比 / 把手 / 主色 / 自动巡航） |
| `#/poster-collage` | 海报拼贴 | `PosterCollage`：1400×800 设计稿上 12 层人物拼贴，悬停放大并置顶，另有 6 层与「带底图」两个变体 + 属性面板（画布尺寸 / 底图 / 放大倍数 / 层级偏移） |
| `#/lift-card` | 立体卡片 | `LiftCard`：hover 时底板仰起、照片沿 Z 轴弹出、倒影浮现，三张不同参数 + 一张大卡 + 属性面板（尺寸 / 仰角 / 弹出距离 / 配色 / 倒影 / 强制展开） |

约定：

- **hash 模式**：demo 的构建产物会通过 unpkg 上的 `dist/index.html` 打开，history 模式在那种静态文件路径下会 404。
- 路由清单在 `src/router/index.ts`，每条路由的 `meta.title` / `meta.description` 同时驱动导航栏 tab 与下方那行简介；新增示例只要加一条路由。
- 全屏按钮只把当前示例标记为 `data-demo-preview` 的组件预览区送进全屏，页面标题、简介、说明与页脚都留在屏幕外；全屏借用 `vue-fullscreen` 5.x 的 `pageOnly + teleport` 模式：预览区临时挂到 body、用 fixed 铺满视口，退出时还原到页面原位置，不调用浏览器原生 Fullscreen API（iframe 内也可用）。预览区右下角提供「退出全屏」浮层按钮，Esc 也可退出；切换路由时会自动退出并还原。
- 全屏按钮左侧的「下载示例」会下载 `src/templates/hel-micro-cdn.html`（单文件示例：Vue 与 hel-micro 走 CDN，组件由 `preFetchLib` 在运行时从 unpkg 拉取），用于对外演示 / 推广 hel 的接法。示例源码用 Vite 的 `?raw` 内联进产物后以 Blob 下载，不依赖网络、也不受 `base` 影响，`file://` 下打开 demo 同样可下载；改示例只需改那个 html 文件。
- 需要全屏的示例在组件预览区外包一层 `<DemoPreview>`；简介页没有预览区，在路由 `meta` 里标记 `fullscreen: false`，工具栏不显示全屏按钮。
- 每个组件示例都用 `<LevaPlayground>` 包一层 leva 实验台（左侧组件 + 右侧 `libs-vue3-leva` 的 `PropsPanel`），面板值通过 `v-bind` 实时写回组件；不再有单独的「属性面板」tab。`LevaPlayground` 支持 `presets` / `listeners` / `slotHtml` / `stage-style`。

## 文件结构

```
demo-vue3/src
├── App.vue                   # demo 外壳：导航栏 + 示例舞台（下载示例 / 全屏按钮）+ router-view
├── components/
│   ├── DemoNavbar.vue        # 顶部导航栏：示例 tab + 当前示例简介
│   ├── DemoPreview.vue       # 组件预览区：全屏目标 + 「退出全屏」浮层按钮
│   ├── DownloadExampleButton.vue # 下载 HTML + CDN 示例按钮（全屏按钮左侧）
│   ├── LevaPlayground.vue    # 单个示例的 leva 实验台：组件 + schema → PropsPlayground
│   ├── MatrixRain.vue        # 赛博朋克页 / 终端登录页的矩阵雨背景（页面氛围，不属于组件）
│   └── ScreenfullButton.vue  # 示例区全屏按钮
├── composables/
│   └── useDemoFullscreen.ts  # vue-fullscreen 的 pageOnly + teleport 封装（provide/inject）
├── configs/
│   ├── app.ts                # demo 展示信息（名称 / 端口 / unpkg 入口）
│   └── remote.ts             # 远程组件地址与 preFetchLib（Promise 复用）
├── router/index.ts           # 示例路由（hash 模式）
├── styles/demo-shell.css     # 外壳样式（导航栏 / 舞台 / 按钮 / 全屏 / 通用排版）
├── templates/
│   └── hel-micro-cdn.html    # 「下载示例」导出的单文件 HTML + CDN 示例源码
├── style.css                 # 变量与全局重置
└── views/                    # OverviewView / HostView / RemoteView / CircularMenuView / MagneticButtonView / SpotlightButtonView / GlowBorderView / TypewriterView / TiltCardView / FloatingLabelInputView / PasswordInputView / ExpandSearchView / CyberInputView / CorgiInputView / GridLoadingView / GooeyBallsLoadingView / DnaLoadingView / NeonRingLoadingView / GearLoadingView / VortexLoadingView / WaterBallLoadingView / HourglassLoadingView / CubeWaveLoadingView / JellyLoadingView / DominoLoadingView / SlideAuthPanelView / TerminalAuthView / WheelMenuButtonView / PhotoSphereView / WarpStarfieldView / ChinaRouteMapView / SplitCodePreviewView / BookFlipView / MinecraftChestView / FilmRollView / RopeGalleryView / CompareSliderView / PosterCollageView / LiftCardView
```

## 关键流程

1. `src/main.ts`：`bindVueRuntime({ Vue })` 把宿主 vue 挂到 `window.Vue`，远程组件 external 的 `vue` 会复用这一份（少了这一份会出现双 vue，表现为远程组件点击后视图不更新）；随后在入口处调用 `loadRemoteLib()` 预加载远程组件，就绪后再挂载宿主。
2. `src/configs/remote.ts`：按 `import.meta.env.PROD` 选择远端地址——生产构建指向 unpkg 上的 `hel-meta.json`，本地开发指向 `http://localhost:20020`，可用 `VITE_REMOTE_HOST` 覆盖。`loadRemoteLib()` 内部调用 `preFetchLib('comps-vue3', { custom: { host } })`：host 为 `hel-meta.json` 时直接取元数据，本地 dev server 没有该文件时解析 `index.html`。
3. `src/router/index.ts` + `src/loadApp.ts`：创建 hash 路由并在 `createApp(App).use(router)` 时挂载；`#/host`、`#/remote` 等示例按路由懒加载。
4. `src/views/RemoteView.vue`：`defineAsyncComponent` 复用入口处已预加载的同一个 Promise，渲染远程组件的 `HelloWorld`。
5. `src/composables/useDemoFullscreen.ts` + `src/components/DemoPreview.vue`：`App.vue` 用 `provideDemoFullscreen()` 创建唯一一份 `useFullscreen` 控制器（`pageOnly`、`teleport`、`fullscreenClass: 'is-demo-fullscreen'`），`ScreenfullButton` 与 `DemoPreview` 通过 `useDemoFullscreen()` 共用它，全屏状态与「退出全屏」按钮始终同步；全屏目标由 App 解析为当前页面的 `[data-demo-preview]`。

> `vite build` 的产物会自动从 unpkg 加载已发布的 `comps-vue3`；`vite dev` 仍走本地 20020，无需手动改 `host`。

## 本地开发

```bash
# 终端 1：起远程组件（20020）
pnpm comps-vue3:dev

# 终端 2：起宿主（30020）
pnpm demo-vue3:dev
```

打开 <http://localhost:30020> ，`远程组件` 示例会渲染 `comps-vue3` 的 `HelloWorld` 组件。

也可以让宿主指向已构建的远程产物：

```bash
pnpm comps-vue3:build:local && pnpm comps-vue3:preview   # 20020 上跑 hel_dist
pnpm demo-vue3:dev
```

## 构建 / 发布

```bash
pnpm demo-vue3:build                                  # 产出 dist/
pnpm --filter @melt-js/demo-vue3 run publish:stage    # build → npm stage 暂存，等待 2FA 审批
```

- `vite.config.ts` 的 `base` 为 `./`，发布后 unpkg 上的 `dist/index.html` 可直接加载同目录资源；hash 路由同样可用。
- `files` 白名单只发布 `dist/` 与 README。
- 生产构建自动使用 `https://unpkg.com/@melt-js/comps-vue3/hel_dist/hel-meta.json`，本地开发自动使用 `http://localhost:20020`；也可用 `VITE_REMOTE_HOST` 覆盖。
