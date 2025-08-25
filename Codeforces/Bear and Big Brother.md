**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
int main() {  
    int a = 0, b = 0;  
    cin >> a >> b;  
    int count_years = 0;  
    while (a <= b) {  
        count_years++;  
        a *= 3;  
        b *= 2;  
    }  
    cout << count_years << endl;  
    return 0;  
}
```
**Explanation:**
	Цель: Два числа, первое увеличивается в три раза каждый ход, второе в два раза. Узнать через сколько первое число будет строго больше второго.
	Решение: В цикле считать и вывести ответ.