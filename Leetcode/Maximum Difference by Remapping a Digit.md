**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int minMaxDifference(int num) {
        string s_num = to_string(num);
        char ch = '0';
        for (int i = 0; i < s_num.size(); ++i) {
            if (s_num[i] != '9') {
                ch = s_num[i];
                break;
            }
        }
  
        string max_num = s_num;
        for (int i = 0; i < max_num.size(); ++i) {
            if (max_num[i] == ch) {
                max_num[i] = '9';
            }
        }
        ch = s_num[0];
        string min_num = s_num;
        for (int i = 0; i < min_num.size(); ++i) {
            if (min_num[i] == ch) {
                min_num[i] = '0';
            }
        }
  
        return stoi(max_num) - stoi(min_num);
    }
};
```
**Explanation:**
	Цель: Дано число и нужно найти разницу между максимальным и минимальным возмодным числом, после преобразование: нужно заменить одно число другим от 0 до 10.
	Решение: Чтобы получить максимальное число, нужно преобразовать первую цифру не равную 9 в 9 и последуюзие цифры, равные этой. Так же сделать для минимального заменить первую цифру на 0 и остальные такие цифры.
	Преобразовать и вычесть из максимального полученного минимальное полученное.