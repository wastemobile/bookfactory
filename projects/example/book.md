---
# 設置檔案名稱，預設使用專案目錄名稱
filename: sanctuary
# 指定詮釋資料檔案
metafile: bookmeta.md
# 設置書籍內容文件與目錄順序
files:
  - ch1.md
  - metalsmith.md
  - subfolder/pandoc.md
  - ch4.md
# 設置試讀版本的內容文件
sample:
  - ch1.md
  - subfolder/pandoc.md
# 設置是否發行（尚未生效）
publish: true
# 設置是否製作電子書
build: true
# 設置是否同步製成Kindle電子書
kindle: false
# 設置發行版本（尚未生效）
release_version: "1.0"
# 設置編輯版本，未設置的話，製成的書檔不會有版本號
edit_version: "0.1"
---
在 Mac 上進行的最簡流程：以純文字檔（YAML + Markdown）建置並維護書籍專案目錄與檔案，安裝 buildebook 套件（`npm install buildebook`，系統必須預先安裝好 Pandoc 與 Kindlegen），一行終端機指令製書。

擺在網路主機上的完整應用程式與網站，使用 Meteor 開發，同樣呼叫相同的製書程序。

核心機制是 Node.js，只使用 JavaScript 開發。
