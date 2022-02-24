---
title: 编码（WIP）
date: 2022-02-24 21:19:04
tags:
  - Identifier
  - 变量名
  - Emoji
  - 颜文字
---

# 源码

源码规定使用 utf16 编码

1. Javascript 源码可以是任何编码
1. Javascript 中字符串使用的是 UTF16 编码

https://262.ecma-international.org/6.0/#sec-source-text

https://dmitripavlutin.com/what-every-javascript-developer-should-know-about-unicode/
https://www.quora.com/Why-are-unicode-characters-outside-the-BMP-called-astral
https://en.wikipedia.org/wiki/Plane_(Unicode)#Basic_Multilingual_Plane
https://stackoverflow.com/questions/43150498/how-to-get-all-unicode-characters-from-specific-categories

# 字符串

## 获取字符串对应的码点数组

String 类型实现的[迭代器协议](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/@@iterator)返回字符串的码点序列，每个码点以**字符串**形式返回。

```js
let string = '\ud83d\udc0e\ud83d\udc71\u2764'

for (let codePoint of string) {
  console.log(codePoint.codePointAt(0).toString(16))
}
// '1f40e', '1f471', '2764'

Array.from(string)

// 内部使用了迭代器协议
Array.prototype.forEach.call((codePoint) => {
  console.log(codePoint)
})

Array.prototype.map.call((codePoint) => {
  console.log(codePoint)
})
```

## 字符串转义序列

https://262.ecma-international.org/6.0/#sec-literals-string-literals

# 正则表达式中的转义序列

# 参考资料

1. [JavaScript 与 Unicode](https://cjting.me/2018/07/22/js-and-unicode/)
