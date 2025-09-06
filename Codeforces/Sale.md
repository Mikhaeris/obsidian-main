**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
#include <algorithm>
#include <iostream>
#include <vector>

using namespace std;

int main() {
    int n, m; cin >> n >> m;

    vector<int> vec(n);
    for (int& a : vec) {
        cin >> a;
    }

    sort(vec.begin(), vec.end());

    int sum = 0;
    for (int i = 0; i < vec.size() &&
                    vec[i] < 0 && i < m; ++i) {
        sum += -vec[i];
    }

    cout << sum << endl;

    return 0;
}
```
**Explanation:**
	Цель: Дан массив из n чисел. Нужно взять такие числа, что их сумма будет максимально отрицательной и количество взятых чисел будет меньше m. Вернуть эту сумму по модулю.
	Решение: Отсортировать массив. Собирать числа слева, пока они отрицательны и количество взятых меньше m.