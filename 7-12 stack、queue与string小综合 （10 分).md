# 7-12 stack、queue与string小综合 （10 分)
输入一个字符串line，输入一个字符x。<br>
将line中的字符依次入栈，然后输出栈中元素个数与栈顶元素。<br>
然后将栈中元素依次出栈并输出，出栈时将不等于x的字符依次入队列。<br>
输出队列元素个数，队头与队尾 然后输出队列中所有元素。

## 输入格式:
输入一个个字符串 输入一个字符

## 输出格式:
将line中的字符依次入栈，然后输出栈中元素个数与栈顶元素。<br>
然后将栈中元素依次出栈并输出，出栈时将不等于x的字符依次入队列，以空格分隔。<br>
输出队列元素个数，队头与队尾，以空格分隔。<br>
然后输出队列中所有元素。

## 输入样例:
```
ThisIsATest s
```

## 输出样例:
```
11 t
tseTAsIsihT
8 t T
teTAIihT
```

## 代码：
```cpp
#include<iostream>
#include<string>
#include<stack>
#include<queue>
using namespace std;

int main() {
	stack<char> S;
	queue<char> Q;
	char x;
	int cnt_s = 0, cnt_q = 0;
	string str;
	cin >> str;
	cin >> x;
	for (int i = 0; i < str.length(); i++) {
		char temp = str[i];
		S.push(temp);
		cnt_s++;
	}
	cout << S.size() << " " << S.top() << endl;
	while (cnt_s--) {
		cout << S.top();
		if (S.top() != x) {
			Q.push(S.top());
			cnt_q++;
		}
		S.pop();
	}
	cout << endl;
	cout << Q.size() << " " << Q.front() << " " << Q.back() << endl;
	while (cnt_q--) {
		cout << Q.front();
		Q.pop();
	}
	return 0;
}
```
