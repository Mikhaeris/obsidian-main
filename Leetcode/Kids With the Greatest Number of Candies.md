**Complexity:** Easy
Answer:
	Time Complexity: O(2N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    vector<bool> kidsWithCandies(vector<int>& candies, int extraCandies) {
        int sizeCandies = candies.size();
        int maxCandies = 0;
        for (const auto& candy : candies) {
            if (candy > maxCandies) {
                maxCandies = candy;
            }
        }

        vector<bool> answer(sizeCandies);
        for (int i = 0; i < sizeCandies; ++i) {
            if (candies[i]+extraCandies >= maxCandies) {
                answer[i] = 1;
            }
            else {
                answer[i] = 0;
            }
        }
  
        return answer;
    }
};
```
**Explanation:**
	Цель: Содать булевый массив, в котором для [i] хранится информация о том, будет ли у данного ребенка максимальное кличество конфет после добавления ему дополнительных конфет.
	Решение: Сначала вычислить максимальный элемент.
	Потом пройтись по каждой ребенку и проверять, если после добавления ему дополнительных конфет у него будет больше или равно максимальному количеству конфет, то для i-го ребенка сделать true, иначе false.