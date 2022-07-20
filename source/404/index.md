---
title: '404 - 好巧耶，在這遇見你！'
date: 2022-07-20 17:35:18
permalink: /404.html
---

## 這是一個不存在的頁面

很抱歉，你目前存取的頁面並不存在。

預計將在約 <span id="timeout">5</span>秒後返回首頁。

如果你很著急想看文章，你可以 **[點這裡](https://colinchiu87.github.io/)** 返回首頁。

<script>
  let countTime = 5;
  function count(){
    document.getElementById('timeout').textContent = countTime;
    countTime -= 1;
    if(countTime === 0){
      location.href = 'https://colinchiu87.github.io/';
    }
    setTimeout(() => {
      count();
    }, 1000);
  }

  count();
</script>
