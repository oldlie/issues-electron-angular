[问题记录](../README.md)


## 子组件利用```output```向父组件发送事件报错

### 症状

在子组件中定义```output```相关成员变量，在父组件中添加事件之后，界面无法显示，Debug工具提示如下错误

> core.es5.js:1020 ERROR Error: Uncaught (in promise): TypeError: Cannot read property 'subscribe' of undefined(…)

### 问题代码

child.component.ts:
```ts

···
···
@Output() onPageClicked: EventEmitter<number>;
···
···

```

parent.component.html:
```html

···
···
<app-child (onPageClicked)="onPaginationClicked()"></app-child>
···
···

```

### 原因

```Output```修饰的成员变量需要实例化，否则父组件中的事件响应方法实际上是绑定到一个空属性上去，因此报错。

### 解决办法

将子组件中```Output```修饰的变量实例化

### 修改后的代码

child.component.ts:
```ts

···
···
@Output() onPageClicked =new EventEmitter<number>();
···
···
```


[问题记录](../README.md)