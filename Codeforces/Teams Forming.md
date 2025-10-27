**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
#include <algorithm>
#include <iostream>
#include <vector>

using namespace std;

int main() {
    int n; cin >> n;
    vector<int> vec(n);
    for (auto& num : vec) {
        cin >> num;
    }

    sort(vec.begin(), vec.end());
    
    int count = 0;
    for (int i = 0; i < n; i += 2) {
        count += vec[i+1] - vec[i];
    }
    cout << count << endl;
    return 0;
}
```
**Explanation:**
	Цель: Даны n учеников, нужно составить из них команды по 2 человека, чтобы в каждой команде умения учеников были равные их можно добучать. Какое минимальное количесто задач нужно прорешать всем ученикам, чтобы сформировать команды.
	Решение: Отсортировать по возрастанию. Взять первого ученика и дать ему прорешать столько задач, скольок разница у него со следующим и так со всеми учениками по два.