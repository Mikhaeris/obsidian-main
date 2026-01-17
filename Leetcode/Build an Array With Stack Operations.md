**Complexity:** Medium
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
```cpp
class Solution {
public:
    vector<string> buildArray(vector<int>& target, int n) {
        vector<string> ans;
        int cur = 1;
        for (int i = 0; i < target.size(); ++i) {
            while (cur < target[i]) {
                ans.push_back("Push");
                ans.push_back("Pop");
                ++cur;
            }
            ans.push_back("Push");
            ++cur;
        }
        return ans;
    }
};
```
**Explanation:**
	Цель: Дан массив, нужно получить ег с помощью операций стека.
	Pешение: Проходится по всему массиву и отслуживать текущее число. Если текущее число меньше текущего в массиве доавлять число и вынимать число. В конце прибавить текущее число. Вернуть массив операций.