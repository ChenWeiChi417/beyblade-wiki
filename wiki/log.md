# 戰鬥陀螺 X 新手入門知識庫 — 異動日誌（Log）

> 本日誌採用**時間倒序**排列（最新紀錄位於最上方），記錄知識庫所有的 `ingest`、`query` 與 `lint` 操作歷程。

## [2026-11-19] lint | 執行全庫健康檢查，修復 7 處專有名詞首次出現格式與 2 處 Strict Grounding 用詞收斂

- **資料來源（Sources）**：
  - `raw/01_structure_and_gimmick.md`
  - `raw/02_bx_series.md`
  - `raw/03_ux_series.md`
  - `raw/04_cx_series.md`
  - `raw/05_rules_and_3on3.md`
- **新增頁面（Created）**：無
- **更新頁面（Updated）**：
  - `wiki/concepts/core-parts.md`
  - `wiki/concepts/scoring-rules.md`
  - `wiki/concepts/3on3-deck.md`
  - `wiki/concepts/xtreme-dash.md`
  - `wiki/series/bx-series.md`
  - `wiki/series/ux-series.md`
  - `wiki/series/cx-series.md`
  - `wiki/entities/stadiums.md`
  - `wiki/guides/beginner-guide.md`
  - `wiki/log.md`
- **說明（Notes）**：完成斷鏈（0 斷鏈）、孤立頁（0 孤立頁）、Frontmatter 欄位與四段式結構檢查；將 7 篇條目中首次出現於 TL;DR 或表格欄位之專有名詞統一補齊「繁體中文（英文）」格式，並將 `xtreme-dash.md` 與 `stadiums.md` 中 2 處輕微延伸潤飾用詞收斂至 100% 貼合 `raw/` 原文。

## [2026-11-19] ingest | 首次攝取 raw/ 5 篇基礎原始資料並建立 11 篇核心條目

- **資料來源（Sources）**：
  - `raw/01_structure_and_gimmick.md`
  - `raw/02_bx_series.md`
  - `raw/03_ux_series.md`
  - `raw/04_cx_series.md`
  - `raw/05_rules_and_3on3.md`
- **新增頁面（Created）**：
  - `wiki/concepts/core-parts.md`
  - `wiki/concepts/xtreme-dash.md`
  - `wiki/concepts/scoring-rules.md`
  - `wiki/concepts/3on3-deck.md`
  - `wiki/series/bx-series.md`
  - `wiki/series/ux-series.md`
  - `wiki/series/cx-series.md`
  - `wiki/entities/representative-beys.md`
  - `wiki/entities/stadiums.md`
  - `wiki/guides/beginner-guide.md`
  - `wiki/guides/series-comparison.md`
- **更新頁面（Updated）**：
  - `wiki/index.md`
  - `wiki/log.md`
- **說明（Notes）**：依 `AGENTS.md` 規範完成首次 Ingest，遵守 Strict Grounding 原則（未提及之零件配置以及 CX 系列的發射器鉤爪材質與重心分布皆明確標註為「待補充」），並將所有條目收錄至 `wiki/index.md`。

## [2026-11-19] init | 初始化知識庫目錄結構與 AGENTS.md 規範

- **資料來源（Sources）**：無
- **新增頁面（Created）**：`AGENTS.md`、`wiki/index.md`、`wiki/log.md`
- **更新頁面（Updated）**：無
- **說明（Notes）**：完成知識庫架構初始化，建立 `wiki/concepts/`、`wiki/series/`、`wiki/entities/`、`wiki/guides/` 四大子資料夾與基礎索引、日誌骨架，等待首次 Ingest。
