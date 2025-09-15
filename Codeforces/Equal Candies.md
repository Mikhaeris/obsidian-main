**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
#include <iostream>
#include <climits>

using namespace std;

int main() {
    int t; cin >> t;
    for (int i = 0; i < t; ++i) {
        int n; cin >> n;
        int sum = 0, min_num = INT_MAX;
        for (int j = 0; j < n; ++j) {
            int num; cin >> num;
            sum += num;
            min_num = min(min_num, num);
        }
        cout << (sum - (min_num * n)) << endl;
    }
    return 0;
}
```
**Explanation:**
	Цель: Есть n коробок конфет. Нужно чтобы в них было равное количество конфет. Можно только съедать конфеты в коробках. Вывести сколько конфет нужно съесть.
	Решение: Посчитать сумму конфет и минимально количество конфет во всех коробках. Вывести сумму минус (количество коробок умноженное на минимальное количество конфет в коробке).