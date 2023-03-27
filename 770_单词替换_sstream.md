### 770. 单词替换
输入一个字符串，以回车结束（字符串长度不超过 100）。

该字符串由若干个单词组成，单词之间用一个空格隔开，所有单词区分大小写。

现需要将其中的某个单词替换成另一个单词，并输出替换之后的字符串。

**输入格式**

输入共 3 行。

第 1 行是包含多个单词的字符串 s;

第 2 行是待替换的单词 a(长度不超过 100);

第 3 行是 a 将被替换的单词 b(长度不超过 100)。

**输出格式**

共一行，输出将 s 中所有单词 a 替换成 b 之后的字符串。

**输入样例：** 

You want someone to help you

You

I

**输出样例：** 

I want someone to help you

### 思路

首先把整一行都进来，然后把每一个字符串a换成字符串b。

### 代码
```c++
#include <iostream>
#include <sstream>

using namespace std;

int main()
{
    string s, a, b;
    
    // 可以读入空格的读入方式
    getline(cin, s);
    cin >> a >> b;
    
    //找出s当中的a
    stringstream ssin(s);   // 把 字符串 初始化为 字符串流 
                            // 把ssin当成cin。相当于从字符串中读信息
    string str;
    while(ssin >> str)
        if (str == a) cout << b << ' ';
        else cout << str << ' ';
    
    return 0;
}
```
