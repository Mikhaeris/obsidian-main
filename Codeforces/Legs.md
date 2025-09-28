
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
    for (int i = 0; i < t; ++i) {
        int n; cin >> n;
        cout << (n / 4) + ((n % 4) / 2) << endl;
    }
    return 0;
}
```
**Explanation:**
	Цель: Фермер посчитал количество ног животных на его ферме. На ферме только курицы и коровы. Нужно узнать какое мнимальное количество животных может бытьне ферме.
	Решение: Сначала подсчитать коровов, а все оставшиеся это курицы.