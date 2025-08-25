**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
int main() {  
    int n = 0; cin >> n;  
  
    int c = 0; cin >> c;  
    int count = 0, max = c, min = c;  
    for (int i = 0; i < n-1; ++i) {  
        cin >> c;  
        if (c > max) {  
            max = c;  
            ++count;  
        }  
        else if (c < min) {  
            min = c;  
            ++count;  
        }  
    }  
  
    cout << count << endl;  
    return 0;  
}
```
**Explanation:**
	Цель: Нужно узнать сколько удивительных чисел было. Удивительное число - если число строго больше или меньше текущего максимума или минимума соответсвенно.
	Решение: Просто подстчитать и вывести ответ.