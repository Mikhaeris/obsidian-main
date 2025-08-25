**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
int main() {  
    string s, t;  
    cin >> s >> t;  
    if (s.size() != t.size()) {  
        cout << "NO" << endl;  
        return 0;  
    }  
    for (int i = 0, j = t.size()-1; i < s.length() && j >= 0; i++, j--) {  
        if (s[i] != t[j]) {  
            cout << "NO" << endl;  
            return 0;  
        }  
    }  
    cout << "YES" << endl;  
    return 0;  
}
```
**Explanation:**
	Цель: Даны две строки, нужно проверить равны ли они, если вторая перевернута.
	Решение: Два указателя. Сначала проверить рана ли их длина. Потом проходится по указателям. Первое слово сначала, второе с конца.