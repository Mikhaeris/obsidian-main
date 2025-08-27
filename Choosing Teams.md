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
    int n, k; cin >> n >> k;

    int count = 0;
    for (int i = 0; i < n; i++) {
        int num; cin >> num;
        if (num <= 5-k) {
            count++;
        } 
    }

    cout << count/3 << endl;
    return 0;
} 
```
**Explanation:**
	Цель: Даны N чисел, нужно узнать сколько получится пар по три человека, такие что для каждое число меньше или равняется 5-k.
	Решение: Создать счетчик, в который добавлются только подходящие чисела.
	Поделить на три этот счетчик и вывести ответ. 