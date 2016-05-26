---
title: 常用正则表达式
date: 2016-05-23 14:19:40
tags: 正则
categories: 前端
---
#### 匹配手机号
```javascript
    /^1((3[0-9]|4[57]|5[0-35-9]|7[0678]|8[0-9])\d{8}$)/g
```
#### 获取url参数
```javascript
    function getUrlVars() {
      var vars = {};
      window.location.href.replace(/[?&]+([^=&]+)=([^&]*)/gi, function(match, p1, p2) {
        vars[p1] = p2;
      });
      return vars;
    }
```
[regex101在线验证](https://regex101.com/)
