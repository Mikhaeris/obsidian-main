**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
class Solution {
public:
    vector<int> intersect(vector<int>& nums1, vector<int>& nums2) {
        unordered_map<int, int> mp;
        for (const auto& n : nums1) {
            mp[n]++;
        }

        vector<int> ans;
        for (const auto& n : nums2) {
            if (mp[n] > 0) {
                mp[n]--;
                ans.push_back(n);
            }
        }

        return ans;
    }
};
```
**Explanation:**
	Цель: Вырнуть массив пересечений двух массивов. Т.е. вернуть массив из встречающихся элементов в обоих массивах.
	Pешение: Сохранить в хеш таблице количество элементов из первого массива. Пройтись по второму и собирать в массив ответа, только встречающиеся элементы.