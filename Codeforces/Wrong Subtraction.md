**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
int main() {  
    long long n = 0, k = 0; cin >> n >> k;  
    for (int i = 0; i < k; i++) {  
        n = n % 10 == 0 ? n / 10 : n - 1;  
    }  
    cout << n << endl;  
    return 0;  
}
```
**Explanation:**
	Цель: Если в конце числа ноль, то делить на делять, иначе убавить еденицу.
	Решение: Если остаток от десяти ноль, то делать на десять, иначе вычесть еденицу, повторить k раз.