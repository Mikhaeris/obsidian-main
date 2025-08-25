**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(2N)
Code:
Solution:
```cpp
int main() {  
    int n = 0; cin >> n;  
    string s;  
    for (int i = 0; i < n; ++i) {  
        cin >> s;  
        if (s.size() > 10) {  
            string ans = {s[0]};  
            ans += to_string(s.size()-2);  
            ans += s[s.size()-1];  
            cout << ans << endl;  
        }  
        else {  
            cout << s << endl;  
        }  
    }  
}
```
**Explanation:**
	Цель: Если длина слова больше 10 символов, то его нужно укоротить: взять первый и последний символ, а между ними количество символов в строке минус эти два символа, иначе просто вернут слово.
	Решение: Если слово длинее 10, то формировать новое слово, по условию, иначе возвращать данное слово.