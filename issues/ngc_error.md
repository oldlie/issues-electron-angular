[问题记录](../README.md)

## 执行 ```node_modules/.bin/ngc -p tsconfig-aot.json``` 命令时出现错误

执行 ```node_modules/.bin/ngc -p tsconfig-aot.json``` 命令时出现错误： 
```Error Unknown compiler option 'angularCompilerOptions'.```
是因为 ```@angular/compiler``` 和 ```@angular/compiler-cli``` 的版本号不一致引起的。
解决办法就是安装 ```@angular/compiler-cli``` 时指定版本号
 ```npm install "@angular/compiler-cli@^4.2.1" --save```


[问题记录](../README.md)