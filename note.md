小心Comparator陷阱
https://blog.csdn.net/yinbodotcc/article/details/1485543


//存在相减溢出的漏洞

return (i2 < i1 ? -1 : (i2 == i1 ? 0 :1));