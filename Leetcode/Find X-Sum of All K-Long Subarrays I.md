**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(2N)
Code:
Solution:
```cpp
class Solution {
public:
    vector<int> findXSum(vector<int>& nums, int& k, int& x) {
        unordered_map<int, int> mp;
        for (int i = 0; i < k; ++i) {
            ++mp[nums[i]];
        }

        vector<int> ans;
        ans.push_back(check_map(mp, x));
        for (int l = 0, r = k; r < nums.size(); ++l, ++r) {
            --mp[nums[l]];
            ++mp[nums[r]];
            ans.push_back(check_map(mp, x));
        }

        return ans;
    }
private:

    int check_map(const unordered_map<int, int>& mp, const int& x) {
        vector<pair<int, int>> vec;
        for (const auto& pr : mp) {
            vec.push_back(pr);
        }

        auto comp = [](auto& a, auto& b) {
            if (a.second < b.second) return false;
            if (a.second > b.second) return true;
            return a.first > b.first;
        };
        sort(vec.begin(), vec.end(), comp);

        int sum = 0;
        for (int i = 0; i < x && i < vec.size(); ++i) {
            sum += vec[i].first * vec[i].second;
        }

        return sum;
    }
};
```
**Explanation:**
	Цель: Дан массив чисел, длина подмассива и количество элементов которые можно брать. Нужно в каждом подмассиве данной длины, взять такие первые элементов, которые повторяются чаще всего и вернуть их сумму. Вернуть массив из всех таких сумм подмассивов.
	Решение: Собирать первые k  элементов и их количество повторений в хэш таблицу. Дальше перекинуть в массив и отсортировать его, взяв элменты из условия. Вернуть сумму нужных элментов. Повторять для все подмассивов длинной k. Вернуть массив из всех сумм.