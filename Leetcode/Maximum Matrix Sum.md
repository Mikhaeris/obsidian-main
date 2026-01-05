**Complexity:** Medium
Answer:
	Time Complexity: O(N\*M)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    long long maxMatrixSum(vector<vector<int>>& matrix) {
        long long sum = 0;
        int count_negative = 0;
        int min_pos_num = INT_MAX;

        for (const auto& row : matrix) {
            for (const auto& el : row) {
                sum += abs(el);
                if (el < 0)
                    ++count_negative;
                min_pos_num = min(min_pos_num, abs(el));
            }
        }

        if (count_negative % 2 != 0)
            sum -= min_pos_num * 2;

        return sum;
    }
};
```
**Explanation:**
	Цель: Дана матрица n на n. В ней есть отрицательные элементы. Можно совершаьть только одну операцию - выбрать два числа и умножить их на -1. Нужно получить максимальную сумму матрицы.
	Pешение: Логично что нужно переворачить отрицательные числа. Посчитать общую сумму матрицы, количество отрицательных элментов и минимальное число по модулю. Если количество отрицательных элементов четное - тогда можно перевернуть все элементы и нужно возвратить сумму. Если количество элементов нечетное - нужно выбрать оставить один элемент нечетным или первернуть один положительный элемент(как раз этот минимальный элемент по модулю и ищется). Дальше нужно вычесть этот элеент из сумму, а так как он уже был в сумме, то нужно его вычесть еще раз.