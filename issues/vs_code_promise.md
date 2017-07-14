[问题记录](../README.md)

## VSCode 提示 ```this.http.post(url,data).toPromise()```  中没有 ```toPromise()``` 方法

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

[问题记录](../README.md)