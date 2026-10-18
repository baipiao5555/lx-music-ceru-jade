# LX Music · 青瓷 (Ceru Jade) UI Patch

基于 [lyswhut/lx-music-desktop](https://github.com/lyswhut/lx-music-desktop) **v2.12.6** 的非官方 UI 改版补丁，新增「青瓷」主题与桌面端界面重构。

![主界面](screenshots/主界面.png)

## 为什么是补丁而不是完整源码

Mimosa 的 Git 安全门禁在提交前扫描到上游源码中的 12 个既有高危项（音乐源加密、同步路径处理等），按规则阻止了完整源码提交。本仓库只包含本次 UI 改动，避免重新分发上游的高风险代码；上游项目仍采用 Apache-2.0 许可。

## 包含的改动

- 新增「青瓷」主题：青绿主色、浅色玻璃主面板、柔和渐变背景，并设为默认主题。
- 侧栏：品牌、图标 + 文字导航、我的歌单、底部主题卡片。
- 首页：`发现音乐` Hero、胶囊筛选、四列歌单卡片、悬停上浮。
- 顶栏搜索框、来源/类型 tab 胶囊化。
- 悬浮玻璃播放条。
- 播放详情页：黑胶唱片 + 唱臂 + 玻璃歌词面板样式。
- 主题名称的中/繁/英/韩翻译。

## 应用方式

```bash
git clone --depth 1 --branch v2.12.6 https://github.com/lyswhut/lx-music-desktop.git
cd lx-music-desktop
git apply /path/to/0001-feat-ui-ceru-jade.patch
```

然后按上游 README 安装依赖并构建。

Windows 上如果 `better-sqlite3` 因缺少 Visual Studio C++ 工具链编译失败，可以用：

```bash
npm install --ignore-scripts --registry=https://registry.npmmirror.com
node build-config/postinstall.js
# 将 Electron 42.11.6 win32-x64 运行时解压到 node_modules/electron/dist
# 写 node_modules/electron/path.txt，内容为 electron.exe（不要带换行）
npm run build
.\node_modules\electron\dist\electron.exe dist\main.js
```

## 说明

- 播放详情页的黑胶样式已编译通过，但当前环境没有可用播放源，未实际播放验证。
- 移动端（React Native）不在本补丁范围内；需要 JDK 17 + Android SDK 单独改造。
- 应用补丁后如果仍显示旧主题，到「设置 → 主题 → 更多主题 → 青瓷」选择一次；新配置默认就是青瓷。

## 许可

补丁基于上游 v2.12.6，遵循 **Apache-2.0**。原项目版权归 lyswhut 及贡献者所有。本仓库为非官方改版，与上游无隶属关系。
