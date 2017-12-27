[问题记录](../README.md)


## ```nginx```做代理，```response```的数据被截断

### 症状

访问```nginx```代理的数据接口时发现返回的```json```数据格式不正确，数据被截断，部分数据没有返回。
不通过代理直接访问数据接口，数据返回正确。

### 问题代码

```log
2017/12/16 10:00:57 [error] 3468#3176: *307495 WriteFile() "D:\nginx-1.11.13/temp/proxy_temp/3/74/0000011743" failed (112: There is not enough space on the disk) while reading upstream, client: 42.80.206.112, server: localhost, request: "POST /api-beta/packages-list HTTP/1.1", upstream: "http://127.0.0.1:8090/api-1.1.11/packages-list", host: "down.xxx.com"
```

### 原因

```nginx```所在服务器磁盘空间被占完了。```nginx```在代理数据时，如果返回的数据长度超过了设定值，需要把超长部分写到磁盘。
而此时磁盘空间已经满了,因此只能返回部分不需要缓存到磁盘的数据。
通常```linux```也会出现这种问题，而```linux```上是因为nginx没有写temp文件夹的权限。

### 解决办法

清理磁盘空间。


[问题记录](../README.md)