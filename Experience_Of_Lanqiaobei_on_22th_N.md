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
```
#include<bits/stdc++.h>

using namespace std;

int main(){
	int n,sum = 0;
	cin >> n;
	for(int i = 0; i < n; i++){
		long long a;
		cin >> a;
		if(a < 3 || (a & (a - 1)) == 0) sum++;
	}
	cout << sum;
	
	//根据下面的暴力方法可以找到规律 
	// for(int i = 3; i <= 1000; i++){
	//     int l = 1,sum = 0;
	//     for(int r = 2; r < i; r++){
	//         int a = (r + l) * (r - l + 1) / 2;
	//         while(a > i && l + 1 < r){
	//             a -= l;
	//             l++;
	//         }
	//         if(a == i){
	//             sum = i;
	//             break;
	//         }
	//     }
	//     if(sum == 0) cout << i << ' ';
	// }
	//输出为 4 8 16 32 64 128 256 512
	//输出都为2进制的位数，如 8 = 1000 将其减一得 7 = 0111，二者与运算刚刚好为0，其他也同理
	//所以可得如果 (a & (a - 1)) == 0 那么它就不是有诗意的数
	return 0;
}
```
