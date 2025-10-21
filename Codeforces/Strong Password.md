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
    int  t; cin >> t;
    while (t--) {
        bool flag = false;
        string s; cin >> s;
        for (int i = 1; i < s.length(); ++i) {
            if (s[i] == s[i-1]) {
                char ch = s[i];
                if (ch-1 < 'a') {
                    ch += 1;
                } else if (ch+1 > 'z') {
                    ch -= 1;
                } else {
                    ch += 1;
                }
                s.insert(s.begin()+i, ch);
                flag = true;
                break;
            }
        }
        char ch = s[s.length()-1];
        if (ch-1 < 'a') {
            ch += 1;
        } else if (ch+1 > 'z') {
            ch -= 1;
        } else {
            ch += 1;
        }
        if (!flag) {
            s.insert(s.end(), ch);
        }
        cout << s << '\n';
    }
    cout.flush();
    return 0;
}
```
**Explanation:**
	Цель: Дана строка, ввод каждого символа занимает 1, если это новый символ то 2. Нужно добавить символ в строку, чтобы ее ввод занимал максимальное количество времени.
	Решение: Искать два подряд идущих числа. Если такие есть то вставлять симовол в это место, сдвигая текущий символ либо влево либо вправо по аски таблице.