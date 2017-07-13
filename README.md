# My Awesome Book

This file file serves as your book's preface, a great place to describe your book's content and ideas.

* [ ] asd

12

> 有三根相邻的柱子，标号为A,B,C,A柱子上按从小到大叠放着N个不同大小的盘子，要求把所有盘子每次移动一个，最终全部放到C柱子上；移动过程中可以借助B柱子，但要求每次移动中必须保持每根柱子上小盘子在大盘子上面。请给出最少移动次数的方案有三根相邻的柱子，标号为A,B,C,A柱子上按从小到大叠放着N个不同大小的盘子，要求把所有盘子每次移动一个，最终全部放到C柱子上；移动过程中可以借助B柱子，但要求每次移动中必须保持每根柱子上小盘子在大盘子上面。请给出最少移动次数的方案

```py
# !/usr/bin/env python
# -- coding: utf-8 --
# @Time : 2017/7/12 9:52
# @Author : Albert·Sun
# @Version : 0.10α-β
# @Description : None

def Hanoi(N, fro, to, aux, string):
    if N == 1:
        print N, ':', fro, '->', to, '| State:', string, '->',
        string[N - 1] = to
        print string
        return

    Hanoi(N-1, fro, aux, to, string)

    print N, ':', fro, '->', to, '| State:', string, '->',
    string[N - 1] = to
    print string

    Hanoi(N-1, aux, to, fro, string)


def HanoiState(string, fro, to, aux):
    if len(string) <= 0:
        return 0

    if string[-1] == aux:
        return -1
    elif string[-1] == to:
        n = HanoiState(string[:-1], aux, to, fro)
        if n == -1:
            return -1
        else:
            return n + (1 << (len(string) - 1))  # n + 2^(size-1)
    else:
        return HanoiState(string[:-1], fro, aux, to)


if __name__ == "__main__":
    Hanoi(3, 'A', 'C', 'B',['A', 'A', 'A'])
    string = 'BACC'
    print string, 'State:', HanoiState(string, 'A', 'C', 'B')
```

```

```



