# Security Center GitHub Model

已完成整理成 **完整 GitHub Model 專案**，並通過基本測試。

📦 下載完整專案 ZIP：  
`security-center-github-model-final.zip`

---

## Overview

Security Center GitHub Model 是一個防禦性安全示範專案，包含桌面 GUI、Canvas 展示版、SQLite 白名單與威脅資料庫、SandboxDrill 沙盒測試、手動遊戲模式與多語言系統。

本版本已 **完全排除 psutil**：

- 無 `import psutil`
- 無 `process_iter`
- 不讀取系統程序清單
- 不自動偵測遊戲程序
- 遊戲模式改為手動 ON/OFF

---

## Features

- 🖥️ CustomTkinter Desktop GUI
- 🌐 Canvas Browser Demo
- 🗃️ SQLite Whitelist
- 🧬 SQLite Threat Database
- 🛡️ Smart Scan
- 🔒 Privacy Page
- 🚀 Performance Page
- 📦 Applications Page
- 🧪 SandboxDrill
- ✅ EICAR test-file creation
- ✅ Scan and quarantine
- ✅ Quarantine list
- ✅ System recovery demo
- ✅ Clean quarantine
- 🎮 Manual Game Mode ON/OFF
- 🎮 Skip scan when Game Mode is ON
- 🌍 中文 / English / 日本語
- 🏆 Score / Level / Combo / Achievements
- ▶️ Run All Functions
- 🔄 Reset

---

## Install

```bash
pip install -r requirements.txt
