[问题记录](../README.md)


## 使用 node API ``` fd = fs.openSync(path, 'w'); ``` 出现 ``` Error: ENOENT: no such file or directory ``` 错误

fs 相关函数只能创建文件，即最后一层指定的文件如果不存在，则创建。在指定路径上如果有文件夹不存在，直接使用 ```open``` 相关方法是不会
创建相应的父文件夹的。因此当遇到这类型问题时需要仔细检查路径是否完整创建。

[问题记录](../README.md)
