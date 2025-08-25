**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
int main() {  
    string best = "yes";  
    int n = 0; cin >> n;  
  
    for (int i = 0; i < n; ++i) {  
        string s = ""; cin >> s;  
        for (int j = 0; j < s.size(); ++j) {  
            if (s[j] >= 'A' && s[j] <= 'Z') {  
                s[j] += 32;  
            }  
        }  
  
        if (s == best) {  
            cout << "YES" << endl;  
        }  
        else {  
            cout << "NO" << endl;  
        }  
    }  
  
    return 0;  
}
```
**Explanation:**
	Цель: Проверить н аправильность слово "YES".
	Решение: Проверка по нижнему регистру, переделываем верхний в нижний и потом сравниваем.