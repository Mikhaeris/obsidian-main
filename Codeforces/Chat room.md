**Complexity:** 1000
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
int main() {  
    array<char, 5> character = {'h', 'e', 'l', 'l', 'o'};  
    array<int, 5> count = {0, 0, 0, 0, 0};  
  
    string s = ""; cin >> s;  
    for (int i = 0, j = 0; i < s.size() && j < 5; ++i) {  
        if (s[i] == character[j]) {  
            ++count[j];  
            ++j;  
        }  
    }  
  
    for (const auto& n : count) {  
        if (n == 0) {  
            cout << "NO" << endl;  
            return 0;  
        }  
    }  
  
    cout << "YES" << endl;  
    return 0;  
}
```
**Explanation:**
	Цель: Нужно проверить, содержится ли слово hello в заданной строке, так чтобы все символы стояли в правильном порядке.
	Решение: Два массива, один содержит слово hello, второй собирает символы по порядку.
	Если в слове не встречается подряд символы, то вернуть нет иначе да.