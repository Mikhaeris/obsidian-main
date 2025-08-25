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
    for (int i = 0; i < t; i++){
        int k; cin >> k;

        int count = 0;
        for (int j = 1; j < k*2; j++) {
            if (j % 3 != 0 && j % 10 != 3) {
                if (++count == k) {
                    cout << j << endl;
                    break;
                }
            }
        }
    }

    return 0;
}
```
**Explanation:**
	Цель: Вывести k член последовательности, в которой нет чисел, которые делятся на три или оканчиваются на три.
	Решение: Проходится от 1 до k\*2 ищя такие числа и когда дойдет до k числа в последовательности, то вывести и завершить внутренний цикл.