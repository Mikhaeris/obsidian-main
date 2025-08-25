**Complexity:** 1000
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
int main() {  
    int n = 0; cin >> n;  
  
    int sum[3] = {0};  
    for (int i = 0; i < n; ++i) {  
        for (int &n : sum) {  
            int t = 0; cin >> t;  
            n += t;  
        }  
    }  
  
    for (int &n : sum) {  
        if (n != 0) {  
            cout << "NO" << endl;  
            return 0;  
        }  
    }  
  
    cout << "YES" << endl;  
    return 0;  
}
```
**Explanation:**
	Цель: Нужно проверить что сумма сил для всех векторов равнется 0.
	Решение: Массив и там складывать сумму. Проверить и вернуть результат.