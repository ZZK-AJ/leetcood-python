### 题目

The **Fibonacci numbers**, commonly denoted `F(n)` form a sequence, called the **Fibonacci sequence**, such that each number is the sum of the two preceding ones, starting from `0` and `1`. That is,

```
F(0) = 0,   F(1) = 1
F(N) = F(N - 1) + F(N - 2), for N > 1.
```

Given `N`, calculate `F(N)`.

 

**Example 1:**

```
Input: 2
Output: 1
Explanation: F(2) = F(1) + F(0) = 1 + 0 = 1.
```

**Example 2:**

```
Input: 3
Output: 2
Explanation: F(3) = F(2) + F(1) = 1 + 1 = 2.
```

**Example 3:**

```
Input: 4
Output: 3
Explanation: F(4) = F(3) + F(2) = 2 + 1 = 3.
```

 

**Note:**

0 ≤ `N` ≤ 30.



### 思路

题目要求的是计算出F(N)的具体数值，由递推公式可以直接利用递归调用的方法，不断递归调用，最后就会回到N=1和N=0阶段，然后在反过来不断算出之前递归调用的数值。最后得到答案。

使用迭代的方法的话，



### Python解法

递归调用的方法：

```python
class Solution:
    def fib(self, N: int) -> int:
        if N==0:
            return 0
        if N==1:
            return 1
        return self.fib(N-1) + self.fib(N-2)
```



迭代的方法：

```python
class Solution:
	def fib(self, N: int) -> int:
		a,b = 0,1
		for i in range(N):
			a,b = b, a+b
		return a
```



### Java解法

```java
class Solution {
     public int fib(int N) {
        if (N < 2) {
            return N;
        }
        int result=1,exResult=0,temp;
        for(int i =2;i<=N;i++){
            temp = result;
            result+=exResult;
            exResult =temp;
        }
        return result;
    }
}
```



