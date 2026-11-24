# 📜 貓咪行為學 LLM Wiki 操作日誌（Log）

> 本檔案為唯追加（Append-only）時間軸紀錄，每次執行 Ingest、Query 或 Lint 皆須依標準格式寫入。

## [2026-11-24] schema | 初始化專案架構與 AGENTS.md
* 確立三層目錄架構（`raw/`、`wiki/`、`slides/`）與目標受眾（無養貓經驗之新手飼主）。
* 設定 Operation A（先討論後寫入）、Operation B（Graph 流程與前置檢查門檻）與 Operation C（Lint 健康檢查）規範。

## [2026-11-24] ingest | raw/01_cat_body_language.docx — 建立作息領域與肢體語言概念頁
* 新增 `wiki/concepts/activity-and-territory.md` 與 `wiki/concepts/tail-and-body-signals.md`。
* 提煉晨昏性（Crepuscular）、臉頰磨蹭（Bunting）費洛蒙標記、尾巴姿態與慢眨眼知識點。

## [2026-11-24] ingest | raw/02_cat_purring.docx — 建立呼嚕聲機制頁與迷思總表
* 新增 `wiki/concepts/purring-mechanism.md` 與 `wiki/myths/common-cat-myths.md`。
* 記錄 25–150 Hz 發聲原理與四大功能（含疼痛自我修復），破除「呼嚕＝絕對開心」迷思。

## [2026-11-24] ingest | raw/03_cat_kneading.docx — 建立踩奶行為概念頁與互動指南
* 新增 `wiki/concepts/kneading-behavior.md` 與 `wiki/guides/bonding-and-interaction.md`。
* 整合幼貓哺乳記憶、築巢本能與肉墊費洛蒙標記三大理論，並連結 `[[tail-and-body-signals]]` 與 `[[purring-mechanism]]`。

## [2026-11-24] ingest | raw/04_flehmen_response.docx — 建立裂唇嗅反應與犁鼻器概念頁
* 新增 `wiki/concepts/flehmen-and-vomeronasal.md`，並更新 `wiki/myths/common-cat-myths.md`。
* 釐清張嘴呆滯表情為啟動上顎犁鼻器解碼費洛蒙之正常感官運作。

## [2026-11-24] ingest | raw/05_cat_behavior_guide.docx — 建立問題行為與壓力管理指南
* 新增 `wiki/guides/stress-and-problem-behaviors.md`，同步擴充 `common-cat-myths.md` 與 `bonding-and-interaction.md`。
* 確立「先就醫排除生理疼痛」、「提供安全避風港」、「禁止手腳逗貓」三大實務原則。

## [2026-11-24] lint | 執行全庫健康檢查（Lint Pass #1）
* 檢查結果：8 個 Wiki 頁面全數收錄於 `index.md`（0 孤兒頁面）；專有名詞已統一（「呼嚕聲（咕嚕聲）」、「犁鼻器」）；費洛蒙、信任放鬆、疼痛辨識三條跨文獻 `[[雙向連結]]` 軸線均已完整建立。
