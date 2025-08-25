**Complexity:** 1000
Answer:
	Time Complexity: O(1)
	Space Complexity: O(1)
Code:
Solution:
```cpp
#include <iostream>  
#include <utility>  
#include <set>  
  
using namespace std;  
  
struct Compare {  
    bool operator()(const pair<int, int>& pr1, const pair<int, int>& pr2) const {  
        return pr1.first < pr2.first;  
    }  
}; 
  
int main() {  
    int s, n; cin >> s >> n;  
  
    multiset<pair<int, int>, Compare> st;  
    for (int i = 0; i < n; ++i) {  
        pair<int, int> nw;  
        cin >> nw.first >> nw.second;  
        st.insert(nw);  
    }  
  
    for (auto it = st.begin(); it != st.end(); ++it) {  
        if (s <= it->first) {  
            cout << "NO" << endl;  
            return 0;  
        }  
        s += it->second;  
    }  
  
    cout << "YES" << endl;  
  
    return 0;  
}
```
**Explanation:**
	Цель: Дано два числа - сила игрока, количество противников. Далее следуют враги - сила и награда. Игрок побеждает, если его сила строго больше силы проивника. Игрок может атаковать противников в любом порядке. Нужно узнать смеожет ли он победить всех противников.
	Решение: Хранить противников в multiset<pair<сила, награда>>. Все противники будут осортированы по возрастнию силы. Теперь осталось пройти по всем врага и смотреть можно ли их победить. Вывести результат.