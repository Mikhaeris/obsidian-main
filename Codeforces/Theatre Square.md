**Complexity:** 1000
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
int main() {  
    long long n = 0, m = 0, a = 0;  
    cin >> n >> m >> a;  
    unsigned long long answer = ((m + a - 1) / a) * ((n + a - 1) / a);  
    cout << answer << endl;  
    return 0;  
}
```
**Explanation:**
	Цель: Есть площадь n на m и плиты a на a. Нужно найти сколько плит нужно для покрытия всей площади, при этом плиты параллельны сторонам площади.
	Решение: Тривиальная задача, в которой нужно посчитать сколько плит нужно для каждой стороны площади и перемножить эти числа.