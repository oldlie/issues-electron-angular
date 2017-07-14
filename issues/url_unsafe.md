[问题记录](../README.md)


## URL中带有 ```unsafe``` 字样导致数据不能加载

在 COMPONENT 中引入 ```import { DomSanitizer } from "@angular/platform-browser";```
然后在构造函数中注入 ```constructor(private sanitizer: DomSanitizer){ }```
最后将含有 URL 的代码修改为：
```
let url = this.sanitizer.bypassSecurityTrustUrl(url);
```

[问题记录](../README.md)