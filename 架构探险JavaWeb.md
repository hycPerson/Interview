## 框架 
annotation

bean

helper
- 管理类，IOC AOP核心代码
proxy

util

dispatcherServlet
@WebServlet注解配置Servlet
## IOC
最终维护两个MAP
一个是Request,Handler的Map的ControllerHelper

一个是类和对象的BEAN_MAP的BeanHelper

IocHelper读取@Inject注解内容，注入属性
![avatar](https://github.com/hycPerson/Interview/blob/master/pics/Ioc.png)

## 代理
在这里我们定义了切面代理和事务代理，实现了具体控制代理的。

AOP Helper在所有的bean中找到需要加切面的bean，并形成代理链

ProxyManager替换了bean容器中的bean。

![avatar](https://github.com/hycPerson/Interview/blob/master/pics/%E4%BB%A3%E7%90%86%E4%B8%8E%E4%BA%8B%E5%8A%A1.png)
## 事务
事务也是动态代理，用到了ThreadLocal保护现场，最终调用了数据库的回滚方法。并没有对有状态的做回滚，dao层hibernate会管理好一致性
