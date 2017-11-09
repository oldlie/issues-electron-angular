[问题记录](../README.md)

## Angular 2 Expression Changed After It Has Been Checked Exception

在加载动态组件时遇到 Angular 抛出这个异常，我在代码中的解决方案：

```ts
this.cdr.detach(); // 停止检测
let componentRef = viewContainerRef.createComponent(componentFactory);
(<ModalBodyComponent>componentRef.instance).data = this.config.data;
setTimeout(() => this.cdr.reattach()); // 待组件动态加载完之后重新 attach
```

detach() 方法的文档：

> Detaches the change detector from the change detector tree.

参考文档: [Angular 2 Expression Changed After It Has Been Checked Exception](http://www.allenhashkey.com/web-development/angular2/angular-2-expression-changed-after-it-has-been-checked-exception/)

[问题记录](../README.md)