<!-- TOC -->

- [NIO模型](#nio%E6%A8%A1%E5%9E%8B)
- [AIO模型及类图](#aio%E6%A8%A1%E5%9E%8B%E5%8F%8A%E7%B1%BB%E5%9B%BE)
- [使用](#%E4%BD%BF%E7%94%A8)
- [实现原理：](#%E5%AE%9E%E7%8E%B0%E5%8E%9F%E7%90%86)
- [ScheduledThreadPoolExecutor原理](#scheduledthreadpoolexecutor%E5%8E%9F%E7%90%86)

<!-- /TOC -->
## NIO模型
![png](https://github.com/hycPerson/Interview/blob/master/pics/nio.png)
## AIO模型及类图
![png](https://github.com/hycPerson/Interview/blob/master/pics/AIO%E6%A8%A1%E5%9E%8B.png)
![png](https://github.com/hycPerson/Interview/blob/master/pics/AIOMap.png)
## 使用
服务端：一个open()静态工厂，一个bind()方法用于绑定服务端IP地址（还有端口号），另外还提供了accept()用于接收用户连接请求

客户端：还提供了read和write方法

CompletionHandler<V,A>，这个接口定义了如下两个方法，分别在异步操作成功和失败时被回调。
- void completed(V result, A attachment);
- void failed(Throwable exc, A attachment);

## 实现原理：
使用了ScheduledThreadPoolExecutor线程池，完成一个个任务

任务是实现了Future接口的PendingFuture

windows下使用的是Iocp
## ScheduledThreadPoolExecutor原理
![png](https://github.com/hycPerson/Interview/blob/master/pics/ScheduledThreadPoolExecutorMap.png)
DelayQueue封装了一个PriorityQueue。这个PriorityQueue会对队列中的Scheduled-


FutureTask进行排序。排序时，time小的排在前面（时间早的任务将被先执行）。

ScheduledThreadPoolExecutor的任务传递示意图
![png](https://github.com/hycPerson/Interview/blob/master/pics/ScheduledThreadPoolExecutor%E8%8E%B7%E5%8F%96%E4%BB%BB%E5%8A%A1%E7%9A%84%E8%BF%87%E7%A8%8B.png)
Condition控制线程等待还是唤醒

获取任务分为3大步骤。
- 1）获取Lock。
- 2）获取周期任务。
- ·如果PriorityQueue为空，当前线程到Condition中等待；否则执行下面的2.2。
- ·如果PriorityQueue的头元素的time时间比当前时间大，到Condition中等待到time时间；否则执行下面的2.3。
- ·获取PriorityQueue的头元素（2.3.1）；如果PriorityQueue不为空，则唤醒在Condition中等待的所有线程（2.3.2）。
- 3）释放Lock。
