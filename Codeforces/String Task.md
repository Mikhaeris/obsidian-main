**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp 
int main() {  
    string s = ""; cin >> s;  
  
    unordered_map<char, char> mp = {  
	    {'a', '0'},  
	    {'o', '0'},  
	    {'y', '0'},  
	    {'e', '0'},  
	    {'u', '0'},  
	    {'i', '0'},  
	    {'A', '0'},  
	    {'O', '0'},  
	    {'Y', '0'},  
	    {'E', '0'},  
	    {'U', '0'},  
	    {'I', '0'}  
    };  
  
    string answer = "";  
    for (int i = 0; i < s.size(); ++i) {  
        if (mp.find(s[i]) != mp.end()) {  
            continue;  
        }  
        else if (s[i] >= 'A' && s[i] <= 'Z') {  
            answer.push_back('.');  
            answer.push_back(s[i] + 32);  
        }  
        else {  
            answer.push_back('.');  
            answer.push_back(s[i]);  
        }  
    }  
  
    cout << answer << endl;  
    return 0;  
}
```
**Explanation:**
	Цель: Дана строка. Нужно из этой строки убрать все гласные, согласные привести к нижнему регистру и перед каждой согласной поставить точку.
	Решение: По сути просто выполнить данные условия.