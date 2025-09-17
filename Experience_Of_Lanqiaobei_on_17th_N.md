# 题目 3325 蓝桥杯2025年第十六届省赛真题-2025 图形
### 属于比较一般的构造题目，其实设一个二维数组，然后调出来也可以做出来。不过有点麻烦，直接用这种比较方便。
```
#include<iostream>

using namespace std;

int main(){
	int arr[4]={2,0,2,5};
	int h,w;
	cin>>h>>w;
	for(int i=0;i<h;i++){
		for(int j=i;j<i+w;j++){//这属于构造题，看仔细点
			cout<<arr[j%4];
		}
		cout<<endl;
	}
	return 0;
}

```
# 题目 3326 蓝桥杯2025年第十六届省赛真题-最短距离
## 这种有最值要求的可以考虑贪心算法，毕竟有求最值的功能嘛。
### 同时要在意题目中关于数据范围的要求，有时int的范围不够，可以用long long，当然也可以直接都用上long long，就是多占了些空间
```
//这不一眼贪心算法？
#include<iostream>
#include<vector>
#include<algorithm>
#define ll long long //不要用忘记define 来减少重复劳动
//#include<bits/stdc++.h> 万能头文件
using namespace std;


int main(){
	int n=0;cin>>n;
	//两种输入方式
	vector<ll>x(n);
	vector<ll>y;
	int temp;
	for(int i=0;i<n;i++){
		cin>>x[i];//更直接，知道vector长度常用
	}
	for(int i=0;i<n;i++){
		cin>>temp;
		y.push_back(temp);//比较灵活，不知道长度时使用
	}
	sort(x.begin(),x.end());
	sort(y.begin(),y.end());
	//全部局部最优合起来就是全局最优
	int t=0;
	ll result=0;
	while(t<n){
		result+=abs(y[t]-x[t]);
		t++;
	}
	cout<<result;
	return 0;
}

/*
#include<iostream>
#include<vector>
#include<algorithm>
//#include<bits/stdc++.h> 万能头文件
using namespace std;
//注意范围，超范围的话会减分的。
int main(){
int n=0;cin>>n;
//两种输入方式
vector<int>x(n);
vector<int>y;
int temp;
for(int i=0;i<n;i++){
cin>>x[i];//更直接，知道vector长度常用
}
for(int i=0;i<n;i++){
cin>>temp;
y.push_back(temp);//比较灵活，不知道长度时使用
}
sort(x.begin(),x.end());
sort(y.begin(),y.end());
//全部局部最优合起来就是全局最优
int t=0;
int result=0;
while(t<n){
result+=abs(y[t]-x[t]);
t++;
}
cout<<result;
return 0;
}
*/
```
