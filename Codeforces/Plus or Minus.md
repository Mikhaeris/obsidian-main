**Complexity:** 1000
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
int main() {  
    int n = 0; cin >> n;  
    for (; n > 0; --n) {  
        int a = 0, b = 0, c = 0;  
        cin >> a >> b >> c;  
  
        if ((a + b) == c) {  
            cout << '+' << endl;  
        }  
        else {  
            cout << '-' << endl;  
        }  
    }  
    return 0;  
}
```
**Explanation:**
	Цель: Дано три числа, если a + b = c, вывести +, иначе -.
	Решение: Просто выполнить проверку и вывести нужный знак.