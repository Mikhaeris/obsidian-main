**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
#include <iostream>
#include <string>

using namespace std;

int main() {
    string correct_str = "codeforces";
    int t; cin >> t;
    do {
        int diff = 0;
        string s; cin >> s;
        for (int i = 0; i < s.size(); ++i) {
            if (s[i] != correct_str[i]) {
                ++diff;
            }
        }
        cout << diff << endl;
    } while (--t);
    return 0;
}
```
**Explanation:**
	Цель: Дана строка s, узнать в скольких идексах эта строка отличается от строки "codeforces".
	Решение: Проходится по кажому символу и сравнивать.