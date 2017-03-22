---
title: 常用数组操作
date: 2017-01-24 17:45:54
tags: 数组
categories: 前端
---

#### 普通数组去重

```javascript
/**
 * 普通数组去重
 * 调用例子：[1, 2, 3, 3].unique() => [1, 2, 3]
 */
Array.prototype.unique = function () {
  return this.filter(function (value, index, self) {
    return self.indexOf(value) === index;
  })
}
```

#### 对象数组去重

```javascript
/**
 * 对象数组去重
 * @param {String} key 用作比较的对象key
 * 调用例子：[{id:1, age: 20}, {id:2, age: 30}, {id:1, age: 20},].uniqueBy('id') => [{id:1, age: 20}, {id:2, age: 30}]
 */
Array.prototype.uniqueBy = function (key) {
  var result = [];
  var arrObject = this;
  var cache = {}
  var arr = arrObject.map(function (value, index, self) {
    return value[key]
  })
  arr = arr.filter(function (value, index, self) {
    return self.indexOf(value) === index
  })

  arr.forEach(function (value, index, self) {
    arrObject.forEach(function (v, i, s) {
      if (!cache[value] && (value === v[key])) {
        result.push(arrObject[i])
        cache[value] = 1
      }
    })
  })
  return result;
}
```

<!--more-->

#### 数组交集

```javascript
/**
 * 数组交集
 * 调用例子：[1, 2, 3].intersection([2, 3, 4]) => [2, 3]
 */
Array.prototype.intersection = function (array) {
  return this.filter(function (value) {
    return array.indexOf(value) !== -1;
  });
};
```

#### 数组差集

```javascript
/**
 * 数组差集
 * 调用例子：[1, 2, 3].diff([2, 3, 4]) => [1]
 */
Array.prototype.diff = function (array) {
  return this.filter(function (value) {
    return array.indexOf(value) == -1;
  });
};
```

#### 删除指定元素

```javascript
/**
 * 删除指定元素
 * @param {any} element 需要删除的元素
 * 调用例子 [1, 2, 3].remove(2) => [1, 3]
 */
Array.prototype.remove = function (element) {
  var index = this.indexOf(element)
  if (index > -1) {
    this.splice(index, 1)
  }
  return this;
}
```
