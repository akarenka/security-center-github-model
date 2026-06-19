# Security Center GitHub Model

已完成整理成 **完整 GitHub Model 專案**，並通過基本測試。

📦 下載完整專案 ZIP：  
`security-center-complete-github-model.zip`

---

多語言防護中心專案，支援 **中文 / English / 日本語**，包含桌面 GUI、Web Dashboard、FastAPI API、SQLite 資料庫、Docker 與 GitHub Actions。

---

## 1. 專案功能

- 🛡️ 安全性狀態總覽
- 🔒 隱私檢查面板
- 🚀 性能檢查面板
- ✅ 智能掃描 Smart Scan
- 📋 白名單 Whitelist 管理
- 🧬 威脅資料庫 Threat Database
- 🌍 中文 / English / 日本語 多語言系統
- 🖥️ CustomTkinter 桌面版
- 🌐 Web Dashboard
- ⚙️ FastAPI REST API
- 🗃️ SQLite 本地資料庫
- 🐳 Docker / docker-compose
- ✅ GitHub Actions CI 測試流程
- 📦 GitHub Release 打包流程

---

## 2. 專案結構

```text
security-center-complete-github-model/
├─ README.md
├─ LICENSE
├─ requirements.txt
├─ pyproject.toml
├─ Dockerfile
├─ docker-compose.yml
├─ .gitignore
├─ .github/
│  └─ workflows/
│     ├─ ci.yml
│     └─ release.yml
├─ security_center/
│  ├─ __init__.py
│  ├─ core.py
│  ├─ api.py
│  └─ i18n.py
├─ apps/
│  ├─ desktop_app.py
│  └─ web/
│     ├─ index.html
│     ├─ styles.css
│     └─ app.js
├─ i18n/
│  ├─ zh.json
│  ├─ en.json
│  └─ ja.json
├─ scripts/
│  ├─ run_api.sh
│  └─ run_desktop.sh
└─ tests/
   └─ test_core.py
```

---

## 3. 安裝方式 Windows

### 3.1 建立虛擬環境

```bash
python -m venv .venv
```

### 3.2 啟動虛擬環境

```bash
.venv\Scripts\activate
```

### 3.3 安裝套件

```bash
pip install --upgrade pip
pip install -r requirements.txt
```

---

## 4. 安裝方式 macOS / Linux

### 4.1 建立虛擬環境

```bash
python3 -m venv .venv
```

### 4.2 啟動虛擬環境

```bash
source .venv/bin/activate
```

### 4.3 安裝套件

```bash
pip install --upgrade pip
pip install -r requirements.txt
```

---

## 5. 執行桌面 GUI

```bash
python apps/desktop_app.py
```

功能包含：

- 語言切換：中文 / English / 日本語
- 智能掃描
- 白名單新增與移除
- 威脅資料庫檢視
- SQLite 本地保存

---

## 6. 執行 FastAPI 後端

```bash
uvicorn security_center.api:app --reload
```

啟動後開啟 API 文件：

```text
http://127.0.0.1:8000/docs
```

API 健康檢查：

```text
http://127.0.0.1:8000/api/health
```

---

## 7. 執行 Web Dashboard

先啟動 API：

```bash
uvicorn security_center.api:app --reload
```

再開另一個終端機執行：

```bash
python -m http.server 5173 -d apps/web
```

開啟瀏覽器：

```text
http://127.0.0.1:5173
```

---

## 8. 使用 Docker 執行

### 8.1 建立並啟動服務

```bash
docker compose up --build
```

### 8.2 開啟 API 文件

```text
http://127.0.0.1:8000/docs
```

### 8.3 停止服務

```bash
docker compose down
```

---

## 9. 執行測試

```bash
pytest -q
```

成功時會看到類似：

```text
2 passed
```

---

## 10. 上傳到 GitHub 教學

以下假設你的 GitHub 帳號是：

```text
akarenka
```

Repository 名稱使用：

```text
security-center-github-model
```

---

### 10.1 在 GitHub 建立新 Repository

到 GitHub 建立新 repository：

```text
security-center-github-model
```

建議設定：

```text
Visibility: Public 或 Private
不要勾選 Add README
不要勾選 Add .gitignore
不要勾選 Add license
```

因為本專案已經包含 README、.gitignore、LICENSE。

---

### 10.2 進入專案資料夾

```bash
cd security-center-complete-github-model
```

---

### 10.3 初始化 Git

```bash
git init
```

---

### 10.4 加入所有檔案

```bash
git add .
```

---

### 10.5 建立第一次 Commit

```bash
git commit -m "Initial Security Center GitHub Model"
```

---

### 10.6 設定 main 分支

```bash
git branch -M main
```

---

### 10.7 連接 GitHub Repository

```bash
git remote add origin https://github.com/akarenka/security-center-github-model.git
```

如果你的 repository 名稱不同，請把 `security-center-github-model` 改成你的 repository 名稱。

---

### 10.8 推送到 GitHub

```bash
git push -u origin main
```

---

## 11. 更新 GitHub 專案

修改檔案後，使用：

```bash
git status
git add .
git commit -m "Update project"
git push
```

---

## 12. 建立 GitHub Release

### 12.1 建立版本標籤

```bash
git tag v1.0.0
```

### 12.2 推送標籤

```bash
git push origin v1.0.0
```

推送後，GitHub Actions 會執行 `.github/workflows/release.yml`，自動建立 release zip。

---

## 13. 常用 Git 指令

查看狀態：

```bash
git status
```

查看遠端：

```bash
git remote -v
```

查看 commit：

```bash
git log --oneline
```

拉取最新版本：

```bash
git pull
```

推送更新：

```bash
git push
```

---

## 14. API Endpoints

| Method | Path | 說明 |
|---|---|---|
| GET | `/api/health` | API 健康檢查 |
| GET | `/api/i18n/{lang}` | 取得語言文字 |
| GET | `/api/whitelist` | 取得白名單 |
| POST | `/api/whitelist` | 新增白名單 |
| DELETE | `/api/whitelist/{identifier}` | 移除白名單 |
| GET | `/api/threats` | 取得威脅資料庫 |
| POST | `/api/threats` | 新增威脅資料 |
| POST | `/api/scan` | 執行安全示範掃描 |

---

## 15. 安全範圍說明

此專案是 **防禦性安全示範專案**。

目前掃描功能只會：

- 統計檔案數量
- 檢查示範用可疑副檔名
- 顯示白名單與威脅資料庫統計
- 不會刪除檔案
- 不會隔離檔案
- 不會修改系統
- 不會攻擊任何網路或裝置

---

## 16. 建議下一步

可以繼續新增：

- 使用者登入系統
- RBAC 權限管理
- 真實檔案 hash 掃描
- VirusTotal API 整合
- 系統資源監控
- 多平台打包 EXE / DMG / AppImage
- GitHub Pages Web Preview
- Render / Railway / Azure 部署設定

---

## 17. License

MIT License
