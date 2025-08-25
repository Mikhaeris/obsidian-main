**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
int main() {  
    int n = 0; cin >> n;  
  
    for (int i = 0; i < n; ++i) {  
        int count = 0;  
        vector<int> res(4);  
        for (int j = 0; j < 4; ++j) {  
            cin >> res[j];  
        }  
  
        for (int j = 1; j < 4; ++j) {  
            if (res[0] < res[j]) {  
                ++count;  
            }  
        }  
  
        cout << count << endl;;  
    }  
  
    return 0;  
}
```
**Explanation:**
	Цель: Узнать сколько чисел больше первого.
	Решение: Просто почитать и вывести.