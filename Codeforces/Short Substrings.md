**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
#include <cstdio>
#include <iostream>

using namespace std;

int main() {
    int t; cin >> t;
    getchar();
    for (int i = 0; i < t; i++) {
        string s;
        int c;
        s += getchar();
        for (int j = 0; (c = getchar()) != '\n'; j++) {
            if (!(j & 1)) {
                s += c;
            }
        }
        cout << s << endl;
    }
    return 0;
}
```
**Explanation:**
	Цель: lДано строка B, которая получена из строки A. Строка B формируется таким образом берется каждая подстрока из A размером 2 по очереди и прибавляется к B. Нуэно узнать строку A из строки B.
	Решение: Брать только четные индексы поступабщих строк и добавлять в ответ и сразу же выводить полученную строку.