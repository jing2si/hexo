---
title: 常用正则表达式
date: 2016-05-26 10:05:40
tags: 正则
categories: 前端
---
#### 匹配手机号
```javascript
    /^1((3[0-9]|4[57]|5[0-35-9]|7[0678]|8[0-9])\d{8}$)/.test('电话号码')
```
#### 手机号中间四位换成*号
```javascript
    '15876543210'.replace(/(\d{3})\d{4}(\d{4})/, "$1****$2")
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

<!--more-->

#### 匹配不包含某字符串
```javascript
    /^(?!.*hello).*$/.test('hell')
    // true
```
#### 匹配emoji表情
```javascript
/\ud83c[\udf00-\udfff]|\ud83d[\udc00-\ude4f]|\ud83d[\ude80-\udeff]/g.test('😀')
// true
```
#### 字符串插入
```javascript
'1234'.replace(/(.{2})/, '$1入')
// 12入34
```
[在线验证正则](https://regex101.com/)
