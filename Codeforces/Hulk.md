**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
int main() {  
    int n = 0; cin >> n;  
    for (int i = 1; i <= n; i++) {  
  
        if (i % 2) {  
            cout << "I hate ";  
        }  
        else {  
            cout << "I love ";  
        }  
  
        if (i == n) {  
            cout << "it";  
            return 0;  
        }  
          
        cout << "that ";  
    }  
    return 0;  
}
```
**Explanation:**
	Цель: Просто вывести текст по порядку.
	Решение: Просто вывести текст по порядку.