# 陽明交大機動學課程專題：四連桿機構優化設計

**NYCU Mechanism Course Project: Four-Bar Linkage Optimization**

> **課程資訊**
> 機動學 (ENME10016) | 徐文祥 教授 | 114 學年度上學期 | 國立陽明交通大學機械工程學系

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![Improvement](https://img.shields.io/badge/Performance-+6.2%25-brightgreen.svg)](docs/03_優化方案/方案F_一般四連桿機構完整設計.md)

---

## 🎯 TL;DR

設計一個**下拉式層架四連桿機構**（80 cm × 40 cm 櫃體），通過優化算法證明：

**一般四連桿比平行四邊形假設優 6.2%**
- ✅ 儲存面積：+6.2%
- ✅ 下拉距離：+9.0%
- ✅ 連桿總長：-1.7%（成本更低）

---

## 📊 主要成果

| 方案 | 儲存面積 | 下拉距離 | 連桿總長 | 類型 |
|------|---------|---------|---------|------|
| 方案 A（平行四邊形） | 2134 cm² | 30.1 cm | 178 cm | 平行四邊形 |
| **方案 F（一般四連桿）** | **2268 cm²** | **32.8 cm** | **175 cm** | **一般四連桿** |
| **改善** | **+6.2%** | **+9.0%** | **-1.7%** | - |

---

## 📁 專案結構

```
├── docs/
│   ├── 完整專案導覽.md          ⭐ 從這裡開始
│   ├── 00_專案需求/            題目與手稿分析
│   ├── 01_設計分析/            設計思考（含關鍵問題分析）
│   ├── 02_理論計算/            數學推導 + Working Model 2D
│   └── 03_優化方案/            6 種方案完整比較（含 Python 代碼）
├── archive/                    原始需求與歷史文件
└── README.md                   本文件
```

---

## 🚀 快速開始

### 1. 閱讀導覽
```bash
docs/完整專案導覽.md
```

### 2. 理解核心問題
**為什麼不能假設平行四邊形？**
```bash
docs/01_設計分析/關鍵問題_為何不能假設平行四邊形.md
```

### 3. 查看最佳方案
**方案 F：一般四連桿完整設計**
```bash
docs/03_優化方案/方案F_一般四連桿機構完整設計.md
```

### 4. 執行代碼（可選）
```bash
# 安裝依賴
pip install numpy scipy matplotlib

# 從文檔複製代碼並執行
docs/03_優化方案/實際執行_含一般四連桿的六方案比較.md
```

---

## 🎓 文檔導覽

### 初學者
1. [專案需求](docs/00_專案需求/題目.md)
2. [設計分析](docs/01_設計分析/解題流程與設計思考分析.md)
3. [理論基礎](docs/02_理論計算/步驟1_平行四邊形機構詳細計算.md)

### 研究者
1. [關鍵問題](docs/01_設計分析/關鍵問題_為何不能假設平行四邊形.md) ⚠️
2. [優化理論](docs/02_理論計算/步驟3_優化算法改進設計.md)
3. [一般四連桿設計](docs/03_優化方案/方案F_一般四連桿機構完整設計.md) ⭐

### 工程師
1. [可執行代碼](docs/03_優化方案/實際執行_含一般四連桿的六方案比較.md) 🐍
2. [Working Model 2D 驗證](docs/02_理論計算/步驟2_Working%20Model%202D驗證指南.md)
3. [方案比較](docs/02_理論計算/步驟4_方案比較分析.md)

---

## 🔑 關鍵技術

**數學模型**
- 四連桿運動學、向量迴路法、複數表示、Grashof 定理

**優化算法**
- 差分進化算法 (Differential Evolution)、多目標優化、約束處理

**工具**
- Python (NumPy, SciPy, Matplotlib)、Working Model 2D、HackMD

---

## 📖 引用

```bibtex
@software{nycu_fourbar_2025,
  title = {陽明交大機動學課程專題：四連桿機構優化設計},
  author = {您的名字},
  year = {2025},
  institution = {國立陽明交通大學機械工程學系},
  course = {機動學 (ENME10016)},
  instructor = {徐文祥},
  url = {https://github.com/thc1006/NYCU-Mechanism-Fourbar-Linkage}
}
```

---

## 📄 授權

MIT License - 詳見 [LICENSE](LICENSE)
