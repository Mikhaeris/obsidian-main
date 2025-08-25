**Complexity:** Medium
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	long long zeroFilledSubarray(vector<int>& nums) {
		long long ans = 0, count = 0;
		for (int i = 0; i < nums.size(); ++i) {
			if (nums[i] == 0) {
				++count;
			} else {
				ans += (count * (count + 1)) / 2;
				count = 0;
			}
		}
		  
		ans += (count * (count + 1)) / 2;
		  
		return ans;
	}
};
```
**Explanation:**
	Цель: посчитать количество подмассивов состоящих только из нулей.
	Решение: Считать количество нулей, как только нули закончиваются по формуле считать количество подмассивов. После цикла тоже посчитать количество подмассивово и добавить в ответ(так как в конце могут содержаться нули и они не будут подсчитаны.)
	P.S. формула количества подмассивов в массиве в математике - формула суммы арифметической прогрессии. S=(n/2)\*(a1+an) или по другому (n\*(n+1))/2 - для этого случая.