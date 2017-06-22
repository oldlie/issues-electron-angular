### Can't bind to 'ngModel' since it isn't a known property of 'input'

查询官网文档可知 ```ngModel``` 指令存在于 ```npm package: @angular/forms```, 参考官网样例在对应的 ```Module``` 中导入 
```
import { FormsModule } from "@angular/forms";
```

### URL中带有 ```unsafe``` 字样导致数据不能加载

在 COMPONENT 中引入 ```import { DomSanitizer } from "@angular/platform-browser";```
将含有 URL 的代码修改为：
```
let url = this.sanitizer.bypassSecurityTrustUrl(url);
```

----

### 删除 TS 文件中相关引用的变量，但是在编译之后仍然出现该引用变量的错误

检查下对应的 HTML 文件中是否有该变量的引用。

----

### npm 安装 SQLite3 失败之后 ``` electron . ``` 命令失效

重新用 ``` npm install electron ``` 就好了。

----

### Angular 测试时出现： ``` 'router-outlet' is not a known element: ``` 错误

需要在测试文件中添加导入声明：
```
import { RouterTestingModule } from "@angular/router/testing";

  beforeEach(async(() => {
    TestBed.configureTestingModule({
      imports: [
        RouterTestingModule,
      ],
      declarations: [
        AppComponent
      ],
    }).compileComponents();
  }));
```

参考文档： [ANGULAR COMPONENT TESTING WITH ROUTERLINK AND ROUTEROUTLET](http://www.kirjai.com/ng2-component-testing-routerlink-routeroutlet/ "router-outlet is not a konw element")

----

### VSCode 提示 ```this.http.post(url,data).toPromise()```  中没有 ```toPromise()``` 方法

需要引入rxjs, 解决方案如下：

1.    如果有 ```vendor.ts``` 文件则在 ```vendor.ts``` 中添加 
    ```
    // RxJS
    import 'rxjs';
    ```

1.    如果没有 ```vendor.ts``` 则在 ```polyfills.ts``` 中添加
    ```
    // RxJS
    import 'rxjs';
    ```

参考文档： [Angular JS 2 HTTP Post: Object doesn't support property or method 'toPromise'](https://stackoverflow.com/questions/36673820/angular-js-2-http-post-object-doesnt-support-property-or-method-topromise)

----

### 执行 ```node_modules/.bin/ngc -p tsconfig-aot.json``` 命令时出现错误

执行 ```node_modules/.bin/ngc -p tsconfig-aot.json``` 命令时出现错误： 
```Error Unknown compiler option 'angularCompilerOptions'.```
是因为 ```@angular/compiler``` 和 ```@angular/compiler-cli``` 的版本号不一致引起的。
解决办法就是安装 ```@angular/compiler-cli``` 时指定版本号
 ```npm install "@angular/compiler-cli@^4.2.1" --save```

 ----