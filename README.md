bookfactory
===========

搭配 [buildebooks](https://www.npmjs.com/package/buildebooks) 使用的測試與範例。

1. `npm -v` 檢視 NPM 版本（2.8.4）。
2. `pandoc -v` 檢視 Pandoc 版本（1.13.2）。
3. `kindlegen -releasenotes` 檢視 Kindlegen 版本（V2.9）。

打開終端機、在**任意目錄**輸入上面三個指令，都必須正常顯示版本資訊，否則製書程式是無法運作的。參考 [預裝程序](https://github.com/wastemobile/buildebooks/blob/master/preinstall.md)。

在通過上述三項檢查的系統上，可以透過 Git 複製此倉儲，輸入 `git clone https://github.com/wastemobile/bookfactory.git`。

### 使用說明

在專案目錄下建立一或多個書籍專案，使用不同的目錄名稱。目錄下可以自由擺放任意數量、名稱、層級的純文字檔與素材，以 Markdown 輕量級標記語法書寫，撰寫與編輯過程中，你可以建立各式各樣的草稿、參考文件，沒有什麼限制。所有檔案都是相對書籍專案目錄設置的，`ch1.md`、`firstnote.txt`、`part1/content.md`...，只要內容正確、找得到對應的檔案，應該都能被正確辨識、製作電子書。

想要製作電子書時，必須以 YAML 格式撰寫一個「製書索引檔」（預設是 `book.md`），以及擺放完整書籍資料的詮釋資料檔（預設是 `metadata.md`）。這兩個簡單的檔案就包含了製作電子書所有必要的設定，你選定的文件、順序，就是書籍的目錄與內容。

你必須設定版本號，例如 `edit_version: "0.3"`，電子書會以 `filename-0.3` 的檔名製成，如果你不更改版本號，書檔會以相同檔名覆蓋過去，持續書寫或編輯、修改時可以這樣用。一旦你將版本號改成 `0.4`，會製成一個新的檔案，舊的版本檔案也會保留下來。

這種顯性的版本設定，是為了未來的發行程序，例如書籍以 `1.0` 版發行了之後，就應該將編輯版號改成 `1.1` 或 `1.0.1`，等到準備好之後再釋出升級版。

製書索引中也有個開關： `build: true`，設定為 `false` 就不會自動製作。例如你的書籍停留在一個正式版本 `1.0`，後續沒有任何修改，就可以「關掉」這本書的自動製作程序，不需要每次執行程式都拿相同內容製作、覆蓋書檔。

在終端機下輸入 `node index.js` 就會執行自動製書程式。

製作出來的電子書是 EPUB 3 格式，同時也會轉製出 Kindle（`.mobi`）的同名版本。（update: 在製書指引檔中添加了 `kindle: true/false` 的選項，可以控制是否同步自動生成 Kindle 版本。）

### 基礎設定檔

目錄下的 `config.md` 檔案，可以設定書籍編輯專案擺放的目錄（projects）、製成的書籍要擺在哪個次目錄（books）、設定內容檔案的「製書索引檔」要叫什麼名字（book.md），以及書籍詮釋資料使用什麼預設檔名（metadata.md）。

```
---
base: 'projects'
dest: 'books'
index: 'book.md'
metafile: 'metadata.md'
---
```

如果沒有 `config.md` 設定檔，程式就會找這些目錄與檔名，找不到就無法製書。如果你依照預設的架構擺放檔案，可以殺掉 `config.md` 檔案無妨。

### 使用概念

