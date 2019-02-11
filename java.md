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

## SpringBoot热更新
 - 先在pom文件中添加依赖
```java
<!-- 热加载 -->
<dependency>
	<groupId>org.springframework</groupId>
	<artifactId>springloaded</artifactId>
	<version>1.2.6.RELEASE</version>
</dependency>
```
 - 再点`Build Project` 就是锤子图标

