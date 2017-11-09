[问题记录](../README.md)


## 使用VsCode自动导入模块代码，在aot编译时报找不到错误

### 症状

VSCode 更新到```1.18```版本。使用本版本提供的```auto import```功能导入一个```class```。使用```aot```方式编译报错：

> 'app/common/super-class' is imported by dist\out-tsc\src\app\common\child-component\child-component.component.js, but could not be resolved – treating it as an external dependency
> No name was provided for external module 'app/common/super-class' in options.globals – guessing 'pagination'

### 问题代码

```ts
···
import { SuperClass } from 'app/common/super-class';

···
export class ChildComponent extends SuperClass
···
```

### 原因

未知

### 解决办法

将```import { SuperClass } from 'app/common/super-class';```修改为相对```ChildComponent```位置的引用```import { SuperClass } from './super-class';```

### 修改后的代码

```ts
···
import { SuperClass } from './super-class';

···
export class ChildComponent extends SuperClass
···
```


[问题记录](../README.md)