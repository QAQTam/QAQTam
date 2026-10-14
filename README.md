# QAQ-Harness

本地优先的 AI agent 工作台：**一个 Rust daemon** 承载多会话 agent 循环、canonical session、
工具运行时、沙箱与权限；**多种客户端**（桌面 / 终端 / 浏览器 / Windows 原生壳 / 手机）
经 **Ringing** 协议接入。

**从哪儿开始 →** [`QAQ-Harness`](https://github.com/QAQTam/QAQ-Harness)
—— 门面与索引仓：哪个仓是什么、每个版本锁了哪些 commit、包在哪下载。它**不放代码**。

## 发行版两块

- [`qaqh-backend`](https://github.com/QAQTam/qaqh-backend) —— **权威后端**：daemon（多会话 agent 循环 / canonical session / 工具运行时 / 沙箱 / 权限）+ Ringing 服务面（Rust 2024 workspace）
- [`qaqh-desktop-app`](https://github.com/QAQTam/qaqh-desktop-app) —— **默认桌面客户端**（Tauri 2 壳 + SolidJS 2），打包时内嵌由后端构建的 daemon 侧车

发布规则：**两仓同名 tag**（如 `v2.0.0-RC1`），壳包必须内嵌同 tag 构建的 daemon；
安装包挂在前端仓的 [Release](https://github.com/QAQTam/qaqh-desktop-app/releases)。

## 其它客户端（同一个 daemon 的多种前端）

`qaqh-electron`（Electron 桌面）· `qaqh-webUI`（浏览器）· `qaqh-tui-app`（终端）·
`qaqh-winui-app`（Windows 原生 WinUI 3，无 WebView）· `qaqh-macios`（macOS / iOS）·
`qaqh-harmony`（鸿蒙）· `qaqh-android`（Android）· `qaqh-js-sdk`（壳无关 TypeScript SDK）

系统层另有 `qaq-shell`（WinPE 桌面 shell，Rust + egui）与 `qaq-pe`（恢复环境工具合集）；
`qaqh-winui-reactor-vendor` / `qaq-winui-reactor` 是 `windows-rs` 的 vendor fork，
**不是**客户端。

> 本账号下还有若干与 QAQ-Harness 无关的仓库（第三方 fork 与其它项目），不在此列。
