# 📱 ADB 工具箱 - Shizuku 一键解锁工具

> 自带驱动的 Windows 成品工具。无需繁琐配置，双击 EXE 即可为手机快速启用 Shizuku。

[![Platform](https://img.shields.io/badge/Platform-Windows-blue)]()
[![Format](https://img.shields.io/badge/Format-EXE-green)]()
[![License](https://img.shields.io/badge/License-MIT-orange)]()

---

## 📖 项目简介

**ADB 工具箱** 是一款专为普通用户打造的桌面端成品工具。它集成了 **ADB 驱动、平台工具以及 Shizuku 启动脚本**，打包成单个 `.exe` 文件。双击运行，无需安装、无需配置环境变量、无需手敲命令。

无论你是想体验 Shizuku 的神奇功能，还是厌倦了每次都要用命令行输入长串路径，这个工具都能帮你**一键搞定**。

---

## 📸 软件截图

![ADB 工具箱截图](https://raw.githubusercontent.com/biteainet/adb-gonjuxiang/main/file.webp)

> *界面简洁直观，已连接设备实时显示，日志清晰可见。*

---

## ✨ 核心特性

- 🚀 **单文件 EXE**：无需安装，解压即用，绿色便携。
- 🔌 **自带驱动**：内置通用 ADB 驱动，连接设备自动识别，无需手动安装。
- 🧩 **自动部署**：一键推送 Shizuku 启动脚本并执行，自动杀死旧进程、启动服务。
- 🖱️ **图形界面**：傻瓜式操作，顶部菜单支持「命令、应用、文件、驱动修复、炸鱼」等功能。
- 🔄 **多设备支持**：兼容主流 Android 机型（Android 8.0+）。
- 🛡️ **安全透明**：基于官方 ADB 协议，完全离线运行，不收集任何数据。

---

## 🖥️ 使用说明

### 第一步：手机准备

1. 进入 **设置 → 关于手机**，连续点击「版本号」7 次开启开发者模式。
2. 进入 **开发者选项**，打开 **USB 调试**。
3. 使用数据线连接电脑，手机弹出授权提示时选择 **允许**。

### 第二步：运行工具

1. 双击 `ADB工具箱.exe` 启动。
2. 等待工具自动检测设备（首次运行会自动安装驱动）。
3. 在「命令」标签页的输入框中，确认或粘贴 Shizuku 启动命令：

   ```bash
   adb shell /data/app/moe.shizuku.privileged.api-xxx==/lib/arm64/libshizuku.so
   ```

   *（工具已内置该路径，通常只需点击「执行」按钮）*

### 第三步：确认成功

看到日志出现以下输出即代表启动成功：

```text
info: starter begin
info: killing old process...
info: apk path is /data/app/moe.shizuku.privileged.api-xxx==/base.apk
info: starting server...
info: shizuku_server pid is 12299
info: shizuku_starter exit with 0
```

随后打开手机上的 **Shizuku** App，即可看到服务已运行，并可授权其他应用使用。

---

## ⚙️ 工作原理

```text
┌─────────────┐      ADB       ┌──────────────┐
│  Windows PC │ ─────────────► │ Android 设备 │
│  (本工具)    │  推送启动脚本   │  (Shizuku)   │
└─────────────┘                └──────────────┘
```

工具内部集成了以下组件：

| 组件 | 说明 |
|------|------|
| `adb.exe` | 官方平台工具，负责与设备通信 |
| `usb_driver` | 通用 ADB 驱动，免手动安装 |
| `start.sh` | Shizuku 官方启动脚本 |
| `launcher` | 自动化调度核心，带图形界面 |

---

## 📋 系统要求

- **操作系统**：Windows 10 / 11（64 位）
- **手机系统**：Android 8.0 及以上
- **其他**：一根支持数据传输的 USB 线

---

## ❓ 常见问题

**Q：提示「未检测到设备」怎么办？**
A：请检查 USB 调试是否开启，尝试更换数据线或 USB 接口。首次连接需在手机上确认授权。

**Q：需要 root 吗？**
A：不需要。本工具基于 ADB 调试授权，Shizuku 本身也无需 root。

**Q：每次重启手机都要重新运行吗？**
A：是的，Shizuku 服务在重启后会失效，重新运行本工具即可。

**Q：会收集我的数据吗？**
A：不会。工具完全离线运行，不联网、不上传任何信息。

---

## 📦 下载

前往 [Releases](../../releases) 页面下载最新版 `ADB工具箱.exe`。

## 🤝 贡献

欢迎提交 Issue 或 Pull Request，一起让工具更好用。

## 📄 许可证

本项目基于 [MIT License](LICENSE) 开源。

---

> ⭐ 如果这个工具帮到了你，别忘了点个 Star 支持一下！
