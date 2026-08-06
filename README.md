# 舊車機 MP3／MP4 轉檔工具

這是「舊車機 MP3／MP4 轉檔工具」的官方下載與版本發布 repo。目前正式版本為 **v1.2.0（Windows x64）**。

> 本 repo 是 release-only 發布入口，不公開程式原始碼。安裝檔與免安裝版只放在 GitHub Releases，不提交到 Git 歷史。

## 下載

- [前往最新版本](https://github.com/TSY3991/TSY.CarMediaConverter/releases/latest)
- [查看所有版本](https://github.com/TSY3991/TSY.CarMediaConverter/releases)
- [微光工具箱下載頁](https://tsy3991.github.io/TSY.Microglow-Tools/tools/car-media-converter/)

一般 Windows 10／11 64-bit 電腦可選擇：

- `CarMediaConverter-Setup-x64-v1.2.0.exe`：安裝版
- `CarMediaConverter-Portable-x64-v1.2.0.zip`：免安裝版，必須完整解壓縮後使用

## 已驗證輸出規格

- MP3：128 kbps、44.1 kHz、雙聲道，移除高風險 metadata 與封面。
- MP4：H.264 High Level 3.0、852×480、25 fps、yuv420p、AAC-LC 128 kbps。
- 非 16:9 影片會等比例縮放並補黑邊，不會強制拉伸。

本工具不保證相容所有車機、媒體檔案或儲存裝置。請保留原始檔與獨立備份，並先用少量檔案在自己的車機測試。

## 未簽章提醒

目前 Setup 尚未使用 Authenticode 程式碼簽章。Windows 或瀏覽器可能顯示安全提醒或需要較長的掃描時間；請只從本 repo 或微光工具箱下載，並使用隨版本提供的 `SHA256.txt` 核對檔案。

```powershell
certutil -hashfile "下載的檔案路徑" SHA256
```

## 安全行為

- 預設不覆蓋既有檔案，也不刪除原始輸入。
- 實際寫入前會先預覽輸出名稱與檢查整批空間。
- 轉檔完成後會完整解碼驗證並計算 SHA-256。
- 取消或失敗時會終止 FFmpeg，並回復本次新建檔案。

## 授權與第三方元件

本工具沿用專有免費使用授權；可在自己的 Windows 電腦安裝、執行與製作個人備份，但不授權公開再散布、販售、出租、冒名發佈或修改後再散布。完整條款請見 [LICENSE.txt](./LICENSE.txt)。

隨程式提供的 FFmpeg／ffprobe 是獨立執行檔，依 GNU General Public License version 3 or later 提供。每次 Release 會一併提供對應 FFmpeg 原始碼壓縮檔、簽章及第三方聲明，詳見 [THIRD-PARTY-NOTICES.txt](./THIRD-PARTY-NOTICES.txt)。
