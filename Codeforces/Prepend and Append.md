**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
#include <iostream>
#include <string>

using namespace std;

int main() {
    int t; cin >> t;
    do {
        int n; cin >> n;
        string str(n, '0');
        cin >> str;

        int l = 0, r = n-1;
        while (l < r) {
            if (str[l] == str[r]) {
                break;
            }
            ++l;
            --r;
        }
        cout << r-l+1 << endl;
    } while(--t);
    return 0;
}
```
**Explanation:**
	Цель: Дана строка, к ней может быть дописна спереди ноль а сзади еденица или наоброт. Определить какой минимальной длины была изначальная строка.
	Решение: Два указателя, проходится пока значения в них не равны.