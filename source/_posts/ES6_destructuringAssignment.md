---
title: ES6-解構賦值
date: 2022-01-03 20:54:09
tags: ["javascript", "ES6"]
---
# 說文解字

解構賦值(Destructuring Assignment)是在ES6的一個新特性，讓我們在撰寫物件、陣列時可以把在裡頭的資料解開擷取成為獨立的變數，能夠更簡短並增加閱讀性。
以下為他的說明：
> The destructuring assignment syntax is a JavaScript expression that makes it possible to extract data from arrays or objects using a syntax that mirrors the construction of array and object literals
<!--more-->
上面所說的就是解構賦值的用法如同**鏡子**(mirror)般，對應陣列or物件的結構，將資料從右邊往左邊送，只不過內容的位置順序不變（鏡子會左右顛倒），也就是一種樣式對應(pattern)的方法。

介紹比較常用的情況：

- 從陣列解構賦值
- 從物件解構賦值
- 解構賦值給定預設值
- 搭配函式的傳入參數使用

# 陣列

```js
let str = 'hello';
let [a, b, c, , d, f] = str;

// a='h', b='e', c='l', d='o' 留空白就會跳過
// f=undefined  如果左方變數多於右方，則會顯示undefined
// 這邊也順便帶入一個概念是分解字串
```

接下來要說的是我覺得很方便的用法“互換”，一般我們要互換兩個變數要多宣告一個第三變數才能完成，這邊我們可以直接完成。

```js
let a = 1, b = 2;
[b, a] = [a, b];

// 此時的 a=2, b=1
```

# 物件

這邊的概念和陣列一樣，不過陣列是利用順序的索引值對照，而物件是用屬性名稱來對應(所以沒有順序性)。

```js
let family = { me: 'colin', sis: 'candy'};

// 一般寫法
let me = family.me;
let sis = family.sis;

//縮寫
let {me, sis} = family;

// me:colin, sis:candy
```

物件的解構還能重新賦予變數的名稱

```js
let player = { jordan: '喬丹', wade: '偉德'};
let { jordan: king } = player;

//此時king的值為'喬丹'
```

# 混合使用

```js
let { jordan: king, family: [, ...member] } = { jordan: '喬丹', family: ['阿姨', '老媽', '老爸'] }
console.log(king, member); // 請問答案是什麼？ Ans: king:'喬丹', member: ['老媽', '老爸']

//p.s 其餘運算子用法 (...變數)：將陣列展開成個別值灑進去。
```

# 預設值

在等號左邊是可以給預設值的，避免未被賦值時造成undefined。

```js
let [jordan = '喬丹', lebron = '雷霸龍'] = ['阿明'];
// jordan值為'阿明'
// lebron則為預設值'雷霸龍'
```

陷阱題

```js
const { a ='hello' } = 'hello'
const [ b ='hello' ] = 'hello'
// 此時 a, b 分別為什麼呢？
```

# 函式

在函式要傳參數時也可以使用解構，參數一樣能夠自訂變數名稱、順序、預設值等

```js
function func({a = 1, b}) {
  return a + b
}

func({a: 1, b: 2}) // 3
func({b: 2}) // 3
func({b: 6, a: 3}) // 9
func({a: null, b: 2}) // 2
```

> 註：所以在函式傳入參數中作解構賦值時，給定null值時會導致預設值無用，請記住這一點。當數字運算時，null相當於0。
