# Metalsmith

Gulp 已經簡化了另一種流程建構工具 Grunt，Metalsmith 則更加侷限了使用情境，主要是替內容生產者打造的微型工具。

Metalsmith 與 Gulp 同樣都讓核心 APIs 非常簡單，大多數的功能都使用「外掛」來實現。前者將功能限縮在數位內容的處理，必須理解它的運作基礎。

1. Metalsmith 預設是處理「來源目錄（src）」下面所有的檔案，即使你希望對不同類型的檔案做些微調，都必須在一條流程線中處理，例如可以在流程一時忽略掉檔案A群，在流程二時只處理檔案B群，但概念是所有檔案都一起通過每一道關卡。
2. Metalsmith 預設會解析文件上方的 YAML front-matter，依照標準將這個物件附加在單個文件上，於是就可以讓程式讀取這些屬性。

使用 Gulp 可以自行設計出與 Metalsmith 一模一樣的機制，只需使用 `gulp-front-matter` 套件讀取每份文件的 YAML 區段，後面可以自由配置。把 Metalsmith 當成 Gulp 流程中的一個特殊機具使用時，第一步驟也是解析、附加這些屬性到文件上。

Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo
consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse
cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo
consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse
cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo
consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse
cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
proident, sunt in culpa qui officia deserunt mollit anim id est laborum.


