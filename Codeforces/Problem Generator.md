**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
#include <iostream>

using namespace std;

int main() {
    int t; cin  >> t;
    while (t--) {
        char arr[7] = {0};
        int n, m; cin >> n >> m;
        for (int i = 0; i < n; ++i) {
            char c; cin >> c;
            ++arr[c - 'A'];
        }
        
        int ans = 0;
        for (int i = 0; i < 7; ++i) {
            if (arr[i] < m) {
                ans += m - arr[i];
            }
        }
        cout << ans << endl;
    }
    
    return 0;
}
```
**Explanation:**
	Цель: Дана строка, где каждая буква соответствует  задаче. Нужно узнать сколько задач, нужно добавить, чтобы можно было провести m раундов. 
	Решение: Считать количество каждой задачи и прибавлять к ответут, сколько не хватает до m.