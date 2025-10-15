**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
#include <iostream>
#include <vector>

using namespace std;

int main() {
    int n; cin >> n;

    vector<int> vec(n);
    for (int i = 0; i < n; ++i) {
        cin >> vec[i];
    }

    vector<int> ans;
    for (int i = 0; i < n; ++i) {
        bool flag = true;
        for (int j = i+1; j < n; ++j) {
            if (vec[j] == vec[i]) {
                flag = false;
            }
        }

        if (flag) {
            ans.push_back(vec[i]);
        }
    }

    cout << ans.size() << '\n';
    for (int i = 0; i < ans.size(); ++i) {
        cout << ans[i] << ' ';
    }

    return 0;
}
```
**Explanation:**
	Цель: Удалить дубликаты в массиве, оставив последнее вхождения каждого элемента.
	Решение: Проверять что это последний элемент, если он последний, то добавить ег в массив.