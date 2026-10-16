# 🗓 任務管理中心（日常家事通知）

管理每月固定與臨時的家事，到期時用 LINE 或 Email 提醒，資料可同步到雲端。

**線上使用**：https://kftseng2oo1.github.io/house/

## 主要功能
- 兩種任務：**📅 每月固定**（每月幾號，可選月底最後一天）、**⚡ 臨時任務**（指定日期）
- 分類：財務、生活、數位、其他；優先度：高、中、低
- 勾選完成、展開編輯、刪除
- 通知設定：LINE User ID 或 Email，可先發測試訊息
- ☁️ 同步：把任務存到 Cloudflare KV，由 Worker 依日期發送提醒

## 設定 LINE 通知
1. 加入官方帳號 `@517nsygr`
2. 依 App 內「如何取得？」說明取得 LINE User ID
3. 填入後按「📱 測試 LINE」

## 技術與依賴
- 單檔 HTML PWA（`index.html` 內含全部 HTML/CSS/JS），`manifest.json` + `sw.js` 提供安裝到主畫面與離線快取。
- 後端：`arcar.kftseng2oo1.workers.dev` 的 `/sync-tasks`、`/send-line`、`/send-email`
- 本機資料：`houseTasksV4`、`houseNotifySettings`
