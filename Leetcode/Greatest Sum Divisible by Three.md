**Complexity:** Medium
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int maxSumDivThree(vector<int>& nums) {
        sort(nums.begin(), nums.end());

        int sum = 0;
        for (const auto& n : nums) {
            sum += n;
        }

        cout << sum << endl;

        int first = 0, second = 0;
        if (sum % 3 == 1) {
            for (const auto& n : nums) {
                if (n % 3 == 1) {
                    first = n;
                    break;
                }
            }

            int count = 0;
            for (const auto& n : nums) {
                if (n % 3 == 2) {
                    second += n;
                    ++count;
                    if (count == 2) {
                        break;
                    }
                }
            }

            if (count != 2) {
                return sum - first;
            }

            if (first == 0) {
                return sum - second;
            } else if (second == 0) {
                return sum - first;
            }
            
            return max(sum - first, sum - second);
        } else if (sum % 3 == 2) {
            for (const auto& n : nums) {
                if (n % 3 == 2) {
                    first = n;
                    break;
                }
            }

            int count = 0;
            for (const auto& n : nums) {
                if (n % 3 == 1) {
                    second += n;
                    ++count;
                    if (count == 2) {
                        break;
                    }
                }
            }

            if (count != 2) {
                return sum - first;
            }

            if (first == 0) {
                return sum - second;
            } else if (second == 0) {
                return sum - first;
            }

            return max(sum - first, sum - second);
        }

        return sum;
    }
};
```
**Explanation:**
	Цель: Дан массив чисел, нужно найти такую максимальную сумму, что она делится на три без остатка.
	Решение: Можно доказать, что при делении на три может быть в остатке либо один либо 2, следовательно надо искать таие числа, чтобы у них был такой же остаток. Т.е. варианты - остаток суммы равен еденицы, значит надо искать число у коотрого остаток еденица или два числа у которых остаток два и наоборот. Чтобы выбирать минимальные числа(для получения макимальной суммы) сначала отсортировать массив. И для каждого из основных случаев смотреть какой вариант выгоднее, с удаелнем одного числа или двух.