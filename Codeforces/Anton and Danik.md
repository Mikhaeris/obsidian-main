**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
int main() {  
    int n = 0; cin >> n;  
  
    int an = 0;  
    for (int i = 0; i < n; i++) {  
        char c; cin >> c;  
        if (c == 'A') an++;  
    }  
  
    if (n == an || n - an < n/2) {  
        cout << "Anton" << endl;  
    }  
    else if (n - an > n/2) {  
        cout << "Danik" << endl;  
    }  
    else {  
        cout << "Friendship" << endl;  
    }  
  
    return 0;  
}
```
**Explanation:**
	Цель: Дано количество партий и строка кто победил. Вывести кто победил.
	Решение: Считать количество букв А и вывести в зависимости от этого результат.