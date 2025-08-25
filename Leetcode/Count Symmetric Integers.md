**Complexity:** Easy
Answer1:
	Time Complexity: O(N + M)
	Space Complexity: O(N)
Code:
Solution:
```cpp
class Solution {
public:
	int countSymmetricIntegers(int low, int high) {
        string s_num = ""; int count_answers = 0;
        for (int i = low; i <= high; ++i) {
            s_num = to_string(i);
            int summ1 = 0;
            for (int j = 0; j < s_num.size()/2; ++j) {
                summ1 += static_cast<int>(s_num[j]);
            }
            int summ2 = 0;
            for (int j = s_num.size()/2; j < s_num.size(); ++j) {
                summ2 += static_cast<int>(s_num[j]);
            }
  
            if (summ1 == summ2) {
                ++count_answers;
            }
        }
  
        return count_answers;
    }
};
```
**Explanation:**
	Цель: Дан диапозон чисел, нужно посчитать колдичество чисел, в которыз сумма левых цифр равна сумме правых чисел.
	Решение: Проходится по этим числам. Переводить в стринг и считать левую сумму, а потом правую и сравнивать. Если суммы равны, то прибавлять к счетчику.

Answer2:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int countSymmetricIntegers(int low, int high, int ans = 0) {
        for (int i = low; i <= high; i++) {
            if (i < 100 && i % 11 == 0) ans++;
            else if (1000 <= i && i < 10000) {
                int left = i / 1000 + (i % 1000) / 100;
                int right = (i % 100) / 10 + i % 10;
                if (left == right) ans++;
            }
        }
        return ans;
    }
};
```
**Explanation:**
	Цель: Дан диапозон чисел, нужно посчитать колдичество чисел, в которыз сумма левых цифр равна сумме правых чисел.
	Решение: Решение сводится к логике.
	Если число в диапазоне от 1 до 100, то проверять делимость на 11.
	// от 100 до 100 нету чисел удовлетворяющих задаче.
	Если число в 1000 до 10000, то проверять равенство сумм левой и правой половинки.