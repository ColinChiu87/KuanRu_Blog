---
title: 為什麼Vue中的data有時候會看到return，而有時候卻沒有？
date: 2021-07-13 19:46:10
tags: Vue.js
---
在簡單的vue實例中看到的data屬性如下：
```js
let app = newVue({
    el: "app",
    data:{
        msg:'',
    },
    methods:{

    },
})
```

在使用組件化的項目中使用的形式是如下：
```js
export default {
    data(){
        return{
            msg:'',
        }
    },
    methods:{

    },
}
```

而這兩邊的差異呢就在於 **不使用return包覆** 的資料會在全局都可見，這會造成變數污染。
反之 **用return的資料** 就只會在當前的component生效而已，不會影響到其他組件。
