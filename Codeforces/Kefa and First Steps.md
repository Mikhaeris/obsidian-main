**Complexity:** 900
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
int main() {  
    int n = 0; cin >> n;  
  
    int max_count = 0, curr_count = 0;;  
    int prev = 0;  
  
    for (int i = 0; i < n; ++i) {  
        int a = 0; cin >> a;  
  
        if (a >= prev) {  
            ++curr_count;  
        } else {  
            max_count = max(curr_count, max_count);  
            curr_count = 1;  
        }  
  
        prev = a;  
    }  
  
    max_count = max(curr_count, max_count);  
  
    cout << max_count << endl;  
    return 0;  
}
```
**Explanation:**
	Цель: Даны числа, нужно найти самую длинную неубывающую пословательность.
	Решение: Сохранять предыдущее число и сравнивать.