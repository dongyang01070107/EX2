# 臺北市區最塞路段排行
署名：視傳四勤　121253015　陳冬昀

純靜態網站，直接抓取臺北市交通管制工程處 gzip XML。每次抓取結束後 60 秒更新一次。支援搜尋、壅塞篩選、排序、最塞前十名、平均車速趨勢、本機快取、失敗重試與來源資料超過 30 分鐘提醒。

資料：https://tcgbusfs.blob.core.windows.net/blobtisv/GetVD.xml.gz
資料集：https://data.gov.tw/dataset/128709
授權：政府資料開放授權條款－第 1 版。

## GitHub Pages
將本資料夾內容（包含 .github）放進 GitHub repository 的 main 分支。在 Settings → Pages → Build and deployment 將 Source 設為 GitHub Actions。接著手動執行 Deploy to GitHub Pages 工作流程或推送新提交。

所有資源均使用相對路徑，支援 username.github.io/repository/。不需要 npm、金鑰或建置工具。請透過 HTTP(S) 開啟，不要以 file:// 直接開啟。

## 驗證限制
製作環境的網路代理拒絕存取指定資料網址（CONNECT 403），尚未驗證來源 XML 實際結構及 CORS 標頭。程式支援 SectionName、AvgSpd、TotalVol、ExchangeTime 作為 XML 子元素或屬性。若來源未允許 GitHub Pages 跨來源存取，需要由資料提供者開放 CORS，或另設受控代理服務；純 GitHub Pages 無法執行伺服器代理。頁面會顯示失敗狀態，不以示範資料代替。
