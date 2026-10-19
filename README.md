# LX Music · 青瓷 (Ceru Jade)

基于 [lyswhut/lx-music-desktop](https://github.com/lyswhut/lx-music-desktop) **v2.12.6** 与 [lyswhut/lx-music-mobile](https://github.com/lyswhut/lx-music-mobile) **v1.9.1** 的非官方 UI 改版。

**当前版本：`v2.12.6-ceru.2`（青瓷改版 rev.2）**

![主界面](screenshots/主界面.png)

## 下载

**Release：** https://github.com/baipiao5555/lx-music-ceru-jade/releases/tag/v2.12.6-ceru.2

| 平台 | 文件 | 说明 |
| --- | --- | --- |
| Windows x64 | `lx-music-desktop-v2.12.6-x64-Setup.exe` | NSIS 安装包，116 MB，未做商业签名 |
| Android arm64 | `lx-music-mobile-v1.9.1-ceru-universal.apk` | 28 MB，推荐，arm64 |
| Android arm64 | `lx-music-mobile-v1.9.1-ceru-arm64.apk` | 14 MB，体积更小，arm64 |

SHA-256：

- Windows：`f7135c3c006ab26a2d199d7011c4b372d51b6a062939f381bd65c4667fbf5be9`
- Android universal：`943c951b3ea1b1dea781569dd41a28b81a47369907a3c765fabb5d4d80402569`
- Android arm64：`c2845cd43a89a1cf1ece80ec456b220f22b6224a7b8e3cda267dfa5491996ca1`

## 版本记录

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
- 启动默认进入「歌单」青瓷首页，首次启动不再弹出版本更新日志。
- 侧栏：品牌、图标 + 文字导航、我的歌单、底部主题卡片。
- 首页：`发现音乐` Hero、胶囊筛选、四列歌单卡片、悬停上浮。
- 顶栏搜索框、来源/类型 tab 胶囊化。
- 悬浮玻璃播放条。
- 播放详情页：黑胶唱片 + 唱臂 + 玻璃歌词面板样式。
- 主题名称的中/繁/英/韩翻译。

### 移动端（青瓷主题版）

- 新增「青瓷」主题并设为默认：青绿主色、浅色主背景。
- 移动端完整布局改版尚未做，界面仍是洛雪移动版的原布局；APK 是主题版。
- rev.2 已补手机端 UI 概念稿（发现页 / 正在播放页），见下方「设计预览」。

## 设计预览（rev.2）

桌面端 + 手机端概念稿：

![桌面 + 手机](design/preview.jpg)

- 桌面端：真实封面、两行歌单、筛选胶囊、悬浮播放条。
- 手机端 · 发现：每日精选大卡、横滑歌单、最近播放、迷你播放器。
- 手机端 · 正在播放：黑胶 + 唱臂、歌词高亮、完整控制。

手机端单独查看：[发现页](design/mobile-discover.jpg) · [正在播放页](design/mobile-player.jpg)

在线预览（GitHub Pages）：https://baipiao5555.github.io/lx-music-ceru-jade/design/preview.html

## 为什么是补丁仓库

Mimosa 的 Git 安全门禁在提交前扫描到上游源码中的 12 个既有高危项（音乐源加密、同步路径处理等），按规则阻止了完整源码提交。本仓库只包含本次 UI/主题改动，避免重新分发上游高风险代码；上游项目仍采用 Apache-2.0 许可。

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
- 移动端 APK 是 arm64-v8a，要求 Android 5.0+；如已安装其它签名的洛雪，需要先卸载。
- 应用补丁后如果仍显示旧主题，到「设置 → 主题」选择「青瓷」；新配置默认就是青瓷。

## 许可

补丁基于上游 v2.12.6 / v1.9.1，遵循 **Apache-2.0**。原项目版权归 lyswhut 及贡献者所有。本仓库为非官方改版，与上游无隶属关系。
