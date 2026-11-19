# 戰鬥陀螺 X 新手入門知識庫（Beyblade X LLM Wiki）

本專案參考 Karpathy 的 LLM Wiki 架構，以 Markdown 建立結構化、嚴格溯源（Strict Grounding）的《戰鬥陀螺 X（Beyblade X）》新手入門知識庫，並結合自動化健康檢查腳本與工作流程，直接從知識庫生成教學型 HTML 簡報。

## 🚀 快速導覽

* **線上教學簡報（GitHub Pages）**：[點此直接開啟新手教學簡報](https://chenweichi417.github.io/beyblade-wiki/outputs/beginner-slides.html)（支援鍵盤左右方向鍵翻頁）
* **知識庫總索引**：[wiki/index.md](./wiki/index.md)
* **知識庫異動日誌**：[wiki/log.md](./wiki/log.md)
* **專案規則與工作流定義**：[AGENTS.md](./AGENTS.md)

## 📂 專案架構

```text
.
├── AGENTS.md                         # 唯一規則檔（定義架構、Strict Grounding 與三大工作流）
├── raw/                              # 唯讀原始資料層（5 篇基礎資料，AI 不可修改）
├── wiki/                             # 知識庫本體（共 11 篇條目，採混合顆粒度設計）
│   ├── index.md                      # 總索引導覽地圖
│   ├── log.md                        # 時間倒序異動日誌
│   ├── concepts/                     # 高顆粒度核心概念與賽制規則
│   ├── series/                       # BX / UX / CX 三大產品系列介紹
│   ├── entities/                     # 中顆粒度實體彙整頁（代表陀螺與戰鬥盤）
│   └── guides/                       # 新手入門指南與三大系列比較
├── scripts/
│   └── lint_wiki.py                  # 自動化 Lint 腳本（檢查 Frontmatter、斷鏈與孤立頁）
├── .agents/workflows/
│   └── generate-slides.md            # HTML 簡報生成與忠實度檢查工作流
└── outputs/
    └── beginner-slides.html          # 由 Wiki 生成的單檔新手教學 HTML 簡報
```

## ✨ 核心設計特色

1. **Strict Grounding（嚴格溯源）**：所有數據、型號與規則皆以 `raw/` 為唯一事實來源，未提及之細節統一標註「待補充」，杜絕外部腦補。
2. **混合顆粒度拆分**：核心概念與三大系列獨立成頁以利簡報精準引用；代表陀螺與戰鬥盤先行彙整，避免產生空殼頁。
3. **自動化健康檢查（Lint）**：可於專案根目錄執行以下指令，驗證所有頁面的 YAML Frontmatter、相對路徑連結（0 斷鏈）與索引覆蓋率（0 孤立頁）：
   ```bash
   python3 scripts/lint_wiki.py
   ```
