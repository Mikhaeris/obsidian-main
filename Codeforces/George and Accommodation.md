**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
int main() {  
    int n = 0; cin >> n;  
    int ans = 0;  
    for (int i = 0; i < n; i++) {  
        int c = 0, m = 0;  
        cin >> c; cin >> m;  
        if (m-c >= 2) {  
            ans++;  
        }  
    }  
    cout << ans << endl;  
}
```
**Explanation:**
	Цель: Посчитать количество пар, в которых m - c >= 2.
	Решение: Посчитаь и вывести ответ.