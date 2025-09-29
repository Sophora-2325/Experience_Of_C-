#  Z 字形变换
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
<img width="1201" height="1119" alt="696d4ce97f1539f10d12a85115e80f57" src="https://github.com/user-attachments/assets/58e3aec9-4a00-4c23-ab44-3cc03a7dfa2b" />

