#  Z 字形变换
![Uploading 696d4ce97f1539f10d12a85115e80f57.png…]()

```
class Solution {
public:
    string convert(string s, int numRows) {
        if(numRows<2) return s;
        vector<string>list(numRows);
        int i=0,flag=-1;
        for(char c:s){
            list[i].push_back(c);
            if(i==0||i==numRows-1)
            flag=-flag;
            i+=flag;
        }
        string res;
        for(string &c:list)
        res+=c;
        return res;
    }
};
```


