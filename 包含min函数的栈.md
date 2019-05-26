# 题目描述
定义栈的数据结构，请在该类型中实现一个能够得到栈中所含最小元素的min函数（时间复杂度应为O（1））。


```
#include <stack>
using namespace std;
class Solution {
public:
    void push(int value) {
        if(minVal > value)
            minVal = value;
        s1.push(value);
        s2.push(minVal);
        
    }
    void pop() {
        s1.pop();
        s2.pop();
    }
    int top() {
        return s1.top();
    }
    int min() {
        return s2.top();
    }

private:
    int minVal = 0xFFFF;
    stack<int> s1;
    stack<int> s2;
};
```