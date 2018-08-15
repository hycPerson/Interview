## ThreadLocal 实现线程安全

```java
    /** 
     * 为了确保一个线程中只有一个Connection,我们可以使用ThreadLocal来存放本地线程变量
     * 隔离线程的容器
     */
    private static final ThreadLocal<Connection> CONNECTION_HOLDER = new ThreadLocal<Connection>();
        public static Connection getConnection(){
        Connection connection=CONNECTION_HOLDER.get();
        if(connection == null){
            try {
                connection = DriverManager.getConnection(URL,USERNAME,PASSWORD);
            } catch (SQLException e) {
                e.printStackTrace();
            }finally {
                CONNECTION_HOLDER.set(connection);
            }
        }
        return connection;
    }
```
