**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
int main() {  
    int n = 0; cin >> n;  
  
    int win = 0;  
    for (int i = 0; i < n; ++i) {  
        int m = 0, c = 0;  
        cin >> m >> c;  
  
        if (m > c) {  
            ++win;  
        }  
        else if (m < c) {  
            --win;  
        }  
    }  
  
    if (win > 0) {  
        cout << "Mishka" << endl;  
    }  
    else if (win < 0) {  
        cout << "Chris" << endl;  
    }  
    else {  
        cout << "Friendship is magic!^^" << endl;  
    }  
  
    return 0;  
}
```
**Explanation:**
	Цель: Узнать кто победил.
	Решение: Одна переменная для отслеживания кто победил.