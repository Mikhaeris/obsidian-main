**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
int main() {  
    string ans = "abc";  
    int n = 0; cin >> n;  
    for (int i = 0; i < n; i++) {  
        string s = ""; cin >> s;  
        int count = 0;  
        for (int j = 0; j < s.length(); j++) {  
            if (ans[j] != s[j]) {  
                count++;  
            }  
        }  
        if (count <= 2) {  
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
	Цель: Можно ли сменой местами двух символов привести строку к виду "abc"?
	Решение: Посчитать разницу между идеальной строкой и данной и вывести ответ, если колчеиство несовпадающих букв равно 2 или меньше(скорее просто 2), то да иначе нет.