[问题记录](../README.md)


## 同一父组件接收不同子组件同名事件时发生'subscribe not found'的错误

### 症状

在父组件新添加一个组件，该组件关闭事件名称为```closed```。触发打开该组件事件时报错：```subscribe ....```

错误的：parent.component.html
```
...
<app-waring-box *ngIf="warningBoxShow" [data]="tipData" (closed)="onWarningBoxClosed($event)"></app-waring-box>
<app-rename-box *ngIf="renameBoxShow" (closed)="onRenameBoxClosed($event)"></app-rename-box>
...
```

### 原因

父组件中已经含有一个组件[1]。组件[1]中也向父组件发送关闭自身组件事件```closed```。当新添加的组件也发送```closed```事件时，父组件
会发生错误。

### 解决办法

将新组件中的事件名称更改为更具体的事件名称，例如```xxxComponentClosed```

修改后的：parent.component.html
```
...
<app-waring-box *ngIf="warningBoxShow" [data]="tipData" (closed)="onWarningBoxClosed($event)"></app-waring-box>
<app-rename-box *ngIf="renameBoxShow" (xxxComponentClosed)="onRenameBoxClosed($event)"></app-rename-box>
...
```

[问题记录](../README.md)