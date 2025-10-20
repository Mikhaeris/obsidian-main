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
    while (t--) {
        int sum = 0, count = 0;
        int n, k; cin >> n >> k;
        for (int i = 0; i < n; ++i) {
            int num; cin >> num;
            if (num >= k) {
                sum += num;
            } else if (num == 0 && sum > 0) {
                --sum;
                ++count;
            }
        }
        cout << count << '\n';
    }
    cout.flush();
    return 0;
}
```
**Explanation:**
	Цель: Дан массив чисел, если число боьше k, то нужно забрать это число, если число равно 0, нужно отдать одну монету. Нужно узнать скольким людям будут отданы монеты.
	Решение: Итеративно пройтись совершая данные операции.