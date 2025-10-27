**Complexity:** Medium
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int numberOfBeams(vector<string>& bank) {
        int count = 0;

        int prev = 0;
        for (int i = 0; i < bank.size(); ++i) {
            int curr = 0;
            for (int j = 0; j < bank[i].length(); ++j) {
                if (bank[i][j] == '1') curr += 1;
            }
            if (curr == 0) continue;

            count += prev * curr;
            prev = curr;
        }

        return count;
    }
};
```
**Explanation:**
	Цель: Дан массив с этажами и устройствами, между ними находятся лазеры. Нужно подсчитать количество лазеров.
	Решение: Количесвто лазеров между двумя этажами равняется их перемножени. Пропускать пустые строчки вернуть количество лазеров.