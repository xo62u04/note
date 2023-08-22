# coding 原則
基本：
**S: Single responsibility principle(SRP) 單一職責**
```
一個class做一件事情
一個function做一件事情
```
**O: Open/close principle(OCP) 開放/封閉原則**
```
改了A功能，要最小程度影響其他功能，最好是都不影響
```
**L: Liskov substitution principle(LSP) Liskov替換**
```
子類別可以取代父類別
```
**I: Interface Segregation Principle(ISP) 介面隔離**
```
將可拆分的功能，製作成不同的interface或是class，提供給其他function繼承、實作
```
**D: Dependency Inversion Principle(DIP) 依賴反轉**
```
父類別不能被子類別影響，不能因為function中的function，讓高層級的function受到影響
EX：
庫存推播的參數變動，導致呼叫庫存推播的地方要修改
成功的案例：庫存推播的事件建立，只需要來源端呼叫寫入pending程式，後面的庫存推播全部都會完成
```

三次原則：
同樣的function會有三個地方使用，要提出去當function 

命名原則：
```
常數命名
  常數名稱完全採用大寫英文字母。【PSR-1】
  必要時使用底線 _ （underscore）來區分單字。【PSR-1】
  如果內容有可能會改變，應改採用變數而非常數。
```
```
類別命名
  必須使用大寫開頭的駝峰式命名（camelCase），又稱爲 TitleCase。【PSR-1】
  extends 和 implements 關鍵字需和類別名稱在同一行。【PSR-2】
```
```
方法命名
  必須使用小寫開頭的駝峰式命名（camelCase）。【PSR-1】
  小寫字母開頭，後面每個單字的第一個字母大寫。【PSR-1】
  當參數的數量多長度超過最大值（80字）時，可以換行處理。換行後其他參數要縮排起始大括弧要在新的一行。【Zend 1】
```
```
檔案命名
  檔案名稱完全採用小寫英文字母。
  字與字之間使用底線 _ 連接（EX：show_table.php）。
  一定要使用 .php 作為副檔名。
  會被引入的設定內容以 .inc.php 結尾。
  檔名長度必須小於 32 個字元（符合舊式系統）。
```
```
變數命名
  變數應該要是駝峰式命名
  例如：
    $userRoles、cfFinancialGroups
```
laravel 5 命名規則
https://gist.github.com/jaceju/506c34ae999ea96b5d55
laravel 8 命名規則
https://webdevetc.com/blog/laravel-naming-conventions/
(大原則不變) 

Early return：
邏輯判斷在程式最前面，出錯提早離開，盡量不要在中間才判斷return跳出