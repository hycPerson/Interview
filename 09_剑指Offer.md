<!-- TOC -->

- [面试题31：栈的压入、弹出序列](#面试题31栈的压入弹出序列)
- [判断phenomena二叉树](#判断phenomena二叉树)
- [数组中只出现一次的数字](#数组中只出现一次的数字)
- [和为S的连续正数序列（不在书里）](#和为s的连续正数序列不在书里)
- [面试题57：和为S的两个数字](#面试题57和为s的两个数字)

<!-- /TOC -->
### 面试题31：栈的压入、弹出序列
规律：如果下一个弹出的数字刚好是栈顶，那么直接弹出；  
如果下一个数字不在栈顶，则把压栈序列中还没有入栈的数字压入辅助栈，直到把下一个需要弹出的数字压入栈顶为止；  
如果所有数字都压入栈后，仍然没有找到下一个弹出的数字，那么该序列不可能是一个弹出序列。  
### 判断phenomena二叉树
左右两个子树的高度差的绝对值不超过1，并且左右两个子树都是一棵平衡二叉树。
```java
public class Solution {
    public boolean IsBalanced_Solution(TreeNode root) {
        condition=true;
        recursion(root);
        return condition;
    }
    public static boolean condition=true;
    //返回的是最大子树最大深度
    public static int recursion(TreeNode root){
        if(root==null)
            return 0;
        int left=recursion(root.left);
        int right=recursion(root.right);
        if(Math.abs(left-right)>1)
            condition=false;
        return left>right?left+1:right+1;
    }
}
```
### 数组中只出现一次的数字

```java
//num1,num2分别为长度为1的数组。传出参数
//将num1[0],num2[0]设置为返回结果
import java.util.Set;
import java.util.Iterator;
import java.util.HashSet;
public class Solution {
    public void FindNumsAppearOnce(int [] array,int num1[] , int num2[]) {
        Set<Integer> set = new HashSet<>();
        for(int i=0;i<array.length;i++){
            if(!set.contains(array[i])){
                set.add(array[i]);
            }else{
                set.remove(array[i]);
            }
        }
        Iterator<Integer> in = set.iterator();
        while(in.hasNext()){
            num1[0]=in.next();
            num2[0]=in.next();
        }
    }
}
```
### 和为S的连续正数序列（不在书里）
你的思路：  
暴力
优化：
有了解决前面问题的经验，这里也考虑两个数small和big分别表示序列的最小值和最大值。
首先把small初始化为1，big初始化为2.如果从small到big的序列的和大于S，可以从序列中去掉较小的值，也就是增大small的值。
如果从small到big的序列的和小于S，可以增大big，让这个序列包含更多的数字。因为这个序列至少要有两个数字，我们一直增加small到（1+S）/2为止。
```java
import java.util.ArrayList;
public class Solution {
    public ArrayList<ArrayList<Integer> > FindContinuousSequence(int sum) {
        int count;
        ArrayList<ArrayList<Integer> > result = new ArrayList<>();
        
       for(int start=1;start<sum;start++){
           ArrayList<Integer> arrayList = new ArrayList<>();
           count=start;
           arrayList.add(start);
           int i=1;
           while(count<sum){
               arrayList.add(start+i);
               count=count+start+i;
               i++;
           }
           if(count==sum){
               result.add(arrayList);
           }
       }
        return result;
    }
}
```
### 面试题57：和为S的两个数字

1、左右指针（时间复杂度N）  
    不够的话往左滑，够的话往右滑  
2、Set法(N*Set的时间复杂度)  
3、Map法  
```java
import java.util.ArrayList;
import java.util.HashSet;
import java.util.Set;
public class Solution {
    public ArrayList<Integer> FindNumbersWithSum(int [] array,int sum) {
       Set<Integer> set = new HashSet<>();
       for(int i=0;i<array.length;i++){
           set.add(array[i]);
       }
       int n1,n2;
       int result1=-1,result2=-1,resSum=1000000000;
       for(int i=0;i<array.length;i++){
           n1=array[i];
           if(set.contains(sum-n1)&& resSum>(sum-n1)*n1){
               resSum=(sum-n1)*n1;
               result1=n1;
               result2= sum-n1;
           }
       }
       ArrayList<Integer> arrayList = new ArrayList<>();
       if(result1==-1)
           return arrayList;
       if(result1<result2){
           arrayList.add(result1);
           arrayList.add(result2);
       }else{
           arrayList.add(result2);
           arrayList.add(result1);
       }
       return arrayList;
    }
}
```