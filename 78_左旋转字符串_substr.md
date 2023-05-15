### 78. 左旋转字符串
字符串的左旋转操作是把字符串前面的若干个字符转移到字符串的尾部。

请定义一个函数实现字符串左旋转操作的功能。

比如输入字符串"abcdefg"和数字 2，该函数将返回左旋转 2 位得到的结果"cdefgab"。

注意：

数据保证 n 小于等于输入字符串的长度。

**数据范围**

输入字符串长度 [0,1000]。

**输出样例：** 

输入："abcdefg" , n=2

输出："cdefgab"

### 复习一下substr
substr(start, length) 表示从起始位置start开始、长度是length这一段字符串。


### 代码
```c++
string leftRottateString(string str, int n) {
  return str.substr(n) + str.substr(0, n);
}
```
