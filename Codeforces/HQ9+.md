**Complexity:** 800
Answer:
	Time Complexity: O(1)
	Space Complexity: O(1)
Code:
Solution:
```cpp
int main() {  
    unordered_set<char> st = {'H', 'Q', '9'};  
  
    int c;  
    while ((c = getchar()) != '\n') {  
        if (st.find(c) != st.end()) {  
            cout << "YES" << endl;  
            return 0;  
        }  
    }  
  
    cout << "NO" << endl;  
    return 0;  
}
```
**Explanation:**
	Цель: Узнать выведется ли что-то на экран.
	Решение: Считывать каждый символ и смотреть, находится ли он в хеш сете.