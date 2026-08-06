## 這次發布了什麼

v1.2.0 是「舊車機 MP3／MP4 轉檔工具」第一個正式 Windows x64 發布版本。

- 將常見音訊轉為 MP3：128 kbps、44.1 kHz、雙聲道。
- 將常見影片轉為 MP4：H.264 High Level 3.0、852×480、25 fps、AAC-LC 128 kbps。
- 非 16:9 影片等比例縮放並補黑邊，避免畫面被拉伸。
- 支援批次加入檔案、資料夾及拖放操作。
- 提供實際寫入前的完整預覽、整批空間檢查、進度、取消及診斷匯出。
- 預設不覆蓋既有檔案，也不刪除原始輸入。

## 系統需求與限制

- Windows 10／11 64-bit（x64）。
- 已包含 .NET 執行環境與測試使用的 FFmpeg／ffprobe。
- 本版本未提供 ARM64。
- 本工具不保證相容所有車機、媒體檔案或儲存裝置，請先用少量檔案在自己的車機測試。
- 免安裝版的設定與紀錄仍會寫入目前 Windows 使用者的 AppData。

## 未簽章提醒

目前 Setup 尚未使用 Authenticode 程式碼簽章。Windows 或瀏覽器可能顯示安全提醒或需要較長的掃描時間。請從官方 Release 或微光工具箱下載，並用 `SHA256.txt` 核對檔案。

## 下載檔案

- `CarMediaConverter-Setup-x64-v1.2.0.exe`：Windows x64 安裝版
- `CarMediaConverter-Portable-x64-v1.2.0.zip`：Windows x64 免安裝版
- `SHA256.txt`：下載完整性雜湊清單
- `RELEASE-MANIFEST.json`：版本與 QA 摘要
- `ffmpeg-8.1.2.tar.xz`：對應 FFmpeg 原始碼
- `ffmpeg-8.1.2.tar.xz.asc`：FFmpeg 原始碼簽章

## 已完成的 QA

- 10/10 單元測試通過。
- 發布版 self-test 與 FFmpeg 實際音訊／影片整合測試通過。
- 安裝、已安裝版 self-test、解除安裝與清理測試通過。
- Portable 在中文及空白路徑、無外部 .NET 開發環境下通過。
- 主程式與 Setup 圖示、版本及 SHA-256 已核對。

## 完整性驗證

```powershell
certutil -hashfile "下載的檔案路徑" SHA256
```
