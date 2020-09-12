# 整数拆分 有顺序

拆分整数 $N$ 为 $C = {a_i}, 1 <= a_i <= 6$，$C$ 有序，求方案数。

## 思路

假设 $f(n)$ 表示 方案数

思路：

把 $N$ 拆分为 $i$ 和 $(n - i)$
则 $i$ 的范围为 $[1, min(6, N)]$

所以 $f(n) = \Sigma_i^{min(6, N)} f(n - i)$

可以使用递归实现，但是递归版本会重复计算一些值。
为了避免重复计算，可以使用 `cache` 记录已经计算过的 $f(n)$。

代码如下：

```python
cache = {}
cache[0] = 1
cache[1] = 1


def f(n):
  if n in cache:
    return cache[n]
  ans = sum([f(n - i) for i in range(1, min(6, n) + 1)])
  cache[n] = ans
  return ans


n = int(input())
print(f(n))
```
