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
    for (int i = 0; i < t; ++i) {
        int c;
        int n; cin >> n;
        string s;
        cin >> s;

        int last = 'a';
        for (int j = 0; j < s.length(); ++j) {
            last = max(last, static_cast<int>(s[j]));
        }
        cout << last - 'a' + 1 << endl;
    }
    return 0;
}
```
**Explanation:**
	Цель: Дано слово, нужно узнать какой длины алфавит нужно знать, чтобы напистаь это слово.
	Решение: В слове исать макимальное по коду букву. Вернуть эту букву относительно начала алфавита.