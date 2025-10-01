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
    int n; cin >>n;
    
    int max_length = 0, curr_length = 0;
    int prev;
    cin >> prev;
    for (int i = 1; i < n; ++i) {
        int curr; cin >> curr;
        
        if (prev < curr) {
            ++curr_length;
        } else {
            max_length = max(max_length, ++curr_length);
            curr_length = 0;
        }

        prev = curr;
    }
    max_length = max(max_length, ++curr_length);

    cout << max_length << endl;

    return 0;
}
```
**Explanation:**
	Цель: Найти самую длинную возврастающую последовательность.
	Решение: Считать возврастающие последовательности и находить максимальную.