**Complexity:** Easy
Answer1:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	vector<int> findDisappearedNumbers(vector<int>& nums) {
		for (int i = 0; i < nums.size();) {
			if (nums[i] != nums[nums[i]-1]) {
				swap(nums[i],nums[nums[i]-1]);
			}
			else {
				++i;
			}
		}
		  
		vector<int> ans;
		for (int i = 0; i < nums.size(); ++i) {
			if (nums[i] != i+1) {
				ans.push_back(i+1);
			}
		}
		  
		return ans;
	}
};
```
**Explanation:**
	Цель: Дан массив размером n, нужно вернуть подмассив, таких элементов, которых нет в данном массие. Элементы не превышают n.
	Решение: Каждый элемент ставить в свою позицию. В конечно итоге элементы, которые не стоят на своей позиции будет стоять на тех индексах+1, что этих элементов нет и этот подмассив и будет ответом.

Answer2:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	vector<int> findDisappearedNumbers(vector<int>& nums) {
		for (auto& n : nums) {
			nums[abs(n)-1] = -abs(nums[abs(n)-1]);
		}
		  
		vector<int> ans;
		for (int i = 0; i < nums.size(); ++i) {
			if (nums[i] > 0) {
				ans.push_back(i+1);
			}
		}
		  
		return move(ans);
	}
};
```
**Explanation:**
	Цель: Дан массив размером n, нужно вернуть подмассив, таких элементов, которых нет в данном массие. Элементы не превышают n.
	Решение: Помечать присутсвие элемента в массиве изменением знака на отрицаительный для элемента в этой позиции. Элементы, которые остались с положительным знаком, занимают позиции отсутствующих элементов.
