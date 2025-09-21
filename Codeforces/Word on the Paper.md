**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(2N)
Code:
Solution:
```cpp
#include <iostream>
#include <vector>

using namespace std;

int main() {
    const int r = 8;
    int t; cin >> t;
    for (int i = 0; i < t; ++i) {
        vector<vector<char>> vec(r, vector<char>(r));
        for (int j = 0; j < r; ++j) {
            for (int k = 0; k < r; ++k) {
                cin >> vec[j][k];
            }
        }
        
        string word;
        for (int j = 0; j < r; ++j) {
            for (int k = 0; k < r; ++k) {
                if (vec[j][k] != '.') {
                    while (j < r && vec[j][k] != '.') {
                        word += vec[j++][k];
                    }
                    goto end;
                }
            }
        }
    end:
        cout << word << endl;
    }
    return 0;
}
```
**Explanation:**
	Цель: Дан лист бумаги, на нем написано слово сверху вниз. Нужно вывести это слово.
	Решение: Проходится по каждому ряду, пока не найдется буква. Дальше собирать слово спускаясь вниз.