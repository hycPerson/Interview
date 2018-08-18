## 1、Tomcat读取web.xml 完成第一步加载
部署web应用时，web容器（比如Tomcat）会读取配置在web.xml中的监听器，从而启动spring容器。

    1、加载监听器类
    2、读取applicationContext.xml
    3、读取spring-mvc.xml
    4、形成ServletContext
```xml
    <listener-class>org.springframework.web.context.ContextLoaderListener</listener-class>
    <listener>
     <context-param>
        <param-name>contextConfigLocation</param-name>
        <param-value>classpath:applicationContext.xml</param-value>
    </context-param>
    <param-name>contextConfigLocation</param-name>
            <param-value>classpath:spring-mvc.xml</param-value>
```
##  2、启动触发事件
在web容器启动时，会触发容器初始化事件，此时contextLoaderListener会监听到这个事件，其contextInitialized方法会被调用

完成一个ConfigurableWebApplicationContext

![avatar](https://github.com/hycPerson/Interview/blob/master/pics/ContextLoaderListener.png)


## 3、初始化
GenericServlet.init() 

HttpServletBean.init() 

----HttpServletBean.initBeanWrapper(BeanWrapper) 
----HttpServletBean.initServletBean() 
--------FrameworkServlet.initServletBean()  
------------FrameworkServlet.initWebApplicationContext()  
------------FrameworkServlet.initFrameworkServlet() 
## 4、初始化web.xml中配置的Servlet，调用initStrategies方法
MultipartResolver 用于处理文件上传

LocaleResolver解析用户区域

ThemeResolver一个主题就是一组静态资源（比如样式表、图片等），它们可以影响应用程序的视觉效果 

HandlerMappings（从request找到Handler）

HandlerAdapters(选择某一个适当的处理器适配器的实现)

HandlerExceptionResolvers

RequestToViewNameTranslator

ViewResolvers

FlashMapManager


AbstractHandlerMapping 准备上下文环境;提供getHandlerInternal钩子;封装拦截器到HandlerExecutionChain

pringMVC--4种映射处理器handlerMapping
