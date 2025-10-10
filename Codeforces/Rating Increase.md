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
    while (t--) {
        string str; cin >> str;
        int i = 1;
        while (i < str.length() && str[i] == '0') {
            ++i;
        }

        string f = string(str.begin(), str.begin() + i);
        string s = string(str.begin() + i, str.end());
        
        if (i <= s.length() && stoi(f) < stoi(s)) {
            cout << f << ' ' << s << '\n';
        } else {
            cout << -1 << '\n';
        }
    }
    cout.flush();
    return 0;
}
```
**Explanation:**
	Цель: Дана строка из цифр, нужно найти в ней два сичла идущи друг за другом, такие что не начинаются с нуля, содержат хотя бы одну цифру и b > a.
	Решение: Первый символ это цифра больше нуля, значит нужно увеличивать индекс, пока встречает нуль. Если Дошли до конца строки или a > b, тогда -1, иначе напечатать первое число начиная с начала до символа i, а второе начиная с индекса i до конца слова.