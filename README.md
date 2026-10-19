# LX Music · 青瓷 (Ceru Jade)

基于 [lyswhut/lx-music-desktop](https://github.com/lyswhut/lx-music-desktop) **v2.12.6** 与 [lyswhut/lx-music-mobile](https://github.com/lyswhut/lx-music-mobile) **v1.9.1** 的非官方 UI 改版。

**当前版本：`v2.12.6-ceru.6`（青瓷改版 rev.6）**

![主界面](screenshots/主界面.png)

## 下载

**Release：** https://github.com/baipiao5555/lx-music-ceru-jade/releases/tag/v2.12.6-ceru.6

| 平台 | 文件 | 说明 |
| --- | --- | --- |
| Windows x64 | `lx-music-desktop-v2.12.6-x64-Setup.exe` | NSIS 安装包，116 MB，未做商业签名 |
| Android arm64 | `lx-music-mobile-v1.9.1-ceru3-universal.apk` | 28 MB，推荐，含新移动端 UI |
| Android arm64 | `lx-music-mobile-v1.9.1-ceru3-arm64.apk` | 14 MB，体积更小，含新移动端 UI |

SHA-256：

- Windows：`2219d22cd1cdaf0257bef3aa08c4fcd641d55354d2ce12e2a3f043896eba0adc`
- Android universal：`5d4b80904d45b7d65984009fe09b1798c7f812c8fb8366ed6cc7889c9a037dd2`
- Android arm64：`55429d4ecc23d0ecedd54131bf22ccb2ae01744f4e414907766d056d0688052a`

## 版本记录

### rev.6（`v2.12.6-ceru.6`）

- 播放条改为左 / 中 / 右三段式：左侧封面与歌曲信息，中间上一首 / 播放 / 下一首，右侧时间与功能按钮。
- 修复播放条歌曲信息区被误加渐变背景、出现绿色横线的问题，播放键组严格居中。
- 收紧窗口关闭按钮右侧留白（工具栏右内边距 16px → 6px，窗口按钮宽度 46px → 38px）。
- 工具栏改为三列栅格，窄窗口下搜索框自动收缩，不再与右侧按钮重叠。
- 热门歌单恢复默认「最新」排序，避免部分音乐源「最热」接口加载失败。
- 重新打包 Windows 安装包，SHA-256 已更新；移动端 APK 与 rev.3 相同。

### rev.5（`v2.12.6-ceru.5`）

- 「发现音乐」页按澜音 CeruMusic 界面重做：移除筛选胶囊、导入歌单、来源选择，保留大标题与「热门歌单Top36」。
- 歌单卡片改为白色圆角卡片（整块封面、标题、精选歌单、播放量、曲目数胶囊），四列自适应网格。
- 热门歌单默认「最热」排序。
- 修复首页与侧栏文字下划线。
- 修复右侧内容区宽度塌陷（`#body` id 与页面 `<body>` 冲突）。
- 修复歌单卡片点击无反应，实机验证可进入歌单详情。
- 启动固定进入「发现」页，不再恢复上次的搜索页或详情页。
- 搜索框自适应宽度，窄窗口下不再与窗口按钮重叠。
- 重新打包 Windows 安装包，SHA-256 已更新；移动端 APK 与 rev.3 相同。

### rev.4（`v2.12.6-ceru.4`）

- 桌面端对齐在线预览：Ceru Music 品牌、发现 / 本地 / 最近导航、我的歌单圆点、底部迷你封面卡片、热门歌单 Top36。
- 播放条改为悬浮圆角卡片，加入青绿圆形播放按钮。
- 启动固定进入「发现」页，不再恢复上次的搜索页。
- 重新打包 Windows 安装包，SHA-256 已更新。
- 移动端 APK 与 rev.3 相同。

### rev.3（`v2.12.6-ceru.3`）

- 移动端实际 APK 落地青瓷 UI 第一版：默认「发现」页、抽屉品牌头与胶囊导航、两列歌单卡片、悬浮播放条、搜索页品牌空状态。
- 抽屉顺序调整为 发现 / 搜索 / 排行榜 / 我的列表 / 设置，启动默认进入发现。
- 新增移动端布局补丁 `0003-feat-ui-ceru-mobile-layout.patch`。
- 桌面端安装包与 rev.2 相同。

### rev.2（`v2.12.6-ceru.2`）

- 桌面端启动默认进入「歌单」青瓷首页，不再先落在搜索页。
- 首次启动不再弹出版本更新日志。
- 重新打包 Windows 安装包，SHA-256 已更新。
- 新增桌面端 + 手机端 UI 概念预览，见下方「设计预览」。
- 移动端 APK 仍为主题版，完整布局改版待落地。

### rev.1（`v2.12.6-ceru.1`）

- 桌面端青瓷 UI 首版、Windows 安装包与 Android 主题版 APK。

## 本次改动

### 桌面端（完整 UI 改版）

- 新增「青瓷」主题：青绿主色、浅色玻璃主面板、柔和渐变背景，并设为默认主题。
- 启动固定进入「发现」页（原歌单页），不再恢复上次搜索页或详情页；首次启动不弹出版本更新日志。
- 侧栏：Ceru Music 品牌（青瓷 · CERU JADE）、发现 / 本地 / 最近导航、我的歌单圆点。
- 首页：`发现音乐` 大标题、热门歌单 Top36、四列白色歌单卡片（整块封面 + 精选歌单 + 播放量 + 曲目数）、悬停上浮。
- 顶栏：返回/前进、自适应搜索框、排行榜/设置/窗口按钮；窗口变窄时搜索框自动收缩。
- 悬浮圆角播放条，青绿圆形播放按钮，播放键组居中，时间与功能按钮分列两侧。
- 播放详情页：黑胶唱片 + 唱臂 + 玻璃歌词面板样式。
- 主题名称的中/繁/英/韩翻译。

### 移动端（青瓷 UI 第一版）

- 新增「青瓷」主题并设为默认：青绿主色、浅色主背景。
- rev.3 已落地移动端 UI 第一版：默认「发现」页、抽屉品牌头与胶囊导航、两列歌单卡片、悬浮播放条、搜索页品牌空状态。
- 底部导航概念稿（发现 / 正在播放）尚未完全实现；当前 APK 使用抽屉导航。

## 设计预览（概念稿）

桌面端 + 手机端概念稿：

![桌面 + 手机](design/preview.jpg)

- 桌面端：真实封面、两行歌单、筛选胶囊、悬浮播放条。
- 手机端 · 发现：每日精选大卡、横滑歌单、最近播放、迷你播放器。
- 手机端 · 正在播放：黑胶 + 唱臂、歌词高亮、完整控制。

手机端单独查看：[发现页](design/mobile-discover.jpg) · [正在播放页](design/mobile-player.jpg)

在线预览（GitHub Pages）：https://baipiao5555.github.io/lx-music-ceru-jade/design/preview.html

> 说明：桌面端 rev.6 已按澜音 CeruMusic 界面重做发现页，并将播放条改为居中三段式；移动端 rev.3 为第一版抽屉式 UI，底部导航 / 黑胶播放页尚未全部实现。

## 为什么是补丁仓库

Mimosa 的 Git 安全门禁在提交前扫描到上游源码中的 12 个既有高危项（音乐源加密、同步路径处理等），按规则阻止了完整源码提交。本仓库只包含本次 UI/主题改动，避免重新分发上游高风险代码；上游项目仍采用 Apache-2.0 许可。

## 补丁文件

- `patches/0001-feat-ui-ceru-jade.patch`：桌面端青瓷 UI，基于官方 v2.12.6。
- `patches/0002-feat-ui-ceru-mobile-theme.patch`：移动端青瓷主题，基于官方 v1.9.1。
- `patches/0003-feat-ui-ceru-mobile-layout.patch`：移动端青瓷布局，基于官方 v1.9.1。

## 应用补丁

### 桌面端

```bash
git clone --depth 1 --branch v2.12.6 https://github.com/lyswhut/lx-music-desktop.git
cd lx-music-desktop
git apply /path/to/patches/0001-feat-ui-ceru-jade.patch
```

Windows 构建参考：

```bash
npm install --ignore-scripts --registry=https://registry.npmmirror.com
node build-config/postinstall.js
# 将 Electron 42.11.6 win32-x64 运行时解压到 node_modules/electron/dist
# 写 node_modules/electron/path.txt，内容为 electron.exe（不要带换行）
npm run build
.\node_modules\electron\dist\electron.exe dist\main.js
```

### 移动端

```bash
git clone --depth 1 --branch v1.9.1 https://github.com/lyswhut/lx-music-mobile.git
cd lx-music-mobile
git apply /path/to/patches/0002-feat-ui-ceru-mobile-theme.patch
git apply /path/to/patches/0003-feat-ui-ceru-mobile-layout.patch
npm run build:theme
npm install --legacy-peer-deps --registry=https://registry.npmmirror.com
```

Android 构建环境：JDK 17、Android SDK Platform 36、Build-Tools 35.0.0、NDK 26.1.10909125、Node 18、Gradle 8.8。生成 arm64 release APK：

```bash
cd android
gradlew.bat assembleRelease -PreactNativeArchitectures=arm64-v8a --no-daemon
```

需要在 `android/keystore.properties` 配置自己的 keystore；不要使用仓库外泄的签名文件。

## 说明

- 播放详情页的黑胶样式已编译通过，但当前环境没有可用播放源，未实际播放验证。
- Windows 安装包和 Android APK 都是自签名，系统可能提示未知发布者/未知来源。
- 移动端 universal APK 含 arm64-v8a 等 ABI；arm64 版体积更小。要求 Android 5.0+；如已安装其它签名的洛雪，需要先卸载。
- 应用补丁后如果仍显示旧主题，到「设置 → 主题」选择「青瓷」；新配置默认就是青瓷。

## 许可

补丁基于上游 v2.12.6 / v1.9.1，遵循 **Apache-2.0**。原项目版权归 lyswhut 及贡献者所有。本仓库为非官方改版，与上游无隶属关系。
