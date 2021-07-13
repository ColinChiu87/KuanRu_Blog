---
title: 什麼時候該使用『 const vm = this 』
date: 2021-05-12 13:28:43
tags: Vue.js
---

 ** 影響this的是在於*函式的呼叫方式* **

以下為this的範例
```js
reverseText: function(){
    return this.text.split('').reverse().join('');
}
```

在第一個範例中，this運行後都是在這個元件底下
並沒有另外的函式在內（ex: forEach）
全部的this都是指向**Vue的該元件**
因此不需要另外使用 vm = this

至於使用 vm = this 可以避免內部有其他函式叫
導致 this 的運作不如預期。
```js
//因為在""內層函式""filter的函式內使用到this，指向會跑掉，所以需要使用vm。
filterArray: function(){
    var vm = this;
    return vm.arrayData.filter(function(){
        return item.name.match(vm.filterText)
    })
}
```
 ** 除了使用 filter/ forEach 會讓this指向window外，函式在直接呼叫的時候this也會指向window **
