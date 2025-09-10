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
    for (int i = 0; i < t; ++i) {
        string str = ""; cin >> str;

        if (str.length() & 1) {
            cout << "NO" << endl;
            continue;
        }

        bool flag = true;
        int l = 0, r = str.length() / 2;
        for (int i = 0; i < str.length() / 2; ++i) {
            if (str[l++] != str[r++]) {
                flag = false;
                continue;
            }
        }

        if (flag) {
            cout << "YES" << endl;
        } else {
            cout << "NO" << endl;
        }
    }
    return 0;
}
```
**Explanation:**
	Цель: Дана строка нужно проверить, что оно состоит из двух равных половинок.
	Решение: Если длина строки нечетная, то не подходит. Иначе два указателя, один на начало, второй в центр и идти пока подстроки равны.