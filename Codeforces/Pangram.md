**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
int main() {  
    int n = 0; cin >> n;  
    string s = ""; cin >> s;  
    vector<int> vec(26, 0);  
    for (int i = 0; i < s.length(); i++) {  
        if (s[i] >= 'A' && s[i] <= 'Z') {  
            vec[s[i] - 'A'] = 1;  
        }  
        else {  
            vec[s[i] - 'a'] = 1;  
        }  
    }  
  
    for (const auto& c : vec) {  
        if (c == 0) {  
            cout << "NO" << endl;  
            return 0;  
        }  
    }  
    cout << "YES" << endl;  
    return 0;  
}
```
**Explanation:**
	Цель: Узнать, является ли данное слово панграммой.
	Решение: Заполнить массив из 26 символов, где каждый элемент обозначает букву в алфавите по порядку, если буква встречалась, то 1, если нет там будет 0.
	Пройтись по заполненному массиву в поичках нуля, если есть ноль, то это не панграмма. Если нолей нет, значит это панграмма.