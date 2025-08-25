**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
int main() {  
    string s = ""; cin >> s;  
    int n = 0;  
    for (int i = 0; i < s.size(); i++) {  
        if (s[i] >= 'A' && s[i] <= 'Z') {  
            n++;  
        }  
    }  
  
    bool to_upper = n > s.size()/2;  
  
    for (int i = 0; i < s.size(); i++) {  
        if (to_upper) {  
            if (s[i] >= 'a' && s[i] <= 'z') {  
                s[i] = s[i] - 32;  
            }  
        }  
        else {  
            if (s[i] >= 'A' && s[i] <= 'Z') {  
                    s[i] = s[i] + 32;  
            }  
        }  
    }  
    cout << s << endl;  
    return 0;  
}
```
**Explanation:**
	Цель: Если в строке больше букв нижнего горегистра, то переделать все буквы в нижний регистр, иначе наоборот.
	Решение: Посчиать сколько букв в ерхнем регистра. В зависимости от этого менять регистр буквы.