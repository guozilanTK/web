# Web 部署此项目

在 guozilan 整个项目结构中，真正打包部署的是这个项目，这个项目基本上只有简单的一些配置和静态资源。

## 配置

在 src/main/resources 目录中，存在了 spring 和 springmvc 的基本配置。

- application.properties: 基本配置信息
- applicationContext.xml: spring配置和数据库MyBatis事务等配置
- logback.xml: 日志配置
- mapper-servlet.xml: spring mvc 配置

上述这些配置可以根据自己的需要去修改。

>**特别注意**
> applicationContext.xml 扫描的包名是 tk.guozilan 开头的，注意改成自己的包名。
> mapper-servlet.xml 扫描的包名是 tk.guozilan 开头的，注意改成自己的包名。


## 静态资源

本项目中只是用 layui 做了一个简单的示范，其他 ui 都可以使用。

## 如何使用

在开发工具中，将此项目部署到 Tomcat 或其他 Web 容器中。

当需要使用其他模块提供的功能时，可以引入其他模块的依赖。

例如引入 [sample](https://github.com/guozilanTK/sample) 项目。

```xml
<dependency>
  <groupId>tk.guozilan</groupId>
  <artifactId>sample-controller</artifactId>
  <version>1.0.0-SNAPSHOT</version>
</dependency>
<dependency>
  <groupId>tk.guozilan</groupId>
  <artifactId>sample-service</artifactId>
  <version>1.0.0-SNAPSHOT</version>
</dependency>
<dependency>
  <groupId>tk.guozilan</groupId>
  <artifactId>sample-web</artifactId>
  <version>1.0.0-SNAPSHOT</version>
  <type>war</type>
</dependency>
```

项目启动后，就可以访问 [sample](https://github.com/guozilanTK/sample) 中 controller 提供的服务。