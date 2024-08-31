# servlet-practice
Shared libraries（共享库） / runtimes pluggability（运行时插件能力）:

Servlet3.0官方支持第三方插件植入，也就是可以抛弃web.xml再结合spring的注解即可实现接口的插拔，而要做的就是就是实现这个ServletContainerInitializer接口即可

1. Servlet容器启动会扫描，当前应用里面每一个jar包的ServletContainerInitializer的实现
2. 提供ServletContainerInitializer的实现类；可以通过注解@HandlesTypes传入感兴趣的业务类；
3. 必须绑定META-INF/services/javax.servlet_initializer.ServletContainerInitializer文件,文件的内容就是ServletContainerInitializer实现类的全类名；


关键接口：ServletContainerInitializer；

关键注解：@HandlesTypes；


2024.1.9日更新：
1. 在新版本tomcat环境下，ServletContainerInitializer的spi文件路径发生变化，新版路径为META-INF/services/jakarta.servlet_initializer.ServletContainerInitializer
2. META-INF要放在idea的resources目录中






