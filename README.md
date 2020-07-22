# daka_01
0.变量、运算符、数据类型及位运算

1.学习中遇到的难点主要是位运算，接触到python的一些特点。

    比如它的数据类型定义的时候不需要像C一样先声明类型，直接赋值即可。

    python有很多用途广泛的包 (package)，比如decimal中的getcontext().prec 来调整精度。
    如：
        import decimal
        from decimal import Decimal
        decimal.getcontext().prec = 4
        c = Decimal(1) / Decimal(3)
        注：Decimal(1/3)=0.333333333333333314829616256247390992939472198486328125
        返回的是Decimal(1/3)的准确表示，一般为53位及以上

        bool 可以作用在基本类型变量和容器类型变量

    
2.一些注意要点和不太明白却又影响不大的问题

    （1）. type() 不会认为子类是一种父类类型，不考虑继承关系。
    （2）. isinstance() 会认为子类是一种父类类型，考虑继承关系。
     (3) 数据流（data stream）是一组有序，有起点和终点的字节的数据序列。包括输入流和输出流
     (4) 流文件:是指的C语言中对文件的处理方式,在C语言中对文件的记录是以字符（字节）为单位的。
     输入输出的数据流的开始和结束仅受程序控制而不受物理符号（如回车换行符）控制。也就是说,
     在输出时不以回车换行符作为记录的间隔.

3.练习题1，

    1). 怎样对python中的代码进行注释？
    单行注释 # 多行注释 '''或 """

    2). python有哪些运算符，这些运算符的优先级是怎样的？
    算术：
        加 + 
        减 -
        乘 *
        除 /
        整除 //
        取余 %
    比较：
        大于 > 
        大于等于 >= 
        小于 < 
        小于等于 <=
        等于 == 
        不等于!=  
    逻辑：
        与 and
        或 or
        非 not
    位：
        按位取反 ~
        按位与 & 
        按位或 | 
        按位异或 ^ 
        左移 << 
        右移 >> 
    三元运算符： small = x if x < y else y
    其他：is 是 
        not is 不是 
        in 存在 
        not in 不存在

    运算优先级： 一元运算符优于二元运算符。先算术运算，后移位运算，最后位运算。 逻辑运算最后结合



    3）python 中 is , is not 与 == , != 的区别是什么？
        1. is, is not 对比的是两个变量的内存地址
        2. ==, != 对比的是两个变量的值
        假如比较的两个变量，指向的都是地址不可变的类型（str等），那么is，is not 和 ==，！= 是完全等价的。
        假如对比的两个变量，指向的是地址可变的类型（list，dict，tuple等），则两者是有区别的

    4)python 中包含哪些数据类型？这些数据类型之间如何转换？
        整型 int
        浮点型 float
        布尔型 bool
         转换为整型 int(x, base=10)
         转换为字符串 str(object='')
         转换为浮点型 float(x)

4.练习题2.
    leetcode 习题 136.
    只出现一次的数字给定一个非空整数数组，除了某个元素只出现一次以外，其余每个元素均出现两次。找出那个只出现了一次的元
    素。尝试使用位运算解决此题。
    
    #用位异或算法，相同的数字异或之后为0，还满足交换律，且0^num=num,所以把所有元素异或之后就剩余那个只出现一次的数字。
    
nums=[4,1,2,1,2]
result = 0
for i in range(len(nums)):
    result ^= nums[i]
print(result) 
