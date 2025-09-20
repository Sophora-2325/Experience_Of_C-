## 题目 3347: 蓝桥杯2025年第十六届省赛真题-冷热数据队列
___
大家还是需要了解这些常用的数据结构的，特别是功能已经被定义为头文件的数据结构  
目前常用的数据结构有数组arr，动态数组vector（个人感觉比malloc好用一些）  
二叉树，队列，双端列表，栈  
需要知道头文件中的常用方法  
___  
```
#include<iostream>
#include<list>
#include<unordered_map>

using namespace std;

int n1, n2, m;
list<int>q1, q2;
unordered_map<int, pair<int, list<int>::iterator>>mp;//又出现一种hash表
int main() {
	cin >> n1 >> n2 >> m;
	while (m--) {
		int x;
		cin >> x;
		if (!mp.count(x)) {//!mp.count(x) 确实涉及隐式类型转换
			q2.push_front(x);
			mp[x] = {2, q2.begin()};
		} else {
			int id = mp[x].first;
			auto it = mp[x].second;
			mp.erase(x);
			if (id == 1)q1.erase(it);
			else q2.erase(it);
			q1.push_front(x);
			mp[x] = {1, q1.begin()};
		}
		if (q1.size() > n1) {
			x = *q1.rbegin();//q1.rbegin()返回一个迭代器，可以理解为一个数组的开头
			q1.pop_back();
			mp[x] = {2, q2.begin()};
		}
		if (q2.size() > n2) {
			x = *q2.rbegin();
			q2.pop_back();
			mp.erase(x);
		}
	}
	for (auto x : q1) cout << x << " ";
	cout << endl;
	for (auto x : q2) cout << x << " ";
	cout << endl;
	return 0;
}
```
