**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    vector<int> addToArrayForm(vector<int>& num, int k) {
        reverse(num.begin(), num.end());
        int carry = k;
        for (int i = 0; i < num.size(); ++i) {
            int sum = num[i] + carry;
            num[i] = sum % 10;
            carry = sum / 10;
        }

        while (carry) {
            num.push_back(carry % 10);
            carry = carry / 10;
        }

        reverse(num.begin(), num.end());
        return num;
    }
};
```
**Explanation:**
	Цель: Дан массив из цифр и число нужно их сложить в начальном масиве.
	Решение: Простое складывание чисел как столбиком. Перевернуть изначальный массив и складывать по разряду и переносить больший разряд вперед.