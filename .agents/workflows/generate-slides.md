---
description: 將 wiki/ 知識庫轉換為單檔可獨立開啟的「戰鬥陀螺 X 新手教學型 HTML 簡報」（outputs/beginner-slides.html），並執行逐頁忠實度檢查（Faithfulness Check）。
---

# 生成戰鬥陀螺 X 新手教學型 HTML 簡報工作流程（Generate Beginner Slides）

本工作流程定義如何以 `wiki/` 知識庫作為**唯一知識來源**，編譯並產出一份單檔可獨立開啟的教學型 HTML 簡報（`outputs/beginner-slides.html`），並在產出後執行嚴格的忠實度檢查。

---

## 階段一：檢索階段（Retrieval Phase — 唯一知識來源）

1. **讀取總索引定位條目**：
   - 首先讀取 `wiki/index.md`，盤點目前知識庫收錄之 `Concepts`、`Series`、`Entities` 與 `Guides` 條目。
2. **讀取相關 `wiki/` 條目**：
   - 完整讀取以下核心 `wiki/` 頁面以擷取每頁的 **TL;DR 簡明摘要**、結構化表格與核心重點：
     - `wiki/guides/beginner-guide.md`
     - `wiki/concepts/core-parts.md`
     - `wiki/concepts/xtreme-dash.md`
     - `wiki/series/bx-series.md`、`wiki/series/ux-series.md`、`wiki/series/cx-series.md`
     - `wiki/guides/series-comparison.md`
     - `wiki/entities/representative-beys.md`、`wiki/entities/stadiums.md`
     - `wiki/concepts/scoring-rules.md`
     - `wiki/concepts/3on3-deck.md`
3. **嚴格事實邊界（Strict Grounding）**：
   - **唯一來源限制**：簡報中的所有知識、數據、型號、零件配置、構造描述與賽制規則，**必須 100% 源自上述 `wiki/` 條目**。
   - **禁止腦補外部知識**：嚴禁引入任何未在 `wiki/` 出現的外部設定或預訓練知識；若 `wiki/` 條目中標註為「**待補充**」的欄位（例如 CX 系列的發射器鉤爪材質與重心分布、未提及的固鎖／軸心具體配置），在簡報表格中必須如實保留「**待補充**」，絕不可自行臆測填補。

---

## 階段二：生成階段（Generation Phase — 單檔 HTML 簡報）

將簡報輸出為單一獨立 HTML 檔案，儲存路徑固定為 `outputs/beginner-slides.html`（若 `outputs/` 資料夾不存在則自動建立）。

### 1. 投影片內容結構（共 8～10 頁）

建議採用以下 9 頁標準教學脈絡（可於 8～10 頁範圍內微調，但須完整涵蓋下列主題）：

| 頁次 | 投影片主題 | 核心呈現內容重點 | 底部必須標註之資料來源（`wiki/` 路徑） |
| :---: | :--- | :--- | :--- |
| **第 1 頁** | **封面：戰鬥陀螺 X 新手入門教學簡報** | 第四代戰鬥陀螺「Gear Sports（齒輪運動）」核心定位、學習地圖總覽 | `wiki/guides/beginner-guide.md`、`wiki/index.md` |
| **第 2 頁** | **三大核心部件：戰刃、固鎖、軸心** | 由上至下三層結構（`戰刃（Blade）`、`固鎖（Ratchet）` 刃數-高度命名如 `3-60`、`軸心（Bit）` 四大軌跡與自帶齒輪） | `wiki/concepts/core-parts.md` |
| **第 3 頁** | **極限衝刺（Xtreme Dash）與戰鬥盤場地** | `軸心（Bit）` 齒輪咬合 `極限軌道（Xtreme Line）` 超高速加速切入盤心撞擊，以及 `BX-10 極限衝擊戰鬥盤` 介紹 | `wiki/concepts/xtreme-dash.md`、`wiki/entities/stadiums.md` |
| **第 4 頁** | **三大產品系列介紹（一）：BX 基礎系列 & UX 獨特系列** | `BX 系列（Basic Line）` 金屬鉤爪一體成型與平均配重 vs `UX 系列（Unique Line）` 樹脂鉤爪與外重心強化離心力 | `wiki/series/bx-series.md`、`wiki/series/ux-series.md` |
| **第 5 頁** | **三大產品系列介紹（二）：CX 客製系列** | `CX 系列（Custom Line）` 戰刃三層分解：`鎖定晶片（Lock Chip）`、`主戰刃（Main Blade）`、`輔助戰刃（Assist Blade）` | `wiki/series/cx-series.md` |
| **第 6 頁** | **BX / UX / CX 三大系列全方位比較與代表陀螺** | 三大系列核心結構、鉤爪材質、重心分布對照表（未提及處標註「待補充」）及 11 款代表性陀螺型號亮點 | `wiki/guides/series-comparison.md`、`wiki/entities/representative-beys.md` |
| **第 7 頁** | **四種獲勝方式與 4 分制計分規則** | 標準對戰 **4 分制**，以及 `持久獲勝（Spin Finish）` 1 分、`擊飛獲勝（Over Finish）` 2 分、`爆裂獲勝（Burst Finish）` 2 分、`極限獲勝（Xtreme Finish）` 3 分與場地計分區對照 | `wiki/concepts/scoring-rules.md`、`wiki/entities/stadiums.md` |
| **第 8 頁** | **3on3 Deck 官方賽制與組牌規則** | 準備 **3 顆陀螺**組成牌組（Deck）、**戰刃／固鎖／軸心皆不可重複**、秘密排定 1～3 號出戰順序與未達 4 分重排續戰機制 | `wiki/concepts/3on3-deck.md` |
| **第 9 頁** | **新手起手建議與入門路線總結** | 從 BX 系列與 `BX-10 極限衝擊戰鬥盤` 起手 → 搭配 UX 特化主力與 CX 客製改裝 → 組建首套 3on3 Deck 牌組 | `wiki/guides/beginner-guide.md`、`wiki/guides/series-comparison.md` |

