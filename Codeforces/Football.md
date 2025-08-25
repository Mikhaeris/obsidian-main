**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
int main() {  
    string s = ""; cin >> s;  
    int count = 1;  
    for (int i = 1; i < s.size(); ++i) {  
        if (s[i] == s[i-1])  
            ++count;  
        else  
            count = 1;  
  
        if (count == 7) {  
            cout << "YES" << endl;  
            return 0;  
        }  
    }  
  
    cout << "NO" << endl;  
    return 0;  
}
```
**Explanation:**
	Цель: Если есть последовательность из 7 цфир подряд, то вывести YES, иначе NO.
	Решение: Один счетчик и всеж