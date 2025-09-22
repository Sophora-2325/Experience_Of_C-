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


# 19714 看题解上说有一个相似的题目，叫“数学诗意”

运用了位运算来判断对象是否纯偶数  
至于为什么要纠结于是否为纯偶数，我在下面给出思考过程  
不难发现，对于奇数可以写作两个连续的数的和：
∀n=2k+1,k∈N,n=k+(k+1)  
我们可以继续，从求和公式的奇偶性下手，令：  
f(a,k)=【k(a+a+k−1)】/2  
若k为奇数，则结果为偶数，k为偶数，则结果为奇数

```
#include<iostream>
#define ll long long
using namespace std;

ll n, m;
ll ans;
bool check(ll x) {
	int s = 0;
	while (x) {
		s += x & 1;//x&1是为了判断x二进制末尾是否为1，若为则x为奇数
		x >> 1;//此举的意义为对x进行向下取证
	}
	if (s == 1) return true;
	return false;
}
int main() {
	cin >> n;
	for (int i = 0; i < n; i++) {
		cin >> m;
		if (check(m))ans++;
	}
	cout << ans;
}
```
