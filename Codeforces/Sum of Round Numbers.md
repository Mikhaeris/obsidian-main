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
  
        string ans = "";  
        int count_numbers = 0, zeroes = 0;  
        do {  
            if (n % 10 != 0) {  
                ans += to_string(n % 10);  
                for (int j = 0; j < zeroes; ++j) {  
                    ans += '0';  
                }  
                ans += ' ';  
                ++count_numbers;  
            }  
            ++zeroes;  
        } while (n/=10);  
        cout << count_numbers << endl;  
        cout << ans << endl;  
    }  
    return 0;  
}
```
**Explanation:**
	Цель: Дано число, нужно вывести сколько в нем круглых слагаемых и вывести их в любом порядке.
	Решение: Делить число на 10, а остаток записывать в строку, так же добавляя нужно количество нулей. Вывести полученную строку.