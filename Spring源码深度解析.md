<!-- TOC -->

- [第1章 Spring整体架构和环境搭建](#第1章-spring整体架构和环境搭建)
    - [1.1 Spring的整体架构](#11-spring的整体架构)

<!-- /TOC -->
第一部分 核心实现
## 第1章 Spring整体架构和环境搭建
### 1.1 Spring的整体架构
1.2 环境搭建
1.2.1 安装GitHub
1.2.2 安装Gradle
1.2.3 下载Spring

第2章 容器的基本实现
2.1 容器基本用法
2.2 功能分析
2.3 工程搭建
2.4 Spring的结构组成
2.4.1 beans包的层级结构
2.4.2 核心类介绍
2.5 容器的基础XmlBeanFactory
2.5.1 配置文件封装
2.5.2 加载Bean
2.6 获取XML的验证模式
2.6.1 DTD与XSD区别
2.6.2 验证模式的读取
2.7 获取Document
2.7.1 EntityResolver用法
2.8 解析及注册BeanDefinitions
2.8.1 profile属性的使用
2.8.2 解析并注册BeanDefinition

第3章 默认标签的解析
3.1 bean标签的解析及注册
3.1.1 解析BeanDefinition
3.1.2 AbstractBeanDefinition属性
3.1.3 解析默认标签中的自定义标签元素
3.1.4 注册解析的BeanDefinition
3.1.5 通知监听器解析及注册完成
3.2 alias标签的解析
3.3 import标签的解析
3.4 嵌入式beans标签的解析

第4章 自定义标签的解析
4.1 自定义标签使用
4.2 自定义标签解析
4.2.1 获取标签的命名空间
4.2.2 提取自定义标签处理器
4.2.3 标签解析

第5章 bean的加载
5.1 FactoryBean的使用
5.2 缓存中获取单例bean
5.3 从bean的实例中获取对象
5.4 获取单例
5.5 准备创建bean
5.5.1 处理ovverride属性
5.5.2 实例化的前置处理
5.6 循环依赖
5.6.1 什么是循环依赖
5.6.2 Spring如何解决循环依赖
5.7 创建bean
5.7.1 创建bean的实例
5.7.2 记录创建bean的ObjectFactory
5.7.3 属性注入
5.7.4 初始化bean
5.7.5 注册DisposableBean

第6章 容器的功能扩展
6.1 设置配置路径
6.2 扩展功能
6.3 环境准备
6.4 加载BeanFactory
6.4.1 定制BeanFactory
6.4.2 加载BeanDefinition
6.5 功能扩展
6.5.1 增加SPEL语言的支持
6.5.2 增加属性注册编辑器
6.5.3 添加ApplicationContext AwareProcessor处理器
6.5.4 设置忽略依赖
6.5.5 注册依赖
6.6 BeanFactory的后处理
6.6.1 激活注册的BeanFactory PostProcessor
6.6.2 注册BeanPostProcessor
6.6.3 初始化消息资源
6.6.4 初始化ApplicationEvent Multicaster
6.6.5 注册监听器
6.7 初始化非延迟加载单例
6.8 finishRefresh

第7章 AOP
7.1 动态AOP使用示例
7.2 动态AOP自定义标签
7.2.1 注册AnnotationAwareAspectJ AutoProxyCreator
7.3 创建AOP代理
7.3.1 获取增强器
7.3.2 寻找匹配的增强器
7.3.3 创建代理
7.4 静态AOP使用示例
7.5 创建AOP静态代理
7.5.1 Instrumentation使用
7.5.2 自定义标签
7.5.3 织入

第二部分 企业应用
第8章 数据库连接JDBC
8.1 Spring连接数据库程序实现（JDBC）
8.2 save/update功能的实现
8.2.1 基础方法execute
8.2.2 Update中的回调函数
8.3 query功能的实现
8.4 queryForObject

第9章 整合MyBatis
9.1 MyBatis独立使用
9.2 Spring整合MyBatis
9.3 源码分析
9.3.1 sqlSessionFactory创建
9.3.2 MapperFactoryBean的创建
9.3.3 MapperScannerConfigurer

第10章 事务
10.1 JDBC方式下的事务使用 示例
10.2 事务自定义标签
10.2.1 注册InfrastructureAdvisor AutoProxyCreator
10.2.2 获取对应class/method的增强器
10.3 事务增强器
10.3.1 创建事务
10.3.2 回滚处理
10.3.3 事务提交

第11章 SpringMVC
11.1 SpringMVC快速体验
11.2 ContextLoaderListener
11.2.1 ServletContextListener的使用
11.2.2 Spring中的ContextLoader Listener
11.3 DispatcherServlet
11.3.1 servlet的使用
11.3.2 DispatcherServlet的初始化
11.3.3 WebApplicationContext的初始化
11.4 DispatcherServlet的逻辑处理
11.4.1 MultipartContent类型的request处理
11.4.2 根据request信息寻找对应的Handler
11.4.3 没找到对应的Handler的错误处理
11.4.4 根据当前Handler寻找对应的HandlerAdapter
11.4.5 缓存处理
11.4.6 HandlerInterceptor的处理
11.4.7 逻辑处理
11.4.8 异常视图的处理
11.4.9 根据视图跳转页面

第12章 远程服务
12.1 RMI
12.1.1 使用示例
12.1.2 服务端实现
12.1.3 客户端实现
12.2 HttpInvoker
12.2.1 使用示例
12.2.2 服务端实现
12.2.3 客户端实现

第13章 Spring消息
13.1 JMS的独立使用
13.2 Spring整合ActiveMQ
13.3 源码分析
13.3.1 JmsTemplate
13.3.2 监听器容器