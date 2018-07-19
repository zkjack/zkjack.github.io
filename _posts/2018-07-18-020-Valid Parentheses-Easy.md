---
layout: post
title:  "020-Valid Parentheses"
categories: jekyll update
---

_______________________________________________________________________________

# 题目 有效的括号字符
### `中文阐述`
给定一个只包括 `'('`，`')'`，`'{'`，`'}'`，`'['`，`']'` 的字符串，判断字符串是否有效。

有效字符串需满足：

1. 左括号必须用相同类型的右括号闭合。
2. 左括号必须以正确的顺序闭合。

_注意_:空字符串可被认为是有效字符串。

### `English Expression`
Given a string containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.

An input string is valid if:

1. Open brackets must be closed by the same type of brackets.
2. Open brackets must be closed in the correct order.

_Note that_ an empty string is also considered valid.

# 方案一：

    class Solution(object):
      def isValid(self, s):
        """
        :type s: str
        :rtype: bool
        """
        parentheses_dict = {')':'(','}':'{',']':'['}       #设置符号配对字典
        parentheses_stack = [None]                         #符号栈,设置None是为了排除空值的情况！
        for parenthes in s:                                #遍历字符串S中的每一个字符
          if parenthes in parentheses_dict and parentheses_dict[parenthes] == parentheses_stack[-1]: #如果是反括号就跟栈顶素匹配
            parentheses_stack.pop()                        #匹配成功就出栈
          else:
            parentheses_stack.append(parenthes)            #如果是正括号就入栈
            
        return len(parentheses_stack) == 1                 #栈只剩下None则说明是有效字符串。
        
# 方案二：
  
    class Solution(object):
      def isValid(self, s):
        """
        :type s: str
        :rtype: bool
        """
        parentheses_dict = {')':'(','}':'{',']':'['}       # 设置符号配对字典
        parentheses_stack = [None]                         # 符号栈,设置None是为了排除空值的情况！
        for parenthes in s:                                # 遍历字符串S中的每一个字符
          if parenthes in parentheses_dict：               # 如果字符是反括号
            if parentheses_dict[parenthes] != parentheses_stack.pop(): #如果栈顶元素不是该反括号对应的正括号，就返回不是有效字符串。
              return False
          else:
            parentheses_stack.append(parenthes)            #如果是正括号就入栈
            
        return len(parentheses_stack) == 1                 #栈只剩下None则说明是有效字符串。