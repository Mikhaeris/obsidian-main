**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
```cpp
class Solution {
public:
    int minimumPairRemoval(vector<int>& nums) {
        int count = 0;
        while (!check_arr(nums)) {
            auto inf = get_min_pair_idx(nums);
            nums[inf.first] = inf.second;
            nums.erase(nums.begin() + inf.first + 1);
            ++count;
        }
        return count;
    }

    bool check_arr(vector<int>& nums) {
        for (int i = 0; i < nums.size()-1; ++i) {
            if (nums[i] > nums[i+1]) {
                return false;
            }
        }
        return true;
    }

    pair<int, int> get_min_pair_idx(vector<int>& nums) {
        int cur_min = nums[0] + nums[1], cur_idx = 0;
        for (int i = 0; i < nums.size()-1; ++i) {
            int cur = nums[i] + nums[i+1];
            if (cur_min > cur) {
                cur_min = cur;
                cur_idx = i;
            }
        }
        return {cur_idx, cur_min};
    }
};
```
**Explanation:**
	Цель: Дан массив. Требуется узнать сколько раз требуется обеденить минимальную пару чисел, чтобы массив стал не убывающим.
	Pешение: Забавно, что оптимизированного решения нет и нужно просто сделать сказанное в условии. На каждом шаге проверять массив, если массив еще не правильный, то искать минималььную пару чисел, и объеденять их. Вернуть количество требуемых операций.