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
        int n; cin >> n;
        string f, s;

        cin.ignore();
        char c;
        while ((c = getchar()) != '\n') {
            if (c == 'B') {
                c = 'G';
            }
            f += c;
        }

        bool flag = true;
        int j = 0;
        while ((c = getchar()) != '\n') {
            if (c == 'B') {
                c = 'G';
            }

            if (c != f[j++]) {
                flag = false;
            }
        }
        
        (flag)
        ? cout << "YES" << endl
        : cout << "NO" << endl;

    }
    return 0;
}
```
**Explanation:**
	Цель: Даны две строки, узнать, являются ли они одинаковыми, если G и B одианоковые ц
	Решение: Если в фотографии есть цветный цвета, то в вывести что она цветная, иначе она черно-белая.