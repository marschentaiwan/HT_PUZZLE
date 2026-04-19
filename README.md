# HT 承諾書拼圖挑戰 🧩

Human Touch 服務承諾書多人即時拼圖遊戲，部署於 GitHub Pages + Firebase Realtime Database。

## 🎮 遊戲網址

- **主持人頁面**：https://marschentaiwan.github.io/HT_PUZZLE/
- **玩家加入頁**：https://marschentaiwan.github.io/HT_PUZZLE/join.html

## 🚀 部署步驟

1. 將 `index.html` 和 `join.html` 上傳到此 repo 根目錄
2. GitHub repo → Settings → Pages → Source: **Deploy from a branch** → Branch: `main` / `root`
3. 等待約 2 分鐘後即可使用

## 🎯 遊戲流程

```
主持人                          玩家手機
─────────────────────────────────────────
① 開啟 GitHub Pages 主頁
② 點「建立遊戲房間」→ 產生 4 位房間代碼
③ 畫面顯示 QR Code + 代碼
                               ④ 掃 QR Code 或輸入代碼
                               ⑤ 輸入姓名 → 加入等待室
⑥ 見到所有玩家後按「開始遊戲」
                               ⑦ 收到拼圖片
                               ⑧ 點選手中的片 → 點棋盤格子放置
⑨ 主持人即時看到拼圖進度與排名
⑩ 30 片全部拼完 → 顯示排行榜 → 宣誓簽署承諾書！
```

## 📊 計分規則

- 拼對 1 片 → **+10 分**
- 放錯位置 → 提示錯誤，可重試
- 30 片平均分配給所有玩家

## ⚙️ Firebase 設定

已內建連接至 `htgame-6d38e` Firebase 專案。
Database Rules 需允許讀寫：
```json
{
  "rules": {
    "rooms": {
      "$room": {
        ".read": true,
        ".write": true
      }
    }
  }
}
```
