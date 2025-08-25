**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
int main() {  
    string s = ""; cin >> s;  
  
    multiset<int> num;  
    for (int i = 0; i < s.size(); i += 2) {  
        num.insert(s[i]);  
    }  
  
    string ans = "";  
    for (const auto& n : num) {  
        ans += n;  
        ans += '+';  
    }  
    ans.pop_back();  
    cout << ans << endl;  
    return 0;  
}
```
**Explanation:**
	Цель: дана математическая последовательность, нужно раставить слагаемые в правильном порядке.
	Решение: Считать все цифры, запихнуть в мультесет и потом мультесет в строку со знакими сложения и вывести.