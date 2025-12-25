**Complexity:** Easy
Answer:
	Time Complexity: O((N\*log(N))+K)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    long long maximumHappinessSum(vector<int>& h, int k) {
        ios_base::sync_with_stdio(0), cin.tie(0), cout.tie(0);
        sort(h.begin(), h.end(), [&](const auto a,const auto b){ return a > b; });

        long long sum = 0;
        for (int i = 0; i < k; ++i) {
            sum += max(h[i] - i, 0);
        }

        return sum;
    }
};
```
**Explanation:**
	Цель: Дан массив детей, обозначающий их счастье и число k. Нужно выбрать детей, чтобы их маскаимальное счастье было макимальным возможным, которое можно получить. Когда выбирается один ребенок, у остальных счастье уменьшается на один. Счастье не может уменьшатся меньше нулю.
	Pешение: Логично что нужн брать детей с максимальным счастьем. Нужно отсортировать массив по убыванию. Каждый раз когда брать ребенка вычетать время, которое прошло до его взятия.