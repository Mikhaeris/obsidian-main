**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
   bool canPlaceFlowers(vector<int>& flowerbed, int n) {
        int answer = 0;
        int zeroCount = 0; double tempCountBed = 0; bool flag = 0;
        for (int i = 0; i < flowerbed.size(); ++i) {
            if (flowerbed[i] == 1) {
                if (!flag) {
                    answer += zeroCount / 2;
                    flag = 1;
                    zeroCount = 0;
                }
                else {
                    tempCountBed = static_cast<double>(zeroCount) / 3;
                    answer += tempCountBed >= 1.5 ? tempCountBed + 1 : tempCountBed;
                    zeroCount = 0;
                }
            }
            else {
                ++zeroCount;
            }
        }
  
        if (!flag && zeroCount > 0) {
                tempCountBed = static_cast<double>(zeroCount-2) / 3;
                answer += tempCountBed >= 1.5 ? tempCountBed + 1 : tempCountBed + 2;
                if (flowerbed.size() == 2) {
                    answer = 1;
                }
        }
        else if (zeroCount > 0) {
            answer += zeroCount / 2;
        }
  
        return answer >= n;
    }
};
```
**Explanation:**
	Цель: Расситваить еденички, так что бы между ними был минимум один нолик. И проверить, хвтит ли места для расставновки заданного количества еденеичек.
	Решение: Идея заключается в подсчете нулей и деление на 3, если часть после запятой больше 0,5, то добавлять + 1. (UPD тут просто проверяется что число больше 1,5)
	Если ни разу не было едениц, то вычитать из количества нулей два и проводить ту же операцию.
	Если остался хвост, то добавлять количество нулей деленое на два.
	Вернуть ответ больше или равняется данному количеству едениц.