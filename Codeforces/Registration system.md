**Complexity:** 1300
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
int main() {  
    unordered_map<string, int> mp;  
  
    int n = 0; cin >> n;  
    for (int i = 0; i < n; ++i) {  
        string s = ""; cin >> s;  
        if (mp.find(s) == mp.end()) {  
            ++mp[s];  
            cout << "OK" << endl;  
        }  
        else {  
            ++mp[s + to_string(mp[s])];  
            cout << s + to_string(mp[s]) << endl;  
            ++mp[s];  
        }  
    }  
  
    return 0;  
}
```
**Explanation:**
	Цель: Система регистрации пользователей, если такой пользователь уже есть, то выдать ему введенное имя плюс цифру, которая еще не занята.
	Решение: Создать хеш таблицу [[Hash table]], где каждому имени соответсвует следующая доступная цифра.
	Если такой пользователь уже есть, то извлекать из его введенного имени дотупную цифру и присваивать ему.