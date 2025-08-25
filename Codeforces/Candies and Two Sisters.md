**Complexity:** 800
Answer:
	Time Complexity: O(1)
	Space Complexity: O(1)
Code:
Solution:
```cpp
int main() {  
    int t = 0; cin >> t;  
    for (int i = 0; i < t; ++i) {  
        int n = 0; cin >> n;  
        cout << ((n % 2) ? n/2 : n/2-1) << endl;  
    }  
    return 0;  
}
```
**Explanation:**
	Цель: Дано число, нужно узнать сколькими способами можно разделить данное число на два, что число a > b.
	Решение: Если число нечетное, то просто делить пополам, если честное, то делить пополам и вычесть один.