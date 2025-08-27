**Complexity:** 800
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

    vector<int> vec;
    for (int i = 0; i < n; i++) {
        int num; cin >> num;
        if (num <= 5-k) {
            vec.push_back(num);
        } 
    }

    cout << vec.size()/3 << endl;
    return 0;
} 
```
**Explanation:**
	Цель: Даны N чисел, нужно узнать сколько получится пар по три человека, такие что для каждое число меньше или равняется n-
	Решение: Получать числа и проверять.