## 1. \#include <vector>
vector是变长数组，支持随机访问，不支持在任意位置 O(1)O(1) 插入。为了保证效率，元素的增删一般应该在末尾进行。

### 1.1 声明
```c++
#include <vector>   // 头文件
vector<int> a;      // 相当于一个长度动态变化的int数组
vector<int> b[233]; // 相当于第一维长233，第二位长度动态变化的int数组
struct rec{…};
vector<rec> c;      // 自定义的结构体类型也可以保存在vector中
```
    
### 1.2 size/empty
size函数返回vector的实际长度（包含的元素个数），empty函数返回一个bool类型，表明vector是否为空。二者的时间复杂度都是 O(1)O(1)。
    
所有的STL容器都支持这两个方法，含义也相同，之后我们就不再重复给出。

### 1.3 clear
clear函数把vector清空。

### 1.4 迭代器
迭代器就像STL容器的“指针”，可以用星号*操作符解除引用。

一个保存int的vector的迭代器声明方法为：
```c++
vector<int>::iterator it;
```
vector的迭代器是“随机访问迭代器”，可以把vector的迭代器与一个整数相加减，其行为和指针的移动类似。可以把vector的两个迭代器相减，其结果也和指针相减类似，得到两个迭代器对应下标之间的距离。

### 1.5 begin/end
begin函数返回指向vector中第一个元素的迭代器。例如a是一个非空的vector，则*a.begin()与a[0]的作用相同。

所有的容器都可以视作一个“前闭后开”的结构，end函数返回vector的尾部，即第n 个元素再往后的“边界”。*a.end()与a[n]都是越界访问，其中n = a.size()。

下面两份代码都遍历了vector<int> a，并输出它的所有元素。
```c++
for (int i = 0; i < a.size(); i ++)
    cout << a[i] << endl;

for (vector<int>::iterator it = a.begin(); it != a.end(); it ++)
    cout << *it << endl;
```
  
### 1.6 front/back
    
front函数返回vector的第一个元素，等价于*a.begin()和a[0]。
    
back函数返回vector的最后一个元素，等价于*--a.end()和a[a.size() – 1]。

### 1.7 push_back()和pop_back()
    
a.push_back(x)把元素x插入到vector a的尾部。
    
b.pop_back()删除vector a的最后一个元素。

## 2. #include <queue>
    
头文件queue主要包括循环队列queue和优先队列priority_queue两个容器。

### 2.1 声明
```c++
queue<int> q;
struct rec{…}; queue<rec> q;                        //结构体rec中必须定义小于号
priority_queue<int> q;                              // 大根堆
priority_queue<int, vector<int>, greater<int>> q;   // 小根堆
priority_queue<pair<int, int>>q;
```
    
### 2.2 循环队列queue
```c++
push    // 从队尾插入
pop     // 从队头弹出
front   // 返回队头元素
back    // 返回队尾元素
```
  
### 2.3 优先队列priority_queue
```c++
push    // 把元素插入堆
pop     // 删除堆顶元素
top     // 查询堆顶元素（最大值）
```
    
## 3. #include <stack>
头文件stack包含栈。声明和前面的容器类似。
    
```c++
push    // 向栈顶插入
pop     // 弹出栈顶元素
```
  
## 4. #include <deque>
双端队列deque是一个支持在两端高效插入或删除元素的连续线性存储空间。它就像是vector和queue的结合。与vector相比，deque在头部增删元素仅需要 O(1)O(1) 的时间；与queue相比，deque像数组一样支持随机访问。
    
```c++
[]              // 随机访问
begin/end       // 返回de
```
