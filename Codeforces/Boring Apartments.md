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
	Цель: Герой очень наглый и звонит в номера с одинаковыми цифрами(1, 11, 111, 1111. 2, 22) и так до 10000. В какой-то момент ему кто-то ответил и он перестал звонить. Нужно вернуть количество цифр на кооторые он нажал.
	Решение: Сначала нужно посчитать целые проходы. Дальше прибавить пройденные цифры от начала данной итерации(т.е. напрмиер число 22). Сложить два числа и вернуть ответ.