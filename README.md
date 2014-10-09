利用C++STL中的stack实现了基本的进制转换，top函数只是显示栈顶元素而pop函数是弹出栈顶元素。

#include <iostream>
#include <cstring>
#include <cmath>
#include <cstdlib>
#include <algorithm>
#include <stack>

using namespace std;

//利用stack进行进制转换的程序

void convert(stack<char>&s, int n, int base){
    static char digit[] = {'0', '1', '2', '3', '4', '5',
    '6', '7', '8', '9', 'A', 'B', 'C', 'D', 'E', 'F'};
    while(n > 0){//除到商为0停止
        s.push(digit[n%base]);
        n = n/base;//迭代
    }
}

int main(){
    
    int numb = 0;//初始数字
    while(cin>>numb){
        stack<char> s;
        int base = 0;
        cout<<"要转化的进制:";
        cin>>base;//要转化的进制数
        convert(s, numb, base);
        while(!s.empty()){
            cout<<s.top();//输出栈顶元素
            s.pop();//弹出栈顶元素
        }
        cout<<endl;
    }
}
