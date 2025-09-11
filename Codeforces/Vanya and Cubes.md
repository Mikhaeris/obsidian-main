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
    int n; cin >> n;
    int sum = 0, row = 0, count = 0;
    for (int i = 1; row <= n; ++i) {
        if (sum + row + i > n) {
            break;
        }

        row += i;
        sum += row;
        ++count;
    }
    cout << count << endl;
    return 0;
}
```
**Explanation:**
	Цель: Даны кубики.Строится пирамида. Каждый ряд в пирамиде формируется от предудщего рядом плюс номер этого ряда. Узнать сколько рядов возмжно построить.
	Решение: Просто посчитать и вывести.
	P.S. это плохой код