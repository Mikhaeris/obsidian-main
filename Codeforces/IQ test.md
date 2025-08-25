**Complexity:** 1300
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
int main() {  
    unordered_map<bool, pair<int, int>> mp;  
  
    int n = 0; cin >> n;  
    for (int i = 0; i < n; ++i) {  
        int a = 0; cin >> a;  
        ++mp[a % 2].first;  
        mp[a % 2].second = i+1;  
    }  
  
    cout << ((mp[0].first > mp[1].first) ? mp[1].second : mp[0].second) << endl;  
    return 0;  
}
```
**Explanation:**
	Цель: Дана числа, нужно найти такое число, котрое различается по четности и вернут его индекс.
	Решение:Создать хеш таблицу, в которой ключ - это четность, а значение - пара количесвто и последняя встречающаяся позиция. Прибавлять на каждом шаге количество и перезаписывать позицию. В конце вернуть позицию единственного отличающегося числа.