**Complexity:** 900
Answer:
	Time Complexity: O(1)
	Space Complexity: O(1)
Code:
Solution:
```cpp
#include <iostream>  
#include <set>  
#include <climits>  
  
using namespace std;  
  
int main() {  
    int n, m; cin >> n >> m;  
    multiset<int> st;  
    for (int i = 0; i < m; ++i) {  
        int num; cin >> num;  
        st.insert(num);  
    }  
  
    int diff_min = INT_MAX;  
    auto l = st.begin(), r = next(st.begin(), n-1);  
    for ( ; r != st.end(); l++, r++) {  
        int diff_curr = *r - *l;  
        diff_min = min(diff_curr, diff_min);  
    }  
  
    cout << diff_min << endl;  
  
    return 0;  
}
```
**Explanation:**
	Цель: Дано n учеников и m пазлов. Нужно купить n пазлов, чтобы разница в количестве пазлов в наборе между макимальным и минимальным была минимальной.
	Решение: Сразу запихивать пазлы в сет, чтобы данные были отсортированы. Дальше с помощью [[Sliding window]] (или двумя указателя) проходится по сету и искать минимальную разницу между количеством пазлов.
	P.S. Конечно можно использовать vector и sort и выйдет короче и быстрее, но с set решение прикольное.