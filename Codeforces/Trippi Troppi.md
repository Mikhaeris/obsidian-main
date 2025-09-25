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
    int t; cin >> t;
    cin.ignore();
    for (int i = 0; i < t; ++i) {
        string str;
        char c;
        while ((c = getchar()) != '\n') {
            str+= c;
        }

        string ans;
        ans += str[0];
        for (int j = 0; j < str.length(); ++j) {
            if (str[j] == ' ') {
                ans += str[j+1];
            }
        }
        cout << ans << endl;
    }
    return 0;
}
```
**Explanation:**
	Цель: Получить аббревиатуру предложения.
	Решение: Получать первые буквы слов.