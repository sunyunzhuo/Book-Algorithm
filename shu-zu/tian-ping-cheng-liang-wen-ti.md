# 分治与递归--实数的整数次幂

---

> 给定实数 x 和整数 n, 求 x的n次幂
>
> 时间复杂度：O\(logN\)

```py
# !/usr/bin/env python
# -- coding: utf-8 --
# @Time : 2017/7/12 10:50
# @Author : Albert·Sun
# @Version : 0.10α-β
# @Description : None

def power(x, n):
    if n == 0:
        return 1
    if n == 1:
        return x

    if n < 0:
        return 1.0/power(x, -n)

    if n % 2 == 0:
        p = power(x, n/2)
        return p*p
    else:
        p = power(x, (n-1)/2)
        return x*p*p

if __name__ == "__main__":
    print 'power(1.01, 365)', pow(1.01, 365), power(1.01, 365)
    print 'power(0.99, 365)', pow(0.99, 365), power(0.99, 365)

    print pow(0.99, -365), power(0.99, -365)
```

结果如下：

![](/assets/鸡汤.png)

