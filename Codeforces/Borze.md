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

int main () {
    string str; cin >> str;

    string ans = "";
    for (int i = 0; i < str.size(); ++i) {
        if (str[i] == '-' && str[i+1] == '-') {
            ans.push_back('2');
            ++i;
        } else if (str[i] == '-' && str[i+1] == '.') {
            ans.push_back('1');
            ++i;
        } else {
            ans.push_back('0');
        }
    }

    cout << ans << endl;

    return 0;
}
```
**Explanation:**
	Цель: Нужнорасшифровать азбуку Борзе. Азбука Борзе состоит из: '.' - 0, '-.' - 1, '--' - 2.
	Решение: Расшифровывать от большего к меньшему.