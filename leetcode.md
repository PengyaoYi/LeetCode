# 17

##[电话号码的字母组合](https://leetcode-cn.com/problems/letter-combinations-of-a-phone-number/)

### 回溯 

```
if not digits: return []

phone = {'2': ['a', 'b', 'c'],
         '3': ['d', 'e', 'f'],
         '4': ['g', 'h', 'i'],
         '5': ['j', 'k', 'l'],
         '6': ['m', 'n', 'o'],
         '7': ['p', 'q', 'r', 's'],
         '8': ['t', 'u', 'v'],
         '9': ['w', 'x', 'y', 'z']}

def backtrack(conbination, nextdigit):
    if len(nextdigit) == 0:
        res.append(conbination)
    else:
        for letter in phone[nextdigit[0]]:
            backtrack(conbination + letter, nextdigit[1:])

res = []
backtrack('', digits)
return res
```



# 98

[验证搜索二叉树](https://leetcode-cn.com/problems/validate-binary-search-tree/)

### 递归

```
def help(root,low,upper):
            if not root:
                return True
            cur=root
            if cur.val>=upper or cur.val<=low:
                return False
            return help(cur.left,low,cur.val) and  help(cur.right,cur.val,upper)
        return help(root,-float('inf'),float('inf'))
```



# 99

[恢复二叉搜索树](https://leetcode-cn.com/problems/recover-binary-search-tree/)

要求空间复杂度为O(1)

### 递归 Morris Traversal算法

空间复杂度为O(n)的做法：中序遍历二叉树，找到非递增的节点，交换一下。

