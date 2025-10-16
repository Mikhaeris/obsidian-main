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
    int arr[3] = {0};
    int n; cin >> n;

    int counter = 0;
    for (int i = 0; i < n; ++i) {
        int num; cin >> num;
        arr[counter++] += num;
        if (counter == 3) {
            counter = 0;
        }
    }

    if (arr[0] > arr[1] && arr[0] > arr[2]) {
        cout << "chest" << '\n';
    } else if (arr[1] > arr[0] && arr[1] > arr[2]) { 
        cout << "biceps" << '\n';
    } else {
        cout << "back" << '\n';
    }

    return 0;
}
```
**Explanation:**
	Цель: Узнать чего больше, первого второго или третьего.
	Решение: Посчиать и узать.