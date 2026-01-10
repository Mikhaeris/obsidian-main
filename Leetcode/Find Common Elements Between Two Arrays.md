**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    vector<int> findIntersectionValues(vector<int>& nums1, vector<int>& nums2) {
        unordered_set<int> st1, st2;

        for (const auto& num : nums1) {
            st1.insert(num);
        }

        for (const auto& num : nums2) {
            st2.insert(num);
        }

        int answer1 = 0;
        for (const auto& num : nums1) {
            if (st2.find(num) != st2.end()) {
                ++answer1;
            }
        }

        int answer2 = 0;
        for (const auto& num : nums2) {
            if (st1.find(num) != st1.end()) {
                ++answer2;
            }
        }

        return {answer1, answer2};
    }
};
```
**Explanation:**
	Цель: Даны два массива. Требуется определить сколько элементов содержатся в первом массиве, что он есть и во втором и наоборот и вернуть два этих числа внутри массива.
	Pешение: Сохранить все элементы в двух сетах(в данном случае это хеш таблицы) и потом пройтись по первому массиву ищя эти элементы во втором хеш сете. И так же со вторым массивом.  Вернуть подсчитанное количество совпадений для первого и для второго массива.