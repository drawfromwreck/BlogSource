---
title: 数组指针和指针数组的区别
date: 2020-10-10 14:56:45
tags:
- C++
categories: 算法
image: img/category/algorithm.jpeg
---

数组指针定义：
```c++
int (*p1)[4];
```

指针数组定义
```c++
int *p2[4];
```

- 数组指针：是指针，括号括起指针名和星号，即指向一个数组的指针
- 指针数组：是数组，指针名不带括号，即内容为指针的一个数组

示例：
```cpp
# include <iostream>
using namespace std;

int main()
{
    int a[3][4]={1,2,3,4,5,6,7,8,9,10,11,12};
    int (*p1)[4];
    p1 = (int(*)[4])a;  // 数组指针
    for(int i = 0; i < 3; i++)
    {
        for(int j = 0; j < 4; j++)
        {
            cout << p1[i][j] << '\n';
        }
    }
    cout << endl;

    int *p2[4]; // 指针数组
    for(int i = 0; i < 3; i++)
    {
        p2[i] = &a[i][0];
    }
    for(int i = 0; i < 3; i++)
    {
        for(int j = 0; j < 4; j++)
        {
            cout << p2[i][j] << '\n';
        }
    }
    cout << endl;    
}
```

输出：
```cpp
1
2
3
4
5
6
7
8
9
10
11
12

1
2
3
4
5
6
7
8
9
10
11
12
```