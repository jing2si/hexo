---
title: 常用数组操作
date: 2017-01-24 17:45:54
tags: array
categories: 前端
---

```javascript
/**
 * 数组增加去重功能
 * 调用例子：[1, 2, 3, 3].unique() => [1, 2, 3]
 */
Array.prototype.unique = function () {
  return this.filter(function (value, index, self) {
    return self.indexOf(value) === index;
  })
}

/**
 * 数组交集
 * 调用例子：[1, 2, 3].intersection([2, 3, 4]) => [2, 3]
 */
Array.prototype.intersection = function (array) {
  return this.filter(function (value) {
    return array.indexOf(value) !== -1;
  });
};

/**
 * 数组差集
 * 调用例子：[1, 2, 3].diff([2, 3, 4]) => [1]
 */
Array.prototype.diff = function (array) {
  return this.filter(function (value) {
    return array.indexOf(value) == -1;
  });
};

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
