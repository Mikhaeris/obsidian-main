**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    double average(vector<int>& salary) {
        int n = salary.size();
        double sum = 0;
        int max_s = salary[0], min_s = salary[0];
        for (int i = 0; i < n; ++i) {
            sum += salary[i];
            max_s = max(max_s, salary[i]);
            min_s = min(min_s, salary[i]);
        }

        sum -= max_s + min_s;

        return sum / (n - 2);
    }
};
```
**Explanation:**
	Цель: Дан массив зарплат. Требуется найти среднюю зарплату, не считая максимальную и минимальную.
	Pешение: Собирать сумму зарплат и параллельно искать минимальное и максимальное число, вычесть их из сумму и найти среднее.