# Git 推送指南

## 📋 整理完成清單

✅ **專案結構已完成整理**

```
四連桿機構設計專案/
├── README.md              ✅ 完整專案說明
├── .gitignore             ✅ Git 忽略文件
├── LICENSE                ✅ MIT 授權
├── docs/                  ✅ 13 個文檔文件
│   ├── 00_專案需求/       ✅ 3 個文件 + 圖片資料夾
│   ├── 01_設計分析/       ✅ 2 個文件
│   ├── 02_理論計算/       ✅ 4 個文件
│   ├── 03_優化方案/       ✅ 3 個文件
│   └── 完整專案導覽.md    ✅ 1 個導覽文件
├── scripts/               ✅ Python 腳本目錄（待添加）
└── archive/               ✅ 6 個歷史文件
```

## 🚀 推送到 GitHub 的步驟

### 1️⃣ 初始化 Git 倉庫（如果尚未初始化）

```bash
git init
```

### 2️⃣ 添加所有文件到暫存區

```bash
git add .
```

### 3️⃣ 檢查狀態（可選）

```bash
git status
```

應該會看到類似這樣的輸出：
```
Changes to be committed:
  new file:   .gitignore
  new file:   LICENSE
  new file:   README.md
  new file:   docs/...
  new file:   archive/...
```

### 4️⃣ 創建首次提交

```bash
git commit -m "Initial commit: 陽明交大機動學課程專題

[專案資訊]
- 課程：機動學 (ENME10016)
- 學期：114 學年度上學期
- 教師：徐文祥 教授

[專案內容]
- 完整的專案文檔（13個文件）
- 包含6種優化方案的理論推導和代碼
- 證明一般四連桿優於平行四邊形（+6.2%儲存面積）
- 完整的數學推導和可執行 Python 代碼
- Working Model 2D 驗證指南
- 專業的 README 和專案結構"
```

### 5️⃣ 在 GitHub 上創建新倉庫

1. 登入 GitHub: https://github.com
2. 點擊右上角的 **"+"** → **"New repository"**
3. 填寫倉庫資訊：
   - **Repository name**: `NYCU-Mechanism-Fourbar-Linkage` ⭐ 推薦
   - **Description**: `陽明交大機動學課程專題：四連桿機構優化設計 | NYCU Mechanism Course Project: Four-Bar Linkage Optimization`
   - **Public** 或 **Private**（根據需求選擇）
   - ⚠️ **不要**勾選 "Initialize this repository with a README"（因為我們已經有了）
4. 點擊 **"Create repository"**

### 6️⃣ 連接遠端倉庫

複製 GitHub 給你的倉庫 URL，然後執行：

```bash
# 使用 HTTPS（推薦）
git remote add origin https://github.com/您的用戶名/倉庫名稱.git

# 或使用 SSH（如果已設定 SSH key）
git remote add origin git@github.com:您的用戶名/倉庫名稱.git
```

### 7️⃣ 推送到 GitHub

```bash
# 推送到 main 分支（新版 Git）
git branch -M main
git push -u origin main

# 如果使用舊版 Git（master 分支）
git branch -M master
git push -u origin master
```

### 8️⃣ 驗證推送成功

在瀏覽器中打開您的 GitHub 倉庫頁面，應該能看到：
- ✅ 完整的 README.md 顯示
- ✅ 所有文檔文件
- ✅ 清晰的目錄結構

---

## 🎯 快速複製指令（一鍵執行）

```bash
# 初始化 Git（如果需要）
git init

# 添加所有文件
git add .

# 提交
git commit -m "Initial commit: 陽明交大機動學課程專題"

# 設定遠端倉庫（請替換成您的用戶名）
git remote add origin https://github.com/您的用戶名/NYCU-Mechanism-Fourbar-Linkage.git

# 推送
git branch -M main
git push -u origin main
```

---

## ⚠️ 注意事項

### 1. 檢查 .gitignore 是否正確

確認以下文件**不會**被提交：
- ❌ `__pycache__/`
- ❌ `*.pyc`
- ❌ `.vscode/`
- ❌ `.DS_Store`
- ✅ 但保留 `docs/` 中的圖片

執行檢查：
```bash
git status --ignored
```

### 2. 確認 LICENSE 中的作者名稱

打開 `LICENSE` 文件，將 `[您的名字]` 替換為您的實際名字：

```
Copyright (c) 2025 張三  # 替換這裡
```

### 3. 更新 README.md 中的聯絡資訊

找到 README.md 中的以下部分並更新：

```markdown
## 📧 聯絡方式
- 聯絡作者：[您的郵箱]  # 替換這裡
```

### 4. 確認所有文件都已保存

```bash
# 查看未提交的更改
git diff

# 查看所有未追蹤的文件
git ls-files --others --exclude-standard
```

---

## 🔄 後續更新流程

當您需要推送新的更改時：

```bash
# 1. 添加更改的文件
git add .

# 2. 提交更改
git commit -m "描述您的更改"

# 3. 推送到 GitHub
git push
```

---

## 🆘 常見問題

### Q1: 推送時要求輸入用戶名和密碼？

**A**: GitHub 已不再支援密碼驗證，需要使用 Personal Access Token：

1. 前往 GitHub: Settings → Developer settings → Personal access tokens
2. 生成新 token（勾選 `repo` 權限）
3. 推送時使用 token 代替密碼

### Q2: 推送失敗："rejected"？

**A**: 可能遠端有其他提交，先拉取：

```bash
git pull origin main --rebase
git push origin main
```

### Q3: 想要修改上次提交的訊息？

**A**: 使用 amend：

```bash
git commit --amend -m "新的提交訊息"
git push -f origin main  # 注意：-f 會強制推送
```

---

## 📊 推送後的檢查清單

推送成功後，在 GitHub 上檢查：

- [ ] README.md 正確顯示（含徽章、表格、表情符號）
- [ ] 目錄結構清晰可見
- [ ] 所有文檔文件都存在
- [ ] .gitignore 正確運作（沒有不該提交的文件）
- [ ] LICENSE 文件正確顯示
- [ ] 圖片資源正確顯示（如果有的話）

---

## 🎉 完成！

恭喜您完成專案整理和推送！

**下一步**：
1. 在 README 中添加您的 GitHub 用戶名和倉庫 URL
2. 考慮添加 GitHub Actions 進行自動化測試
3. 添加 Issues 和 Projects 來追蹤後續工作
4. 邀請協作者或分享給社群

---

**整理日期**: 2025-11-14
**工具**: Claude Code
**狀態**: ✅ 準備就緒
