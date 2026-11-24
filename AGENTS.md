# AGENTS.md — 貓咪行為學 LLM Wiki 知識庫與教學簡報生成規範

## 1. 專案目標與受眾定位
* **核心目標**：將 `/raw/` 資料夾中的 5 份貓咪行為學原始文獻，增量編譯為結構化、具備雙向連結（`[[頁面名稱]]`）的持久化 Markdown 知識庫（`/wiki/`），並以此知識庫為**唯一事實來源**，生成一份教學型 HTML 簡報。
* **目標受眾**：完全沒有養過貓的新手飼主（使用台灣習慣用語繁體中文撰寫，關鍵行為學術語保留英文原文，如 `Flehmen Response`、`Kneading`、`Crepuscular`、`Bunting`）。

## 2. 三層目錄架構
```text
cat-behavior-wiki/
├── AGENTS.md                  # [Layer 3: Schema] 本規範檔
├── index.md                   # [Layer 2: Index] 知識庫總目錄（分類索引＋一句話摘要）
├── log.md                     # [Layer 2: Log] 唯追加（Append-only）時間軸操作紀錄
├── raw/                       # [Layer 1: Raw Sources] 原始資料層（唯讀，禁止修改）
├── wiki/                      # [Layer 2: The Wiki] Agent 維護的知識庫本體
│   ├── concepts/              # 核心行為與生理機制頁面
│   ├── myths/                 # 新手常見迷思破解頁面
│   └── guides/                # 飼主實務應對指南
└── slides/                    # [最終產出] 教學型 HTML 簡報
```

## 3. 核心操作工作流（Operations & Loops）

### Operation A：Ingest（吸收原始資料）— 先討論、後寫入
1. **階段 1（討論與提案）**：讀取 `/raw/` 檔案，提煉核心知識點並提出預計新增／更新的 `/wiki/` 頁面與 `[[雙向連結]]` 提案，經使用者確認後才寫入。
2. **階段 2（寫入與更新）**：寫入 `/wiki/` Markdown 檔案（含 YAML frontmatter 與來源標註），同步更新 `index.md`，並在 `log.md` 追加紀錄。

### Operation B：Query（查詢與生成 HTML 簡報）— Graph 工作流與前置檢查門檻
1. **節點 1（流程澄清）**：先繪製 Graph 流程圖並確認檢查點。
2. **節點 2（大綱規劃與檢查）**：讀取 `index.md` 產出投影片大綱，經確認後進入下一階段。
3. **節點 3（逐頁文案與 Pre-generation Gate）**：撰寫逐頁文案並標註 Wiki 出處，執行強制檢查（知識邊界零幻覺、白話易懂、溯源完整），通過後才允許生成 HTML。
4. **節點 4（生成 HTML 與紀錄）**：輸出單一獨立 HTML 簡報，並在 `log.md` 追加紀錄。

### Operation C：Lint（知識庫健康檢查）
檢查孤兒頁面（Orphan Pages）、專有名詞一致性，以及跨文獻 `[[雙向連結]]` 完整性。
