**Complexity:** 1100
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
#include <iostream>
#include <vector>

using namespace std;

int main() {
    int n, k; cin >> n >> k;
    vector<int> fence(n);
    for (int& board : fence) {
        cin >> board;
    }

    int curr_sum = 0;
    int i;
    for (i = 0; i < k; ++i) {
        curr_sum += fence[i];
    }


    int min_sum = curr_sum;
    int idx = 1;

    int l = 0, r = k;
    while (r < n) {
        curr_sum -= fence[l++];
        curr_sum += fence[r++];
        if (min_sum > curr_sum) {
            min_sum = curr_sum;
            idx = l+1;
        }
    }

    cout << idx << endl; 

    return 0;
}
```
**Explanation:**
	Цель: Дана длина массива(n) и количство досок(k), которые можно убрать. Дан массив. Нужно найти такой индекс в массиве, что суммарная длина досок будет минимальной.
	Решение: Получить данные. Посчитать длину первых k досок - это будте начальной минимальной суммой. Дальше проходится двумя указателями, прибавляя новое число и убавляя первое из суммы. Если сумма меньше минимальной, то переназначить индекс. В конце вернуть индес.