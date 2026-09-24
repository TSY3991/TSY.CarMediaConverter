# 媒體轉檔工具

這是「媒體轉檔工具」的官方下載與版本發布 repo。目前正式版本為 **v1.3.0（Windows x64）**。

> 本 repo 是 release-only 發布入口，不公開程式原始碼。安裝檔與免安裝版只放在 GitHub Releases，不提交到 Git 歷史。

## 下載

- [前往最新版本](https://github.com/TSY3991/TSY.CarMediaConverter/releases/latest)
- [查看所有版本](https://github.com/TSY3991/TSY.CarMediaConverter/releases)
- [微光工具箱下載頁](https://tsy3991.github.io/TSY.Microglow-Tools/tools/car-media-converter/)

一般 Windows 10／11 64-bit 電腦可選擇：

- `CarMediaConverter-Setup-x64-v1.3.0.exe`：安裝版
- `CarMediaConverter-Portable-x64-v1.3.0.zip`：免安裝版，必須完整解壓縮後使用

## 主要功能

- 快速轉檔：輸出通用 MP3，以及適合多數新式裝置或舊式播放設備的 MP4。
- 影片轉檔：支援 MP4、MKV、AVI、MOV、TS、FLV、WebM、WMV、MPG、3GP 等常見容器，並可調整影像、音訊、解析度與畫質。
- AI 畫質放大：整合 Real-ESRGAN ncnn-vulkan，可選擇 2×、3× 或 4× 放大；實際速度取決於 Vulkan GPU。
- 批次處理：提供整體進度、預估剩餘時間、處理紀錄與逐檔結果。
- 完成驗證：輸出完成後會完整解碼，並確認影片／音訊串流符合所選用途。
- USB 安全同步：保留預覽、空間檢查、雜湊與原子同步流程。

本工具不能保證相容所有裝置、編碼器、媒體檔案或儲存裝置。請保留原始檔與獨立備份，重要用途請先用少量檔案測試。

## 未簽章提醒

目前 Setup 尚未使用 Authenticode 程式碼簽章。Windows 或瀏覽器可能顯示安全提醒或需要較長的掃描時間；請只從本 repo 或微光工具箱下載，並使用隨版本提供的 `SHA256.txt` 核對檔案。

```powershell
certutil -hashfile "下載的檔案路徑" SHA256
```

## 安全行為

- 預設不覆蓋既有檔案，也不刪除原始輸入。
- 實際寫入前會先顯示確認內容並檢查空間。
- 轉檔完成後會完整解碼驗證與確認必要串流。
- 取消或失敗時會終止 FFmpeg，並清理本次未完成的輸出。

## 授權與第三方元件

本工具採專有免費使用授權；可在自己的 Windows 電腦安裝、執行與製作個人備份，但不授權公開再散布、販售、出租、冒名發佈或修改後再散布。完整條款請見 [LICENSE.txt](./LICENSE.txt)。

隨程式提供的 FFmpeg／ffprobe 依 GNU General Public License version 3 or later 提供；Real-ESRGAN 與 ncnn 依各自授權提供。每次 Release 會附上相關來源、授權與第三方聲明，詳見 [THIRD-PARTY-NOTICES.txt](./THIRD-PARTY-NOTICES.txt)。
