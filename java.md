# 设置

## tomcat 远程调试

```java
-Xdebug -Xrunjdwp:transport=dt_socket,suspend=n,server=y,address=9999
```

## IDEA控制台乱码
在IDEA安装根目录下，打开`/bin/idea64.exe.vmoptions`文件，在末尾添加配置
```java
-Dfile.encoding=UTF-8
```


