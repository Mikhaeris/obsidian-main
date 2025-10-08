**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N\*2)
Code:
Solution:
```cpp
#include <iostream>

using namespace std;

int main() {
    int t; cin >> t;
    while (t--) {
        int num; cin >> num;
        cout << num*2 << endl;
    }
    return 0;
}
```
**Explanation:**
	Цель: Дано количество банок вареньяЮ которое нужно риготовить, для одной банки нужно 2кг ягоды и 2кг сахара.
	Решение: Просто умножить на два.