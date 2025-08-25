**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
int main() {  
    int arr[4];  
    for (auto& n : arr) {  
        cin >> n;  
    }  
  
    long long ans = 0;  
    int c = getchar();  
    while ((c = getchar()) != '\n') {  
        if (c >= '1' && c <= '4') {  
            ans += arr[c - '1'];  
        }  
    }  
  
    cout << ans << endl;  
}
```
**Explanation:**
	Цель: В первоу строке даны 4 числа - стимость нажатия на определенный квадрат, во второй строке дана последовательность. Посчитать сколько будет стоить.
	Решение: Сделать то что сказано. Интересный момент, только в обработке значений сразу, без хранения второй строки.