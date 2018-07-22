---
layout: post
title:  "007-反转整数"
categories: jekyll update
---

_______________________________________________________________________________
# `题目：`
给定一个 32 位有符号整数，将整数中的数字进行反转。

# 方案一：

    class Solution(object):
      def reverse(self, x):
        """
        :type x: int
        :rtype: int
        """
        result = 0                       # 给结果变量赋初值0
        negative = False                 # 默认给出数大于0
        if x < 0:                        # 如果数<0,标记正负，并转换成正书
            x *= -1
            negative = True
        while(x!=0):                     # 如果数不等于0
            result = result * 10 + x%10  # result*10所有位数晋级，再加上x余数完成当前位的倒转
            x /= 10                      # 道转位从低向高推进
        if  -2147483648 > result or result > 2147483648: #判断是否超出32位边界
            result = 0
        return result*-1 if negative else result #正数则返回值，负数则返回*-1值
        

