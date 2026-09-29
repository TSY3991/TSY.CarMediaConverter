# 媒體轉檔工具 v1.5.0

## 這次更新

- 影片清單改為可自動換行的逐檔資訊卡，不需左右拖曳即可查看完整資訊。
- 加入來源影片分析，直接顯示原始解析度、畫面比例、幀率、片長、格式與檔案大小。
- 進階設定會依來源自動選取建議的檔案格式、影片與聲音壓縮方式、畫面大小、畫質、流暢度、顯示卡加速與畫面比例。
- 小於或等於 1080p 的來源預設保持原始大小，超過 1080p 才建議限制最高 1080p。
- 無聲影片會自動建議不加入聲音；一般來源預設採 MP4、H.264／AVC 與 AAC 的通用組合。
- 使用者手動調整後，重新開啟進階設定不會覆蓋已選內容；來源清單變更時才重新計算建議。
- 使用說明與技術文件已同步更新。

## 系統需求與限制

- Windows 10／11 64-bit（x64）。
- 已包含 .NET 執行環境、FFmpeg／ffprobe 與 Real-ESRGAN ncnn-vulkan。
- AI 畫質放大需要可用的 Vulkan GPU；低階或內建顯示晶片處理長影片可能非常耗時。
- 本版本未提供 ARM64，也未使用 Authenticode 程式碼簽章。
- 自動建議依加入的來源影片與本機可用編碼器計算，不會辨識實際連接的車機或電視型號。
- 不保證所有裝置、編碼器或檔案都能播放；重要用途請保留原檔並先用少量檔案測試。
- 免安裝版的設定與紀錄仍會寫入目前 Windows 使用者的 AppData。

## 下載檔案

- `CarMediaConverter-Setup-x64-v1.5.0.exe`：Windows x64 安裝版
- `CarMediaConverter-Portable-x64-v1.5.0.zip`：Windows x64 免安裝版
- `SHA256.txt`：下載完整性雜湊清單
- `RELEASE-MANIFEST.json`：版本、元件與 QA 摘要
- `ffmpeg-8.1.2.tar.xz`：對應 FFmpeg 原始碼
- `ffmpeg-8.1.2.tar.xz.asc`：FFmpeg 原始碼簽章

## 已完成的 QA

- 87/87 單元測試通過，0 失敗。
- 發布版 self-test、FFmpeg 隔離整合測試與 Real-ESRGAN 啟動檢查通過。
- Portable 隔離解壓與 self-test 通過。
- Setup 隔離靜默安裝、已安裝版 self-test、解除安裝與測試資料清理通過。
- Setup、Portable、FFmpeg 原始碼與簽章均提供 SHA-256。

## 完整性驗證

```powershell
certutil -hashfile "下載的檔案路徑" SHA256
```
