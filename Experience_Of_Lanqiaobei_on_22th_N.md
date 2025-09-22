# 题目 3319: 蓝桥杯2025年第十六届省赛真题-可分解的正整数
感觉这个题没啥能将的，能看出来就能做出来，看不出来就很难全做对，我当初就没做对。
```
#include<iostream>
#include<algorithm>
using namespace std;

int main() {
	int N;
	cin >> N;
	int arr[N];
	for (int i = 0; i < N; i++) cin >> arr[i];
	int length = sizeof(arr) / sizeof(arr[0]);
	cout<<N-count(arr,arr+length,1);  能给大家增加点知识点的就这个地方，快速计算某个数值在数组中出现的次数
	return 0;
}
```
