#  342. Power of Four

## Description

```
Difficulty: Easy
Total Accepted:67.4K
Total Submissions:175.3K
Contributor: LeetCode
```

Given an integer (signed 32 bits), write a function to check whether it is a power of 4.

**Example:**
Given num = 16, return true. Given num = 5, return false.

***

## Solution
  关于这道题目，前面有做过判断一个数是否为2的幂的问题，当时做的时候是把数值用二进制的域来看待，这样就可以发现，2的幂在2进制下的规律是，最高位为1，其他位为0，这道题要求4的幂。首先，4的幂是2的幂的一个子集，我们可以在上道题的基础上，去思考这道题。复杂问题简单化思想，把该问题，转化为在求2的幂的解空间里求特定的一部分解空间。第一步，先求出2的幂。第二步，在求出的结果上，与上我们进一步的限制条件。关于这类题的限制条件，就是用二进制与的特殊性，也就是1去与任何数位可以筛选该数位的功能去给出我们的限制条件。

```java
public class Solution {
    public boolean isPowerOfFour(int num) {
        if(num <= 0)
            return false;
        return (((num&(num-1))==0)&&(num&0x55555555) != 0);
    }
}
```

***

**enjoy life, coding now! :D**