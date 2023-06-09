# My-Pet-Record

## Set Up
```
npm install
```
## Run Dev
```
npm run dev
```
open http://localhost:3001/ and start to develop

## Demonstration
```
npm run start
```
open http://localhost:3001/ 
## Structure

### My-Pet-Record
* app.js
* bin
	* www
* package.json
* public
    * css ... 有點太瑣碎，之後會整理少數檔案
    * img
    * js
    * json
        * zh-tw/ja-jp/en-us ... 根據 cookie 讀取個個語言的 data.json
            * data.json ... 如果之後資料太多可能會把各個頁面需要的抽出來留每頁都會需要的
* routes
    * index.js
    * route.js ... 原本想包成 modules 讓 index.js 去 import 設定路徑
* views
    * error.pug ... 未來會去設計能給使用者看到的錯誤頁面
    * layout.pug ... 存放固定 header&footer
    * 其餘一般頁面

## 主要設計功能：
* 多語言化（使用cookie與渲染時傳入相應語言的 json 資料）
* 用JS做Slider（可用左右箭頭及下方橫條切換）
* 用 Json 檔使同樣程式碼的程式碼不需重複，且方便修改
* 增加投影片時只需新增json資料不需要去動到頁面的程式碼
* 在用 route.js 設定路徑時不用一個一個設定用，且新增頁面時只需要修改 route.js 檔案會自行追加
* 針對手機及電腦瀏覽做不同的對應（RWD），其中還有配合js去做Menu的展開及關閉
* 利用 CSS transition & animation 讓網頁不過於靜態
* 當捲軸往下時會自動出現的回到最頂按鈕
* Header 可以依據卷軸滑動及位置顯示或隱藏
* 使用base.css寫共用的CSS，也因為希望能有較細微的調整，比如説height、width等，用了scss跑for loop設定多個 class