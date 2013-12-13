## 自動化安裝外掛指令

symphonyno5 是透過讀取根目錄下的 `extensions.csv` 自動化安裝外掛，未來若是要更新或增加外掛，都可以先修正此檔，接著執行 `symphonyno5 extensions` 即可。

	注意：Git 移除 submodule 非常麻煩，無法透過此指令檔運作。

## 外掛清單

### 官方預設與開發

前八個：export_ensemble、markdown、maintenance_mode、selectbox_link_field、jit_image_manipulation、profiledevkit、debugdevkit、xssfilter，為 Symphony CMS 預設與必要之核心外掛。

numberfield、remote_datasource、members、uniqueinputfield 這四個則是 Symphony 團隊官方建置的外掛，特別是 Members 這個外掛是一定要安裝的，才能建立前端的會員系統。

### Symphony No.5

Production Mode 與 Asset Compiler 則是 SymphonyNo5 作者 Firegoby Design 提供的外掛。由於 SymphonyNo5 開新專案時會同時建立 master 與 develop 兩個分支，分別對應到開發環境與正式環境。主要用途是根據 `production` 與 `development` 兩個參數，讓 Asset Compiler 可以建立不同環境中的編譯流程。（但目前其實並未使用。）

### [Vlad Ghita](https://github.com/vlad-ghita/)

主要是與前端多語介面相關的外掛（除了 Sections Event 之外）。

### [Symphony Community](http://symphonyextensions.com/developers/symphonists/)

許多社群提供的好用外掛。

### Email相關

- git://github.com/creativedutchmen/email_newsletter_manager.git,extensions/email_newsletter_manager
- git://github.com/creativedutchmen/email_template_manager.git,extensions/email_template_manager


