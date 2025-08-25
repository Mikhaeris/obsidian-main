**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
int main() {  
    int t = 0; cin >> t;  
    for (int i = 0; i < t; ++i) {  
        int n = 0; cin >> n;  
        cout << (n % 10) + (n / 10)<< endl;  
    }  
    return 0;  
}
```
**Explanation:**
	Цель: Узнать сумму цифр двухзначного числа.
	Решение: Остаток деления на десять плюс разделить число на десять.