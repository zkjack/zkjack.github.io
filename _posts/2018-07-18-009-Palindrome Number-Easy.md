---
layout: post
title:  "009-回文数-Palindrome Number"
categories: jekyll update
---

_______________________________________________________________________________
# `中文阐述：`
判断一个整数是否是回文数。回文数是指正序（从左向右）和倒序（从右向左）读都是一样的整数。

你能不将整数转为字符串来解决这个问题吗？

# `English Expression:`
Determine whether an integer is a palindrome. An integer is a palindrome when it reads the same backward as forward.

Coud you solve it without converting the integer to a string?

# 方案一：

    class Solution(object):
      def isPalindrome(self, x):
        """
        :type x: int
        :rtype: bool
        """
        reverse_x = 0            # 设置反转数字为0
        origin_x  = x            # 保留原始x的值
        if x < 0:                # 如果x小于0，则返回不是回文数
            return False
        while x > 0:             # 如果x大于0
            reverse_x = reverse_x*10 + x%10   # 把当前数*10各位晋级，加上x的当前位
            x /= 10              # x从低到高完成反转
        
        return reverse_x == origin_x   # 反转后的数和原结果一样则是回文数

# 方案二：
  
    # 把x变成字符串的方法
    class Solution(object):
      def isPalindrome(self, x):
        """
        :type x: int
        :rtype: bool
        """
        
        x = str(x)              # 把x变成字符串
        if x != x[::-1]:        # 调用python反转函数，与原字符串做对比
            return False        # 两个串相同则返回真，否则返回假
        return True           