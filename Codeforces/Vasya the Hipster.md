**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
int main() {  
    int a = 0, b = 0; cin >> a >> b;  
    if (a > b) {  
        int tmp = a;  
        a = b;  
        b = tmp;  
    }  
  
    cout << a << " " << (b-a) / 2 << endl;  
    return 0;  
}
```
**Explanation:**
	Цель: Вывести минимальное число и потом сколько раз можно разделить число на 2 (перед этим вычесть из этого числа минимальное).
	Решение: Просто выполнить действия.