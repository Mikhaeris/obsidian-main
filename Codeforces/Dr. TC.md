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
    while (t--) {
        int n; cin >> n;
        string s; cin >> s;
        
        int s_sum = 0;
        for (int i = 0; i < s.length(); ++i) {
            if (s[i] == '1') {
                ++s_sum;
            }
        }

        int max_sum = s_sum;
        int sum = s_sum;
        for (int i = 0; i < s.length(); ++i) {
            max_sum += (s[i] == '1') ? sum-1 : sum+1;
        }

        cout << max_sum - s_sum << endl;

    }
    return 0;
}
```
**Explanation:**
	Цель: Дана строка из 0 и 1. Кждый шаг i-й символ первеорачиватеся, нужно посчитать какая сумма будет во всех перестановок, кромеихначаельной строки.
	Решение: Посчитать сумму данной строки. На каждом шаге добавлять или убавлять у сумму еденичку и доабвлять к максималной сумме.