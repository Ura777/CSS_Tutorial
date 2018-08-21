# CSS_Tutorial
## 目錄
* [環境設置](https://github.com/Ura777/CSS_Tutorial#%E7%92%B0%E5%A2%83%E8%A8%AD%E7%BD%AE)
* [Java環境變數設置](https://github.com/Ura777/CSS_Tutorial#java%E7%92%B0%E5%A2%83%E8%AE%8A%E6%95%B8%E8%A8%AD%E7%BD%AE)
* [Visual Studio Code相關設定](https://github.com/Ura777/CSS_Tutorial#visual-studio-code%E7%9B%B8%E9%97%9C%E8%A8%AD%E5%AE%9A)
* [課程介紹](https://github.com/Ura777/CSS_Tutorial#%E8%AA%B2%E7%A8%8B%E4%BB%8B%E7%B4%B9)
  * [Ch01 - Tomcat的管理](https://github.com/Ura777/CSS_Tutorial#ch01---tomcat%E7%9A%84%E7%AE%A1%E7%90%86)
  * [Ch02- 基本的CSS](https://github.com/Ura777/CSS_Tutorial#ch02--%E5%9F%BA%E6%9C%AC%E7%9A%84css)
  * [Ch03 - 字型、文字與清單](https://github.com/Ura777/CSS_Tutorial#ch03---%E5%AD%97%E5%9E%8B%E6%96%87%E5%AD%97%E8%88%87%E6%B8%85%E5%96%AE)
  * [Ch04 - Box Model](https://github.com/Ura777/CSS_Tutorial#ch04---box-model)
* * *
## 環境設置
* 作業系統 = Windows 7
* JDK版本 = [1.8.0_171](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)
* Apache Tomcat版本 = [9.0.8](https://tomcat.apache.org/download-90.cgi)
* Visual Studio Code版本 = [Windows x64 User Installer Stable Build](https://aka.ms/win32-x64-user-stable)
* * *
## Java環境變數設置
* 取得並複製JDK安裝路徑  
 
        路徑通常為：  
		C:\Program Files\Java\jdk1.8.0_162
 
* 控制台 &gt; 所有控制台項目 &gt; 系統 &gt; 點選右邊的進階系統設定 &gt; 點選上方的進階標籤 &gt; 環境變數
* 在Administrator的使用者變數(U)區塊中點選新增按鈕，根據對應的欄位輸入以下的資料：  
 
    | 欄位名稱      | 輸入內容                            |
    |:-------------:|:-----------------------------------:|
    | 變數名稱(N)   | JAVA_HOME                           |
    | 變數值(V)     | C:\Program Files\Java\jdk1.8.0_162  |
 
* 在系統變數(S)的區塊中點選變數名稱為Path的選項 &gt; 點選編輯按鈕
* 按下鍵盤的右方向鍵 &gt; 輸入分號 &gt; 輸入以下內容：  
 
        %JAVA_HOME%\bin;
 
* 輸入完之後，一直按下確定按鈕。
* 打開命令提示字元視窗，輸入以下指令後按下Enter：  
 
        java
 
* 出現列表Java的功能列表，代表環境變數設置成功。
* * *
## Visual Studio Code相關設定
* 更改字體大小
  * 上方選單點選檔案 &gt; 喜好設定 &gt; 設定
  * 點選右邊視窗的使用者設定標籤，在下方輸入以下程式碼：
 
        {  
            "editor.fontSize": 22
        }
 
  * 按下快捷鍵Ctrl+S儲存
* * *
## 課程介紹
## Ch01 - Tomcat的管理
* 更改通訊埠
  * 去安裝Tomcat的路徑中尋找server.xml
 
        路徑通常為：  
		C:\Program Files\Apache Software Foundation\Tomcat 9.0\conf\server.xml
 
  * 使用文字編輯器開啟server.xml &gt; 尋找以下的程式碼：
 
        <Connector port="8080" protocol="HTTP/1.1"  
               connectionTimeout="20000"  
               redirectPort="8443" /> 
 
  * 將8080改成想要設定的數字
 
        例如：
		80
 
  * 修改完成後儲存檔案 &gt; 重新啟動Tomcat
* 虛擬資料夾與真實資料夾的對應
  * 去安裝Tomcat的路徑中尋找server.xml
 
        路徑通常為：  
		C:\Program Files\Apache Software Foundation\Tomcat 9.0\conf\server.xml
 
  * 使用文字編輯器開啟server.xml &gt; 尋找以下的程式碼：
 
        <Host name="localhost"  appBase="webapps"  
            unpackWARs="true" autoDeploy="true">
 
  * 在上述的程式碼下方新增以下的程式碼：
 
        <Context path="/虛擬資料夾名稱" docBase = "實體資料夾位置" debug="0" />  
		  
		例如：  
		<Context path="/test" docBase = "C:\CSS_Tutorial" debug="0" />
 
  * 修改完成後儲存檔案 &gt; 重新啟動Tomcat
  * 虛擬資料夾與實體資料夾的名稱都不能有中文字
* * *
## Ch02- 基本的CSS
* CSS
  * 階層式樣式表
  * Cascading Style Sheet
  * 選擇器(Selector)與規則(rule)組成
  * 規則內為屬性:值
  * 以分號做為屬性之間的建隔
 
        例如：
        h1{
            color: red;
        }
 
* 使用方式
  * 行內宣告
  * 在標籤內使用style屬性
  * 內嵌宣告
    * 使用style標籤
    * 連結外部CSS檔案
    * 使用link標籤
    * 在style標籤內使用@import
* Class選擇器
  * 選擇器的開頭為.
* Id選擇器
  * 選擇器的開頭#
* Attribute選擇器
  * 選擇器為[屬性名稱與篩選方式]
 
        例如：
        [class~="test"]{
            background-color: red;
        }
 
  * 篩選方式如下：
    * [attribute = "value"] ->  屬性等於value
    * [attribute ~= "value"] -> 屬性包含完整value
    * [attribute |= "value"] -> 屬性等於value或是以value開頭
    * [attribute ^= "value"] -> 屬性開頭有value
    * [attribute $= "value"] -> 屬性最後有value
    * [attribute *= "value"] -> 屬性有出現value
* * *
## Ch03 - 字型、文字與清單
* color
  * 文字顏色
* font-family
  * 字體
* font-size
  * 字體大小
* font-style
  * 文字斜體
* font-weight
  * 文字粗體
* text-align
  * 文字對齊方式
* text-indent
  * 首行縮排
* letter-spacing
  * 字元間距
* word-spacing
  * 文字間距
* line-height
  * 行高
* text-show
  * 文字陰影
* list-style-type
  * 項目符號與編號類型
* list-style-image
  * 圖片項目符號
* list-style-position
  * 項目位置
* list-style
  * 可以同時設定list-style-type、list-style-position與list-style-image。
* * *
## Ch04 - Box Model
* margin
  * 邊界
* border-style
  * 邊框樣式
* border-width
  * 邊框寬度
* border-color
  * 邊框顏色
* border
  * 邊框綜合設定
  * 可以同時設定border-color、border-width與border-style。
* border-radius
  * 邊框導圓角
* border-image
  * 圖片邊框
* padding
  * 邊界留白
* * *


