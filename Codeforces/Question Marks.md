**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
#include <iostream>

using namespace std;

int main() {
    int t; cin >> t;
    while (t--) {
        int arr[5] = {0};
        int n; cin >> n;
        for (int i = 0; i < n*4; ++i) {
            char ch; cin >> ch;
            if (ch == '?') { ++arr[4]; }
            else { ++arr[ch - 'A']; }
        }
        
        int count = 0;
        for (int i = 0; i < 4; ++i) {
            if (arr[i] <= n) {
                count += arr[i];
            } else {
                count += n;
            }
        }

        cout << count << '\n';
    }
    cout.flush();
    return 0;
}
```
**Explanation:**
	Цель: Дана строка символов(A, B, C, D, ?). Всего правильных 4\*n данного ответа. Сколько максимум праивльных ответов можно получить?
	Решение: Подсчитать количество ответов. Добавить сколько есть в ответ, либо максимум(если превышает 4\*n).