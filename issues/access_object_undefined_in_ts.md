[问题记录](../README.md)


## 访问```TypeScript```中没有定义的变量

### 症状

桌面程序加载浏览器时给```window```对象添加自定义属性，而```TS```中的```window```没有自定义属性的定义，在程序中访问自定属性报错:```undefined```。同时使用```AOT```方式，无法通过编译

### 问题代码

xxx.component.ts:
```ts

···
···
window.myApp.log('写日志');
···
···

```

### 原因

```TS```类型检查比较严格。

### 解决办法

利用数组的方式绕过TS的类型检查

### 修改后的代码

xxx.component.ts:
```ts

···
···
let myapp = window['myApp'];
myapp.log('写日志');
···
···
```


[问题记录](../README.md)