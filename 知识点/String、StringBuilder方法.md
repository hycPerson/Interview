String方法
1 length字符串的长度
2 charAt（）截取一个字符
3 getchars（）截取多个字符并由其他字符串接收
4 getBytes()将字符串变成一个byte数组
5 toCharArray()将字符串变成一个字符数组
6 equals()和equalsIgnoreCase()比较两个字符串是否相等，前者区分大小写，后者不区分
7 startsWith()和endsWith()判断字符串是不是以特定的字符开头或结束
8 toUpperCase()和toLowerCase()将字符串转换为大写或小写
9 concat() 连接两个字符串
10 trim()去掉起始和结束的空格
11 substring（）截取字符串
12 indexOf()和lastIndexOf()前者是查找字符或字符串第一次出现的地方，后者是查找字符或字符串最后一次出现的地方
13 compareTo()和compareToIgnoreCase(）按字典顺序比较两个字符串的大小，前者区分大小写，后者不区分

StringBuilder
 reverse()
 insert(int offset, int i)
 setCharAt(int i, char c)：将第 i 个代码单元设置为 c（可以理解为替换）
 delete(int startIndex,int endIndex)：删除起始位置（含）到结尾位置（不含）之间的字符串

 StringBuilder的Reverse
 ```java
     public AbstractStringBuilder reverse() {
        boolean hasSurrogates = false;
        int n = count - 1;
        for (int j = (n-1) >> 1; j >= 0; j--) {
            int k = n - j;
            char cj = value[j];
            char ck = value[k];
            value[j] = ck;
            value[k] = cj;
            if (Character.isSurrogate(cj) ||
                Character.isSurrogate(ck)) {
                hasSurrogates = true;
            }
        }
        if (hasSurrogates) {
            reverseAllValidSurrogatePairs();
        }
        return this;
    }
 ```

 byte数组转换成String类型
 str = new String(byte[] data, "utf-8");