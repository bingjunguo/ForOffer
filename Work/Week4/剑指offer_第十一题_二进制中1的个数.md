## 平台
牛客网

## 语言
python2.7.3

## 作业内容

### 题目描述
输入一个整数，输出该数二进制表示中 1 的个数。其中负数用补码表示。



### 题目理解



### 解题思路
正数:将正数转化为二进制，计算1的个数

负数:将负数转化为补码，补码为反码最低位加1得到，原码的0全部为反码的1

32 - 原码中1的个数 = 补码中1的个数

现代电脑的字长一般是 32 位的，也就是说，一个字的位数是 32。字节是 8 位的数据单元，
一个字节可以表示 0－255 的十进制数据。对于 32 位字长的现代电脑，
一个字等于 4 个字节，对于早期的 16 位的电脑，一个字等于 2 个字节。

整数转二进制：
1、采用%2的方式计算
2、采用python自带了方法 bin.
比如bin(10) 回返回字符串'0b1010' ，只留下‘0’，‘1’序列需要把‘0b’去掉.
    
    bin(number).replace('0b','') 或bin(number)[2:]
    >>> bin(10)  // 为了下边表示方便 放入t中
    '0b1010'
 
二进制转整数：
    
    >>> int(t[2:],2)
    10


### 程序
    
    class Solution:
        def NumberOf1( self,n):
            if n >= 0:
                count_1 = bin(n).count("1")
    
            else:
                n = abs(n)
                count1 = 32 - bin(n - 1).count("1")
            return count_1


### 补充知识点

[补码](https://jingyan.baidu.com/article/1e5468f90a9568484861b77c.html)
