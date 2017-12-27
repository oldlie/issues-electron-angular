[问题记录](../README.md)


## 使用一组分别独立的CheckBox控件时，绑定的事件响应参数总是第一个值

### 症状

在HTMLTemplate中创建数个CheckBox控件，并为每个控件绑定```onCheckType(t: string)```方法。试图通过```t```字段来区分每次点击的是
哪个CheckBox控件。然而，不管点击哪个CheckBox，总是只改变第一个CheckBox的值。

### 问题代码

checkbox.component.html：
```html
...
<ul>
    <li>
        <input type="checkbox" id="checkbox01" [checked]="a" (click)="onCheckType('a')">
        <label for="checkbox01" data-name="A"></label>
    </li>
    <li>
        <input type="checkbox" id="checkbox01" [checked]="b" (click)="onCheckType('b')">
        <label for="checkbox01" data-name="B" ></label>
    </li>
    <li>
        <input type="checkbox" id="checkbox01" [checked]="c" (click)="onCheckType('c')">
        <label for="checkbox01" data-name="C" ></label>
    </li>
    <li>
        <input type="checkbox" id="checkbox01" [checked]="d" (click)="onCheckType('d')">
        <label for="checkbox01" data-name="D" ></label>
    </li>
</ul>
...
```

### 原因

Angualr的事件绑定和HTML控件的ID相关，因为CheckBox的ID都设置成了同一个，因此事件绑定逻辑出现了错误。而且本身在HTML规范中，
ID不允许重复。

### 解决办法

去掉手动指定的CheckBox ID或者将ID各自ID指定为唯一值。

### 修改后的代码

checkbox.component.html：
```html
...
<ul>
    <li>
        <input type="checkbox" id="checkbox01" [checked]="a" (click)="onCheckType('a')">
        <label for="checkbox01" data-name="A"></label>
    </li>
    <li>
        <input type="checkbox" id="checkbox02" [checked]="b" (click)="onCheckType('b')">
        <label for="checkbox02" data-name="B" ></label>
    </li>
    <li>
        <input type="checkbox" id="checkbox03" [checked]="c" (click)="onCheckType('c')">
        <label for="checkbox03" data-name="C" ></label>
    </li>
    <li>
        <input type="checkbox" id="checkbox04" [checked]="d" (click)="onCheckType('d')">
        <label for="checkbox04" data-name="D" ></label>
    </li>
</ul>
...
```

[问题记录](../README.md)