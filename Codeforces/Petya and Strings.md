**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
int main() {  
    string f = "", s = "";  
    cin >> f >> s;  
    for (int i = 0; i < f.size() && i < s.size(); ++i) {  
        if (f[i] >= 'A' && f[i] <= 'Z') {  
            f[i] += 32;  
        }  
        if (s[i] >= 'A' && s[i] <= 'Z') {  
            s[i] += 32;  
        }  
  
        if (f[i] < s[i]) {  
            cout << -1 << endl;  
            return 0;  
        }  
        else if (f[i] > s[i]) {  
            cout << 1 << endl;  
            return 0;  
        }  
    }  
  
    cout << 0 << endl;  
    return 0;  
}
```
**Explanation:**
	Цель: Сравнить две строки лексикографически.
	Решение: Проходится по обоим строкам и сравнивать символы, так же менять регистр на нижний, если требуется