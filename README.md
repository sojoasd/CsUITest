# UI Test

此測試可以分為兩種方法，一種是透過 VS2013 的功能自動錄製，產生錄製後的程式碼；另外一種是寫錄製程式碼，這裡會透過一個範例說明上述
兩者作法。

* 錄製主程式的目錄：/CodeUITest/CodedUITest1.cs
* 錄製程式的目錄：/CodeUITest/UIMap.Designer.cs

## 一、教學影片

* 錄製器操作：[連結點](https://www.youtube.com/watch?v=WRRpXT8yxMI)
* 錄製程式撰寫：[連結點1](https://www.youtube.com/watch?v=MU7mmfQjOis)
                [連結點2](https://www.youtube.com/watch?v=QeQ4Lg56LHU)
                [連結點3](https://www.youtube.com/watch?v=NGZjQBe6NwY)

## 二、自動錄製

此專案範例是使用 VS2013 版本，步驟如下
####  1.建立專案
<img src="https://github.com/sojoasd/CsUITest/blob/master/CodeUITest/Image/%E5%BB%BA%E7%AB%8B%E5%B0%88%E6%A1%88.JPG" width="500" height="400" />

####  2.選取範圍
<img src="https://github.com/sojoasd/CsUITest/blob/master/CodeUITest/Image/%E5%BB%BA%E7%AB%8B%E7%AF%84%E5%9C%8D.JPG" width="500" height="100" />
<br>
* 在此範圍內點右鍵，一定要在這個 Scope 內才能建立錄製哦!

####  3.啟動錄製器
<img src="https://github.com/sojoasd/CsUITest/blob/master/CodeUITest/Image/%E5%95%9F%E5%8B%95%E9%8C%84%E8%A3%BD%E5%99%A8.JPG" width="500" height="180" />

####  4.錄製器UI說明
<img src="https://github.com/sojoasd/CsUITest/blob/master/CodeUITest/Image/%E9%8C%84%E8%A3%BD%E5%99%A8UI.JPG" width="500" height="120" />
<br>
* 開始/停止
* 即時顯示錄製過程
* 選取畫面的物件，如輸入框，目前 **Chrome 不適用**，而且不太好控制
* 產生程式碼，一旦點選後會立即停止錄製

####  5.開始錄製
<img src="https://github.com/sojoasd/CsUITest/blob/master/CodeUITest/Image/%E9%8C%84%E8%A3%BD%E9%96%8B%E5%A7%8B.JPG" width="500" height="280" />
<br>
* 在欲錄製的畫面點選開始，如從簽核範本新增頁面開始錄製，**記得下次啟動時也要從這個畫面開始**

####  6.錄製完成
<img src="https://github.com/sojoasd/CsUITest/blob/master/CodeUITest/Image/%E9%8C%84%E8%A3%BD%E5%AE%8C%E6%88%90.JPG" width="500" height="100" />
<br>
* 錄製完成後會在剛剛 Scope 內出現此段程式碼，點 `F12` 可以看到完整的錄製程式

####  7.執行測試
<img src="https://github.com/sojoasd/CsUITest/blob/master/CodeUITest/Image/%E9%96%8B%E5%A7%8B%E5%9F%B7%E8%A1%8C.JPG" width="500" height="300" />
<br>
* 在剛剛 Scope 內點右鍵「執行測試」
 
####  8.執行成功
<img src="https://github.com/sojoasd/CsUITest/blob/master/CodeUITest/Image/%E5%9F%B7%E8%A1%8C%E6%88%90%E5%8A%9F.JPG" width="500" height="100" />
<br>
* 若成功可以看到綠色勾勾，若失敗則會出現 X ，點 X 會顯示錯誤訊息，通常錄製程式失敗都是抓不到畫面物件

## 三、客製錄製程式碼

為何要客製程式?
因若在操作上突然想再加入某個動作或是判斷，那又要大費周章的再錄一次，若能客製某段程式，只加入一小段動作或判斷才夠方便!
<br>
** 這裡請參考檔案目錄為：/CodeUITest/UIMap.Designer.cs **

####  1.找 HtmlDocument 物件
此 HtmlDocument 物件是整個 UI 操作畫面所擷取的物件，透過此物件可以抓取畫面內的所有 Html Dom 物件，等等會用到
<img src="https://github.com/sojoasd/CsUITest/blob/master/CodeUITest/Image/%E6%89%BEHtmlDocument.JPG" width="500" height="100" />
<br>
* 在開頭找很像的，若不確定他是否為 HtmlDocument 物件，則可以點 `F12` 來看，如下圖

<img src="https://github.com/sojoasd/CsUITest/blob/master/CodeUITest/Image/%E6%89%BEHtmlDocument2.JPG" width="500" height="150" />

####  2.找 Html Dom 物件
剛剛錄製的程式只選完「是否設定條」為是後的畫面，那這裡我們就繼續接下去，建立一個名為 Hello 的 Group，而為了要讓程式知道你點了哪個按鈕，輸入了什麼，這些都必須知道是哪些 Html 物件，此時我們需先知道這些 Html 物件的屬性，如下圖
<img src="https://github.com/sojoasd/CsUITest/blob/master/CodeUITest/Image/%E6%89%BEDom%E7%89%A9%E4%BB%B6.JPG" width="500" height="50" />

