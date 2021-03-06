# 设置

## tomcat 

### 远程调试

```java
-Xdebug -Xrunjdwp:transport=dt_socket,suspend=n,server=y,address=9999
```
### [配置连接同时扶持http和https](https://stackoverflow.com/questions/7790141/is-security-constraint-configuration-for-tomcat-mandatory)
```xml
If you omit the <transport-guarantee>CONFIDENTIAL</transport-guarantee> tag 
(or the whole <security-constraint>) your application will be available through both HTTP and HTTPS. 
If your web.xml contains <transport-guarantee>CONFIDENTIAL</transport-guarantee> 
Tomcat automatically redirects the requests to the SSL port if you try to use HTTP
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

## Mybatis

### 大小写转义

- 方式1、转义字符
	```xml
	<select id="searchByPrice" parameterType="Map" resultType="Product">
	    <!-- 方式1、转义字符 -->
		select * from Product where price &gt;= #{minPrice} and price &lt;= #{maxPrice}
    </select>
	```
- 方式2、标记CDATA
  ```xml
  <select id="searchByPrice" parameterType="Map" resultType="Product">
    <!-- 方式2、CDATA -->
	<![CDATA[select * from Product where price >= #{minPrice} and price <= #{maxPrice} ]]>
  </select>
  ```
