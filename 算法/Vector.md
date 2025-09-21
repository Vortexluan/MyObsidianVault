应当是一种类似于可变数组的东西...?
我们先看一看它的实际用法
```cpp
//首先来看创建
//vector是在stl库中的东西
//要说明的一点是obsidian对于预处理的指令都是会灰化的，这里的井号灰化并没有问题
//当然，我们也可以使用#include<vector>的方式来做到引入头文件

#include<bits/stdc++.h>
using namespace std;
vector<int>v;//这里我们就拥有了一个名为v的一维可变数组，用v[1],v[2]的方式来访问
vector<int>v[114];//这里我们得到的就是名为v的二维可变数组，用v[1][2]的方式来访问,其中第一维为0-113

//接下来就说明一些关于vector的操作
v.push_back(114);//在vector的末尾添加元素
v[1];//就像正常访问数组一样访问vector
v.size();//获得v的大小
v.clear();//清空
v.begin();//取得v的第一个元素的地址
v.end();//取得v的最后一个元素的地址
//如果我们想要遍历vector只需要像正常的数组一样就可以了

//删除，erase()这个函数有两个用法
v.erase(pos);//删除下标为pos的数据
v.erase(start,end);//删除[start,end)的数据，注意一下这里的左闭右开

//assign()更为灵活的复制方式
v.assign(first,last);//给出两个地址，把[first,last]对应的值全部一一复制下来，
//例如v1={1,2,3,4,5};
//v.assign(v1.begin()+1;
//v1.begin()-1);
//可以得到v={2,3,4}
v.assign(n,val);//赋值数量为n的val

//insert()
```
我们可以使用vector来构造图，这是非常好用的东西