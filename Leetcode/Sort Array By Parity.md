**Complexity:** Medium
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	vector<int> sortArrayByParity(vector<int>& nums) {
		int l = 0, r = nums.size()-1;
		while (l < r) {
			if ((nums[l] & 1) == 0) {
				++l;
			}
			else if ((nums[r] & 1) == 1) {
				--r;
			}
			else {
				swap(nums[l], nums[r]);
			}
		}
		return move(nums);
	}
};
```
**Explanation:**
	Цель: Честные элементы нужно переместить вправо, а нечетные влево.
	Решение: Два указателя. Сдвигаем левый, пока на его месте не окажется нечетное число, так же сдвигаем правый, пока не его месте не окажется четное число, потом меняем эти элементы местами.