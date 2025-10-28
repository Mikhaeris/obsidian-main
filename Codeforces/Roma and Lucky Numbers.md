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
    int count = 0;
    int n, k; cin >> n >> k;
    for (int i = 0; i < n; ++i) {
        int num; cin >> num;
        
        int curr_c = 0;
        while (num) {
            if (num % 10 == 4 || num % 10 == 7) {
                ++curr_c;
            }
            num /= 10;
        }

        if (curr_c <= k) {
            ++count;
        }
    }
    cout << count << endl;
    return 0;
}
```
**Explanation:**
	Цель: Даны числа, нужно узнать в скольких числах содержатся счасливые цифры меньше k.
	Решение: Считать в каждом числе количество цифр и проверять.