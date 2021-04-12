# Dynamic Programming^[1]^

动态规划不是某一种具体的算法，而是一种算法思想：若要解一个给定问题，我们需要解其不同部分（即子问题），再根据子问题的解以得出原问题的解。

## 最优子结构

最优子结构规定的是子问题与原问题的关系。动态规划要解决的都是一些问题的最优解，即从很多解决问题的方案中找到最优的一个。当我们在求一个问题最优解的时候，如果可以把这个问题分解成多个子 题，然后递归地找到每个子问题的最优解，最后通过一定的数学方法对各个子问题的最优解进行组合得出最终的结果。**总结来说就是一个问题的最优解是由它的各个子问题的最优解决定的**。

将子问题的解进行组合可以得到原问题的解是动态规划可行性的关键。在解题中一般用*状态转移方程*描述这种组合。

## 重复子问题

重复子问题规定的是子问题与子问题的关系。当我们在递归地寻找每个子问题的最优解的时候，有可能会会重复地遇到一些更小的子问题，而且这些子问题会重叠地出现在子问题里，出现这样的情况，会有很多重复的计算，动态规划可以保证每个重叠的子问题只会被求解一次。*当重复的问题很多的时候，动态规划可以减少很多重复的计算*。

重复子问题不是保证解的正确性必须的，但是如果递归求解子问题时，没有出现重复子问题，则没有必要用动态规划，直接普通的递归就可以了。

解决动态规划问题的核心：**找出子问题及其子问题与原问题的关系**。找到了子问题以及子问题与原问题的关系，就可以递归地求解子问题了。但重叠的子问题使得直接递归会有很多重复计算，**于是就想到记忆化递归法：若能事先确定子问题的范围就可以建表存储子问题的答案**。

动态规划算法中关于最优子结构和重复子问题的理解的关键点：

1. 证明问题的方案中包含一种选择，选择之后留下一个或多个子问题；
2. 设计子问题的递归描述方式；
3. 证明对原问题的最优解包括了对所有子问题的最优解；
4. 证明子问题是重叠的（这一步不是动态规划正确性必需的，但是如果子问题无重叠，则效率与一般递归是相同的）

## 典型例题

### 1. 一维线性

1）最大子序和，题目链接：[53.Maximum Subarray, Easy](https://leetcode-cn.com/problems/maximum-subarray/)

```c++
/*
Given an integer array nums, find the contiguous subarray (containing at least one number) which has the largest sum and return its sum.
*/

class Solution {
public:
    int maxSubArray(vector<int>& nums) {
        int pre = 0, maxAns = nums[0];
        for (const auto &x: nums) {
            pre = max(pre + x, x);
            maxAns = max(maxAns, pre);
        }
        return maxAns;
    }
};
```

 2）爬楼梯，题目链接：[70.Climbing Stairs, Easy](https://leetcode-cn.com/problems/climbing-stairs/)

```c++
/*
You are climbing a staircase. It takes n steps to reach the top.

Each time you can either climb 1 or 2 steps. In how many distinct ways can you climb to the top?
*/
class Solution {
public:
    int climbStairs(int n) {
        int p = 0, q = 0, r = 1;
        for (int i = 1; i <= n; ++i) {
            p = q; 
            q = r; 
            r = p + q;
        }
        return r;
    }
};
```



## Reference

[1]: https://leetcode-cn.com/leetbook/read/dynamic-programming-1-plus/xceyqr/	"LeetCode"

