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

首先把整一行s读进来，找出s当中的a，然后把每一个字符串a换成字符串b。

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
    
    stringstream ssin(s);   // 把 字符串 初始化为 字符串流 
                            // 把ssin当成cin。相当于从字符串中读信息
    string str;
    while(ssin >> str)
        if (str == a) cout << b << ' ';
        else cout << str << ' ';
    
    return 0;
}
```

### 了解一下stringstream
stringstream是可以把一个字符串初始化成一个类似cin的东西，从中读出任意我们需要的格式的信息。

比如，我们需要读入两个int数字，一个字符串，一个double类型的数字。

ssin可以帮助我们从一个字符串中，提取我们需要的各种（格式）信息。
```c++
#include <iostream>
#include <sstream>

using namespace std;

int main()
{
 string s;
 getline(cin, s);
 
 stringstream ssin(s);
 
 int a, b;
 string str;
 double c;
 
 ssin>> a >> str >> b >> c;
 
 cout << a << endl << str << endl << b << endl << c << endl; 
 
 return 0; 
} 
```

⚠ ssin(s)的名字可以任意取，也可以是“stringstream fdsa(s);”，重点是把它初始化。

### sscanf的方式(seldom)
```c++
#include <cstdio>
#include <iostream>
#include <sstream>

using namespace std;

int main()
{
    char s[1000];
    fgets(s, 1000, stdin);

    int a, b;
    char str[1000];
    double c;
    
    sscanf(s, "%d%s%d%lf", &a, str, &b, &c); // 第一个参数是需要读的字符串，后面就跟scanf一样了
    
    printf("%d\n%s\n%d\n%lf\n", a, str, b, c);
    return 0; 
} 
```
⚠ 在不知道有多少个字的时候，sscanf其实不是很好写。它用的不是很多。
