**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
int main() {  
    long long n = 0; cin >> n;  
    long long count_lucky = 0;  
    while (n/10) {  
        if (n % 10 == 4 || n % 10 == 7) {  
            count_lucky++;  
        }  
        n = n / 10;  
    }  
  
    if (n % 4 == 0 || n % 7 == 0) {  
        count_lucky++;  
    }  
    if (count_lucky == 4 || count_lucky == 7) {  
        cout << "YES" << endl;  
    }  
    else {  
        cout << "NO" << endl;  
    }  
    return 0;  
}
```
**Explanation:**
	Цель: Cчастливое число, если все его числа 4 и 7. Почти счастливое - если количество счастливых чисел 4 или 7.
	Решение: Проверять остаток в цикле, потом проверить последнее число и вывести ответ.