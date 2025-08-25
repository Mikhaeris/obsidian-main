**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
int main() {  
    int t = 0; cin >> t;  
    for (; t > 0; --t) {  
        int n = 0; cin >> n;  
        int prod = 1; int min_num = INT_MAX; bool flag = false;  
        for (; n > 0; --n) {  
            int num = 0; cin >> num;  
            if (!flag && num == 0) {  
                flag = true;  
            }  
            else {  
                prod *= num;  
                min_num = min(min_num, num);  
            }  
        }  
        if (!flag) {  
            prod /= min_num;  
            prod *= min_num + 1;  
  
        }  
        cout << prod << endl;  
    }  
    return 0;  
}
```
**Explanation:**
	Цель: Дано n чисел нужно найти их проиведение, такое, что при добавление к какому-то числу это произведение становилось максимальным.
	Решение: Загвостска в нулем, просто добавление флага.