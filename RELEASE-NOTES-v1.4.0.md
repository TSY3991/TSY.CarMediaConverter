# 媒體轉檔工具 v1.4.0

## 這次更新

- 影片轉檔新增三種自動解析度建議：一般裝置最高 1080p、新舊設備最高 720p、舊型設備最高 480p。
- 自動模式只縮小超過上限的影片，不會把低解析度來源硬放大。
- 縮放時會維持原始長寬比例，避免人物或畫面被拉伸變形。
- 「一般使用」預設採用最高 1080p；「檔案較小」預設採用最高 720p。
- 保留原始大小、固定 4K／1080p／720p／480p，以及自訂寬高選項。
- 使用說明已補上不同播放設備的選擇方式。

## 系統需求與限制

- Windows 10／11 64-bit（x64）。
- 已包含 .NET 執行環境、FFmpeg／ffprobe 與 Real-ESRGAN ncnn-vulkan。
- AI 畫質放大需要可用的 Vulkan GPU；低階或內建顯示晶片處理長影片可能非常耗時。
- 本版本未提供 ARM64，也未使用 Authenticode 程式碼簽章。
- 自動解析度依使用者選擇的用途限制畫面大小，不會自動辨識實際連接的車機或電視型號。
- 不保證所有裝置、編碼器或檔案都能播放；重要用途請保留原檔並先用少量檔案測試。
- 免安裝版的設定與紀錄仍會寫入目前 Windows 使用者的 AppData。

## 下載檔案

- `CarMediaConverter-Setup-x64-v1.4.0.exe`：Windows x64 安裝版
- `CarMediaConverter-Portable-x64-v1.4.0.zip`：Windows x64 免安裝版
- `SHA256.txt`：下載完整性雜湊清單
- `RELEASE-MANIFEST.json`：版本、元件與 QA 摘要
- `ffmpeg-8.1.2.tar.xz`：對應 FFmpeg 原始碼
- `ffmpeg-8.1.2.tar.xz.asc`：FFmpeg 原始碼簽章

## 已完成的 QA

- 82/82 單元測試通過。
- 發布版 self-test、FFmpeg 隔離整合測試與 Real-ESRGAN 啟動檢查通過。
- 實際 FFmpeg 自動解析度測試：640×360 維持原尺寸、1920×1080 正確降為 1280×720、1280×720 正確降為 854×480。
- 靜默安裝、版本檢查、已安裝版 self-test、開始功能表捷徑、GUI 啟動、解除安裝與清理測試通過。
- Portable 在中文及空白路徑下通過版本、說明、self-test 與 Real-ESRGAN 檢查。
- Setup、Portable、FFmpeg 原始碼與簽章皆提供 SHA-256。

## 完整性驗證

```powershell
certutil -hashfile "下載的檔案路徑" SHA256
```
