*********本工程演示通过maven的web模板生成javaweb项目！*********
1、通过maven的web模板生成一个工程
   切换到要存放工程的目录，如E:\tmp>，使用命令【E:\tmp>mvn archetype:generate -DgroupId=com.thg -DartifactId=maven4web -DarchetypeArtifactId=maven-archetype-webapp -DinteractiveMode=false】
生成项目 ，标准的web目录结构会自动创建，结构如下
|____maven4web
||____pom.xml
||____src
|||____main
||||____resources
||||____webapp
|||||____index.jsp
|||||____WEB-INF
||||||____web.xml

2、生成eclipse支持
  切换到生成的工程目录下，使用命令【E:\tmp\maven4web>mvn eclipse:eclipse -Dwtpversion=2.0】，带wtp参数是为了将项目转换成web项目（war），默认是java项目（jar）

3、在eclipse中导入工程
  在 Eclipse IDE中，按步骤 File -> Import… -> General -> Existing Projects into workspace 操作导入工程

4、修改POM添加项目依赖和插件
  在pom.xml中添加了依赖（Spring, logback 和 JUnit）和插件（tomcat，jdk）后，需要再次执行命令【E:\tmp\maven4web>mvn eclipse:eclipse】生成eclipse支持（不需要待wtp参数是因为在pom中做了声明）
  
5、修改工程代码
  根据实际情况创建相关目录、添加配置文件、修改代码：
  5.1：创建 Spring MVC 的控制器类BaseController.java；
  5.2：创建Spring配置文件mvc-dispatcher-servlet.xml;
  5.3:修改web.xml 支持 Servlet 2.5，并添加Spring 监听器 ContextLoaderListener 集成了Spring框架；
  5.4：移动文件 index.jsp 到 WEB-INF/pages 目录下， 为了保护直接访问
  5.5：在资源文件夹(resources)中创建 logback.xml 文件
|____pom.xml
|____src
| |____main
| | |____java
| | | |____com
| | | | |____yiibai
| | | | | |____controller
| | | | | | |____BaseController.java
| | |____resources
| | | |____logback.xml
| | |____webapp
| | | |____WEB-INF
| | | | |____mvc-dispatcher-servlet.xml
| | | | |____pages
| | | | | |____index.jsp
| | | | |____web.xml
  
  
6、通过eclipse的项目插件（tomcat）部署发布工程
  通过命令【E:\tmp\maven4web>mvn eclipse:eclipse】生成eclipse支持，再通过命令【E:\tmp\maven4web>mvn tomcat7:run】启动并发布服务（注意是tomcat7，否则会报错）。
  