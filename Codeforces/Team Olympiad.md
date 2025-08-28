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
#include <climits>

using namespace std;

int main() {
    int n; cin >> n;

    vector<vector<int>> vec(3);
    for (int i = 0; i < n; i++) {
        int t; cin >> t;
        vec[t-1].push_back(i+1);
    }

    size_t min_size = INT_MAX;
    for (int i = 0; i < vec.size(); i++) {
        min_size = min(min_size, vec[i].size());
    }

    cout << min_size << endl;
    for (int i = 0; i < min_size; i++) {
        for (int j = 0; j < 3; j++) {
            cout << vec[j][i] << " ";
        }
        cout << endl;
    }

    return 0;
} 
```
**Explanation:**
	Цель: Есть участиник олимпиады, которые хороши только в одном предмете, требуется собрать команды, чтобы в каждой были участники из всех предметов(всего 3). Узнать сколько команд получится и вывести индексы учатников в каждой команде.
	Решение: Создать матрицу, в которой i строка обозначает предмет, а j индекс участника. Заполнить эту матрицу. Дальше найти минимальный размер строки в этой матрице. вывести минимальный размер и проходится по столбцам матрицы, выводя всех участников всех получившихся сформированных команд.
	P.S. Это самый худших код за последнее время, мне абсолютно не нравится.