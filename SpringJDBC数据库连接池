<!-- TOC -->

- [概念](#概念)
- [dbcp 连接池创建](#dbcp-连接池创建)
- [连接池原理](#连接池原理)
- [PoolingDataSource.getConnnection()](#poolingdatasourcegetconnnection)

<!-- /TOC -->
## 概念
数据库连接池负责分配,管理和释放数据库连接,它允许应用程序重复使用一个现有的数据库连接,而不是重新建立一个

Spring里主要是dbcp

## dbcp 连接池创建
[png](https://github.com/hycPerson/Interview/blob/master/pics/ContextLoaderListener.png)
里主要用的是BasicDataSource

因为从applicationContext.xml可以看出

<bean id="dataSource" class="org.apache.commons.dbcp.BasicDataSource"
          destroy-method="close">
          再依据后面的xml配置连接池maxActive、maxIdle

创建连接池createConnectionPool() 

依次调用 

- GenericObjectPool()  
- setMaxActive(int) //最大连接数据库连接数
- setMaxIdle(int)  //最大等待连接中的数量
- setMinIdle(int)  //
- setMaxWait(long) //最大等待秒数
- setTestOnBorrow(boolean)  
- setTestOnReturn(boolean)  
- setTimeBetweenEvictionRunsMillis(long)  
- setNumTestsPerEvictionRun(int)  
- setMinEvictableIdleTimeMillis(long)  
- setTestWhileIdle(boolean)  
- 可以看出GenericKeyedObjectPool是真正的连接池
- 返回的是PoolingDataSource类的实例，去getConnnection()

## 连接池原理
使用了KeyedObjectPool

根据一些参数比如key值去查找某些指定的池中对象，比如可以根据一个参数来决定使用池中具体的那一个数据库连接，等等。此时就需要使用

KeyedPoolableObjectFactory和KeyedObjectPool接口。

一个Connection类，可以想象成一个远程连接比如数据库连接等。

## PoolingDataSource.getConnnection()
最终调用GenericKeyedObjectPoolborrowObject的borrowObject方法

在borrowObject方法里重写了需要实现的逻辑

又写了一个类Latch来计数



