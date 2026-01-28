**Complexity:** Easy  
Answer:  
- Time Complexity: O(N)
- Space Complexity: O(N)

Code:  
```cpp
class Solution {
public:
    vector<int> resultArray(vector<int> nums) {
        vector<int> v1;
        vector<int> v2;

        v1.push_back(nums[0]);
        v2.push_back(nums[1]);
        for (int i = 2; i < nums.size(); ++i) {
            if (v1[v1.size()-1] > v2[v2.size()-1]) {
                v1.push_back(nums[i]);
            } else {
                v2.push_back(nums[i]);
            }
        }

        v1.insert(v1.end(), v2.begin(), v2.end());
        return v1;
    }
};
```
**Explanation:**
- Цель: Дан массив, из него нужно сформировать два массива по правилу. Первые два элемента распределяются в свои массивы. Следующий элемент вставляется в массив у которого последнее вставленное число больше.
- Pешение: Сформировать два массива. Заполнять их по правилу. В конце объеденить в один.