### 2. 介面、互動與來源標註規範

- **單檔獨立運作**：所有 HTML、CSS 樣式與 JavaScript 切換邏輯均內嵌於 `outputs/beginner-slides.html` 單一檔案內，雙擊即可在任何現代瀏覽器離線開啟。
- **鍵盤與按鈕導覽**：
  - 支援鍵盤左右方向鍵（`ArrowRight` / `ArrowLeft`，以及空白鍵或上下頁按鈕）流暢切換投影片。
  - 畫面角落或底部導覽列清楚顯示**目前頁碼／總頁數**（例如 `1 / 9`）與視覺化進度條。
- **版面設計**：版面乾淨易讀、層次分明，善用卡片、標籤（Badges）與高對比表格呈現重點，適合教學投影與新手自學。
- **強制底部來源標註**：
  - **每一頁投影片底部（Footer）**都必須固定顯示：`資料來源：wiki/對應路徑.md`（若引用多篇則以頓號或逗號並列，如 `資料來源：wiki/concepts/xtreme-dash.md、wiki/entities/stadiums.md`）。

---

## 階段三：忠實度檢查（Faithfulness Check Phase）

當 `outputs/beginner-slides.html` 生成完畢後，**必須立即執行自動化或逐頁核對**，並向使用者輸出完整的**「簡報忠實度檢查報告（Faithfulness Check Report）」**：

1. **引用路徑真實性檢查**：
   - 解析 `outputs/beginner-slides.html` 中每一頁底部標註的 `資料來源：wiki/...` 路徑，確認所有被引用的 `wiki/*.md` 檔案皆真實存在於專案中（0 幽靈引用）。
2. **逐頁事實與數據核對（Slide-by-Slide Grounding Verification）**：
   - 逐頁比對簡報內文與所引用的 `wiki/` 條目：
     - **專有名詞與型號**：確認所有專有名詞中英對照、11 款陀螺編號與名稱（`BX-01`～`BX-04`、`UX-01`～`UX-03`、`UX-08`、`CX-01`～`CX-03`）及場地（`BX-10 極限衝擊戰鬥盤`）完全正確。
     - **數值與規則**：確認固鎖命名範例（`3-60` = 3 個凸點、高度 6.0mm）、4 分制與四種獲勝分數（1 分、2 分、2 分、3 分）、3on3 Deck 規則（3 顆陀螺、三大部件皆不可重複、秘密排定 1/2/3 號順序）毫無偏差。
     - **零幻覺與「待補充」檢查**：確認沒有出現任何 `wiki/` 未記載的外部知識，且未知欄位（如 CX 系列鉤爪材質與重心分布）均誠實標註為「待補充」。
3. **輸出檢查報告**：
   - 在對話中列出每一頁投影片的主題、對應之 `wiki/` 來源路徑，以及忠實度核對結果（`PASS` / `FAIL`）。若發現任何不一致，必須立即修正 `outputs/beginner-slides.html` 後再回報完成。
