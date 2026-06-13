# 🌿 SVDSS — 永續視覺化決策輔助系統
### Sustainable Visualization Decision Support System

> **Note:** This SVDSS refers to the *Sustainable Visualization Decision Support System* for interior design sustainability compliance — distinct from the bioinformatics SVDSS (Structural Variant Discovery from Sample-specific Strings).

---

## 簡介 Overview

**SVDSS** 是一套整合 AI 與綠建材資料庫的室內設計永續決策輔助系統，協助設計師在設計階段即時評估綠建材使用率（Rgi）與碳排放係數，實現 ESG 合規自動化。

SVDSS is an AI-powered decision support system for interior designers in Taiwan, enabling real-time assessment of green building material usage rates (Rgi) and carbon emission coefficients during the design phase.

---

## 核心功能 Features

- 🏗️ **Rgi 評估引擎** — 自動計算綠建材使用率，法規門檻 60%（《綠建材設計技術規範》）
- 📦 **綠建材資料庫 v3** — 1,157 筆認證建材（健康 693 / 再生 241 / 高性能 214 / 生態 4）
- 🔌 **SketchUp Plugin** — Ruby API 外掛，直接在 3D 模型中套用綠建材並計算 Rgi
- 📊 **碳排係數分析** — 依建研所 LCADB → ICE v3.0 → 環境部 v7 優先順序計算
- 📄 **ESG 報告自動化** — n8n 工作流程驅動，WeasyPrint 輸出 PDF

---

## 系統架構 Architecture

```
施工圖 PDF
    ↓
建材清單萃取（Claude AI）
    ↓
綠建材資料庫比對（1,157筆）
    ↓
Rgi 計算 + 碳排分析
    ↓
ESG 報告 PDF（WeasyPrint）
    ↓
n8n 自動遞送
```

---

## SketchUp Plugin 安裝 Installation

### 需求 Requirements
- SketchUp 2025
- Windows（D 槽，路徑 `D:\SVDSS\claude\`）

### 安裝步驟
1. 下載 `svdss_panel.rb` 與 `green_materials_master.json`
2. 複製至 SketchUp Plugins 資料夾：
   ```
   C:\Users\%USERNAME%\AppData\Roaming\SketchUp\SketchUp 2025\SketchUp\Plugins\
   ```
3. 重新啟動 SketchUp → Extensions → 🌿 SVDSS 永續評估

---

## 資料庫說明 Database

| 標章種類 | 筆數 |
|----------|------|
| 健康綠建材 | 693 |
| 再生綠建材 | 241 |
| 高性能綠建材 | 214 |
| 生態綠建材 | 4 |
| **合計** | **1,157** |

資料來源：內政部建築研究所綠建材標章核定清冊（2026-03-19 爬取）

碳排係數優先順序：
1. 建研所 LCADB（A1–A3 階段）
2. ICE v3.0（Bath University）
3. 環境部係數管理表 v7

再生建材適用 ×0.72 折減係數。

---

## 研究背景 Research Context

本系統為東海大學 EMBA 碩士論文研究成果：

> **論文題目：** Integrating Sustainability Indicators into LLM-Based Visualization and Decision Support for Interior Design Output
>
> **指導教授：** 姜自強 教授
>
> **研究機構：** 東海大學（Tunghai University）EMBA

---

## 商業應用 Commercial Use

SVDSS 同步發展為 B2B SaaS 產品，服務台灣室內設計產業：

- 目標用戶：室內設計師、建築師、工程顧問
- 核心價值：綠建材合規自動化、ESG 報告一鍵生成
- 整合系統：工誌 mark flow.（施工現場管理 SaaS）

---

## 開發團隊 Team

**樂融設計 LeRong Design**
- 網站：[lrdesign.pro](https://lrdesign.pro)
- 系統設計：Yvonne Shen｜System Designer
- 研究機構：東海大學 EMBA

---

## 授權 License

本專案程式碼與資料庫內容為研究用途，商業使用請聯繫 lrdesign.pro。

---

*SVDSS © 2026 樂融設計 LeRong Design × 東海大學 EMBA*
*System Designer ✦ Yvonne Shen*
