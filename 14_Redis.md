bind 127.0.0.1
protected-mode yes
port 6379
dbfilename dump.rdb
password root


redis下，数据库是由一个整数索引标识，而不是由一个数据库名称。默认情况下，一个客户端连接到数据库0。redis配置文件中下面的参数来控制数据库总数：
databases 16
redis> select 2


redis里直接set()第一反应应该是String类型


expire过期操作
自增自减是对string的自增自减

基本操作
https://www.2cto.com/database/201708/664677.html


setex =set +expire
Setnx =set +not exist


set 是string
hset 是hashmap
l开头是list lrange

s开头的是set，如果是纯set就是String
z开头的是有序set


l
h开头的是map
s
z
四大开头
加上本身set指的是
一共五种

l
h
s
z

有序set的set是来自哪里
zadd(final String key, final double score, final String member)