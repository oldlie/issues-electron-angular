[问题记录](../README.md)


## 正则```/^[A-Za-z0-9]{6, 20}$/```匹配6到20个数字或字母字符不正确

### 症状

使用正则表达式简单匹配一个仅由6到20字符的字符串总是返回```false```

### 问题代码

```js
const reg = /^[A-Za-z\d]{6, 20}$/;
console.log(reg.test('123456'));
```

### 原因

范围语法错误，6和20之间不应该有空格。从IDE颜色的提示也能看出端倪。错误语法时，着色为字符串颜色，正确语法为其他颜色。

### 解决办法

删除6和20之间的空格

### 修改后的代码

```js
const reg = /^[A-Za-z\d]{6,20}$/;
console.log(reg.test('123456'));
```


[问题记录](../README.md)