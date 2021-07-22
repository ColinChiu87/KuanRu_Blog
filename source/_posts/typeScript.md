---
title: 來聊聊 Type Script
date: 2021-07-22 17:43:01
tags: ts
---
第一次在專案裡與 TS 相遇，那就不免俗的了解囉！

{% asset_img js-ts.jpg %}

稍微簡介一下～
TypeScript是由微軟開發的一種能用來編譯出JavaScript程式碼的程式語言，因其比JS還多了一道編譯手續，能夠在編譯階段找出語法上的問題，而且也添加了型別檢查的機制，讓程式更容易閱讀與偵錯，也更適合開發大型的專案。
白話一點來說，JS可以通過TS編譯器來編譯，而且還能夠實現JavaScript的版本轉換(例如ES6轉ES5)

# 安裝與設定
### Node.js
我們要先設定好Node.js和npm環境，建議使用Node.js最新的LTS版本。
Node.js是JavaScript程式的執行環境，讓我們不需要開啟瀏覽器也可以執行JS。而npm則是JS的套件管理器，常與Node.js一同被安裝。

Windows的使用者可以直接到[Node.js官方網站](https://nodejs.org/en/)下載，而Linux或MacOS的使用者可以參考[這篇文章](https://magiclen.org/linux-install-nodejs/)安裝指定版本。

### tsc
tsc是TypeScript程式的編譯器，能夠將TS編譯成JS。
執行以下npm指令:
```
npm i -g typescript
```
關於編譯器的設定，我就先不說明，一開始花太多時間在這會顯得有點浪費且沒意思，畢竟內容很龐大也很複雜。
***
# 簡單的範例
```ts
function func(name: string){
    return "Hello " + name;
}

func(colin)
```
這邊唯一和我們學過的JavaScript不同，就是func這個函式的傳入參數多一個 :string 的指示詞，這東西在ＴＳ裡稱做類型註解。這邊就是說傳入的參數只接受字串(string)的型態，只要是其他型別在呼叫或是執行時就會報錯。

對於函式而言，會有傳入參數和回傳值兩種情況，那麼我們就要養成習慣。
```ts
function func(name: string): string{
    return "Hello " + name;
}

func(colin)
```
上面這表示回傳值的型態也是string類型，順帶一提，如果函式沒有回傳值時可以使用 void，相信很多人都有看過吧，這就是專門為沒有回傳值的函式所準備的類型。

```ts
name: string | number = "Colin";
```
這裡的意思是 name這個變數能接受的型態為字串(string)與數字(number)，而且預設值為 Colin字串。
***
