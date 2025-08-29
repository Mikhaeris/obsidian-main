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
    int t; cin >> t;
    for (int i = 0; i < t; i++) {
        char s1[4], s2[4];
        cin >> s1 >> s2;

        char temp = s1[0];
        s1[0] = s2[0];
        s2[0] = temp;

        cout << s1 << " " << s2 << endl;
    }
    return 0;
}
```
**Explanation:**
	Цель: Даны два слова длинной три. Нужно помеять первые символы в жтих словах и вывести.
	Решение: Два массива размером 4(включаю заершающий ноль). Меть местами первые элементы и вывести.