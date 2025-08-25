**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
int main() {  
    int n = 0, m = 0; cin >> n >> m;  
    bool flag = true;  
    for (int i = 0; i < n; i++) {  
        for (int j = 0; j < m; j++) {  
            if (i%2) {  
                if (flag && j == m - 1) {  
                    cout << "#";  
                }  
                else if (!flag && j == 0) {  
                    cout << "#";  
                }  
                else {  
                    cout << '.';  
                }  
            }  
            else {  
                cout << '#';  
            }  
        }  
        if (i%2) {  
            flag = !flag;  
        }  
        cout << endl;  
    }  
    return 0;  
}
```
**Explanation:**
	Цель: Вывести змейку.
	Решение: Просто вывести змейку в консоле