# 题目 3327: 蓝桥杯2025年第十六届省赛真题-倒水
```
#include <iostream>
//二分+一点数学知识
using namespace std;

typedef long long LL;
const int N = 1e5 + 10;

LL n, k;
LL a[N];

bool check(LL x)
{
	// 从前往后模拟倒水过程
	for(int i = 1; i <= k; i++)
	{
		LL t = 0; // 当水量为 x 时，能够往下一个杯子中倒的水量
		for(int j = i; j <= n; j += k)
		{   
			// 判断是否能倒
			if(a[j] + t >= x) t = a[j] + t - x;
			else return false;
		}
	}
	return true;
}

int main()
{
	cin >> n >> k;
	for(int i = 1; i <= n; i++) cin >> a[i];
	
	LL l = 1, r = 1e5;
	while(l < r)
	{
		LL mid = (l + r + 1) / 2;
		if(check(mid)) l = mid;
		else r = mid - 1;
	}
	
	cout << l << endl;
	
	return 0;
}
```
