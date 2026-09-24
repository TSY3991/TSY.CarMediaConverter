# 媒體轉檔工具 v1.3.0

## 這次更新

- 產品定位從舊車機專用擴大為通用媒體轉檔工具，仍保留舊式播放設備相容選項。
- 快速轉檔提供 MP3、通用 MP4 與舊式設備 MP4；用途選項改為白話說明。
- 影片轉檔支援 MP4、MKV、AVI、MOV、TS、FLV、WebM、WMV、MPG、3GP，以及多種影像／音訊編碼與解析度設定。
- 整合 Real-ESRGAN ncnn-vulkan AI 畫質放大，可依模型選擇 2×、3× 或 4×。
- 加入單一整體進度、完成百分比、預估剩餘時間、頁面內處理紀錄與逐檔結果。
- 確認視窗改為一致的應用程式樣式；修正 AVI、MOV、MPG 等影片輸出可能只剩音訊的串流選擇問題。
- 每個輸出完成後會完整解碼，並確認應有的影像／音訊串流存在。
- 保留 USB 安全同步、預覽、空間檢查、雜湊與原子寫入流程。

## 系統需求與限制

- Windows 10／11 64-bit（x64）。
- 已包含 .NET 執行環境、FFmpeg／ffprobe 與 Real-ESRGAN ncnn-vulkan。
- AI 畫質放大需要可用的 Vulkan GPU；低階或內建顯示晶片處理長影片可能非常耗時。
- 本版本未提供 ARM64，也未使用 Authenticode 程式碼簽章。
- 不保證所有裝置、編碼器或檔案都能播放；重要用途請保留原檔並先以少量檔案測試。
- 免安裝版的設定與紀錄仍會寫入目前 Windows 使用者的 AppData。

## 下載檔案

- `CarMediaConverter-Setup-x64-v1.3.0.exe`：Windows x64 安裝版
- `CarMediaConverter-Portable-x64-v1.3.0.zip`：Windows x64 免安裝版
- `SHA256.txt`：下載完整性雜湊清單
- `RELEASE-MANIFEST.json`：版本、元件與 QA 摘要
- `ffmpeg-8.1.2.tar.xz`：對應 FFmpeg 原始碼
- `ffmpeg-8.1.2.tar.xz.asc`：FFmpeg 原始碼簽章

## 已完成的 QA

- 79/79 單元測試通過。
- 發布版 self-test、FFmpeg 實際整合測試與 Real-ESRGAN 啟動檢查通過。
- AVI、MOV、MPG 實際短片轉檔均確認具有影像與音訊，且可完整解碼。
- 靜默安裝、已安裝版 self-test、解除安裝與清理測試通過。
- Portable 在中文及空白路徑下通過 self-test。
- Setup、Portable、FFmpeg 原始碼與簽章皆提供 SHA-256。

## 完整性驗證

```powershell
certutil -hashfile "下載的檔案路徑" SHA256
```
