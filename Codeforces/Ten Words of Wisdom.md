**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(2N)
Code:
Solution:
```cpp
#include <iostream>

using namespace std;

int main() {
    int t; cin >> t;
    for (int i = 0; i < t; ++i) {
        int max_b = 0, max_j = 0;
        int n; cin >> n;
        for (int j = 0; j < n; ++j) {
            int a, b; cin >> a >> b;
            if (a <= 10) {
                if (max_b < b) {
                    max_b = b;
                    max_j = j + 1;
                }
            }
        }

        cout << max_j << endl;
    }
    return 0;
}
```
**Explanation:**
	Цель: Нужно узнатьномер учатсника, у которого наивысшее качество ответа и количество слов не больше десяти.
	Решение: Сохранять лучшей качественный ответ и номер учатсника. В конце вернуть номер учатника с наилучшим ответом.