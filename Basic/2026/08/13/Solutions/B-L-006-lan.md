
- 用户名：lan_sora
- 日期：2026-08-13


## 代码

```cPP

/*
//这不是为SET量身定制的作业吗，那还说啥了我踏马写写写写写
思路：塞进SET，看SET大小，输出SET，没了

*/


#include <iostream>
#include <set>
using namespace std;

int main()
{
    set<int> arr;
    int num;
    cin>>num;
    for (int i=0;i<num;i++){
        int input=0;
        cin>>input;
        arr.insert(input);
    }
    cout<< arr.size() << endl;
    for(auto p=arr.begin();p!=arr.end();p++){//(auto p:arr)
        cout << *p << " ";
    }

}

```

