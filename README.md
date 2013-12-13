## Symphony No.5 Command Line Tool 終端機命令列工具

* Version 0.3.0
* Date: 3rd December 2012
* Symphony CMS version 2.3.4

### 更新（2013/11/20）

完備了一些指令的翻譯。將安裝程序更新到 Symphony CMS 2.3.4，移除了一個與其不相容的外掛，並新增了與前台多語設定相關的幾個外掛。

### 注意事項！

此處的程序已將預設抓取之倉儲改為 [@wastemobile](http://github/wastemobile) 的私人倉儲，其中的外掛清單與預設並不相同，如果您希望藉由 Firegoby 的設定、從頭開始一個乾淨的 Symphony No.5 install，請務必修改程序第74行中的設定。

將程序第74行的內容改回 `... git://github.com/firegoby/symphonyno5.git ...`，或是直接前往 [原始倉儲](https://github.com/firegoby/symphonyno5.sh) 拷貝正確的檔案。

## 概觀

Symphony No.5 終端機命令列工具是一個用來輕鬆管理 [Symphony No.5](http://github.com/firegoby/symphonyno5.git) 的 bash script。

## 功能

* 建立與設置新的 Symphony CMS 開發專案。
* 根據 `extensions.csv` 檔案列表，更新與安裝 Symphony 的 git submodules 外掛。
* 編譯且串聯 Coffeescript 與 Javascript 檔案，產生單一最小化的正式檔案。
* 將 LESS、Sass 或 Stylus 撰寫的格式，編譯成單一經壓縮過的 CSS 樣式表。
* 設定正式環境的目錄與檔案權限。
* 根據 `manifest/config.php` 中的設定，修復目錄與檔案權限。

## 安裝

1. 拷貝 `symphonyno5` 到任意已存在於系統 `$PATH` 中的可執行目錄。
2. 執行 `chmod +x symphonyno5` 讓程序俱備可執行的權限。

	Mac 的環境路徑設定都在 /etc/paths 檔案中（可能需要 sudo 權限），使用 echo $PATH 指令可以觀看目前設定的所有路徑。我會在個人目錄下建立一個 bin 或 scripts 目錄，將這目錄加入路徑設定，未來還有各種非系統預設的程序要執行，就通通集中擺放。

## 如何使用

***Note**: 除了新增 `new` 指令之外，其它指令都要在專案的根目錄下運行。*

### 新建開發專案

    symphonyno5 new projectname

### 根據 `extensions.csv` 列表，更新/安裝 Symphony Extensions 

    symphonyno5 extensions

### 設定目錄與檔案權限

    symphonyno5 setperms 0775 0664

### 根據 `manifest/config.php` 修復目錄與檔案權限

    symphonyno5 fixperms

## FAQ

1. **為什麼所有 CSS 與 Javascript 編譯、最小化的功能都不見了？**

  一個專用於這些功能的外掛 [Asset Compiler](http://github.com/firegoby/asset_compiler) 已經誕生了！不再使用命令列，使用 master.xsl 中的標籤就能控制，試試看！（ps. 如果還是想用CLI，就用 git 切回 `0.2.0` 版吧。）

## Changelog

* 0.3.0 - 3 Dec 12
  * Removed `compile` commands
* 0.2.0 - 24 Nov 12
  * Remove Ant build script support
  * Compile javascript via Curl API call to Google Closure
  * Retask `fixperms` command
  * Add `setperms` command
  * Add plain `compile` command to compile all assets, CSS & JS
  * Misc refactoring/cleanup of code
* 0.1.1 - 22 Nov 12 
  * Drop the `.sh` extension from the script
  * Rename `submodules` command to `extensions`
* 0.1.0 - 21 Nov 12 - Initial release