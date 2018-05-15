[问题记录](../README.md)


## 从远程clone下来的Angular项目编译出错

### 症状

1.    在其他电脑上运行调试完毕之后将Angular项目上传到GitHub
1.    本机clone能够正常运行的代码
1.    执行```cnpm install```安装依赖到本地
1.    执行```npm start```或者```ng build -prod```

### 问题代码

``` shell
PS E:\projects\git\z-shop\admin-ui> ng build -prod
Your global Angular CLI version (6.0.0) is greater than your local
version (1.6.0). The local Angular CLI version is used.

To disable this warning use "ng config -g cli.warnings.versionMismatch false".
 95% emittingUnhandled rejection Error: ENOENT: no such file or directory, open 'E:\projects\git\z-shop\admin-ui\node_modules\_@angular_common@5.2.10@@angular\package.json'
```

### 原因

具体不知道啥原因。cnpm用来更新还是比较好，还是别用来第一次安装依赖了。

### 解决办法

删掉之前的```node_modules```文件夹，使用```npm install```安装依赖。

### 修改后的代码

```
npm install
```

[问题记录](../README.md)