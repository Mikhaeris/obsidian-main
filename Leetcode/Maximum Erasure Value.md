**Complexity:** Easy
Answer1:
	Time Complexity: O(N)
	Space Complexity: O(N)?
Code:
Solution:
```cpp
class Solution {
public:
	int maximumUniqueSubarray(vector<int>& nums) {
		unordered_set<int> st;
		
		int curr_sum = 0, max_sum = 0;
		for (int l = 0, r = 0; r < nums.size();) {
			if (st.find(nums[r]) == st.end()) {
				st.insert(nums[r]);
				curr_sum += nums[r];
				++r;
			}
			else {
				st.erase(nums[l]);
				curr_sum -= nums[l];
				++l;
			}
			  
			max_sum = max(max_sum, curr_sum);
		}
		  
		return max_sum;
	}
};
```
**Explanation:**
	Цель: Найти макимальную сумму, такого подмассива, в котором все элементы уникальны.
	Решение: Создать [[Hash set]] и с помощью [[Sliding window]] пройтись по всему вектору.
	Если встречается новый элемент, то добавлять его в схэш сет и прибавлять текущую сумму и сдвинуть правый указатель вправо.
	Если элемент уже имеется, то сначала удалить его из хэш сета, потом вычесть из текущей суммы и сдвинуть левый указатель вправо.
	Максимальный элемент равняется максимум из макс эемента и текущего элемента.

Answer2:
	Time Complexity: O(N)
	Space Complexity: O(N)?
Code:
Solution:
```cpp
class Solution {
public:
	int maximumUniqueSubarray(vector<int>& nums) {  
	    unordered_map<int, int> mp;  
	  
	    int curr_sum = 0, max_sum = 0;  
	    for (int l = 0, r = 0; r < nums.size(); ++r) {  
	        ++mp[nums[r]];  
	        curr_sum += nums[r];  
	  
	        while (mp[nums[r]] > 1) {  
	            curr_sum -= nums[l];  
	            --mp[nums[l]];  
	            ++l;  
	        }  
	  
	        max_sum = max(max_sum, curr_sum);  
	    }  
	  
	    return max_sum;  
	}
};
```
**Explanation:**
	Цель: Найти макимальную сумму, такого подмассива, в котором все элементы уникальны.
	Решение: Создать [[Hash table]] и с помощью [[Sliding window]] пройтись по всему вектору.
	Решение аналогично с предыдущим, только теперь элементы не удаляются, а сохраняется в хеш таблице количество их повторов, чтобы повторов всегда было один.

Answer3:
	Time Complexity: O(N)
	Space Complexity: O(N)?
Code:
Solution:
```cpp
class Solution {
public:
	int maximumUniqueSubarray(vector<int>& nums) {
		vector<int> vec(10000, 0);
		  
		int curr_sum = 0, max_sum = 0;
		for (int l = 0, r = 0; r < nums.size(); ++r) {
			++vec[nums[r]-1];
			curr_sum += nums[r];
			  
			while (vec[nums[r]-1] > 1) {
				curr_sum -= nums[l];
				--vec[nums[l]-1];
				++l;
			}
			  
			max_sum = max(max_sum, curr_sum);
		}
		  
		return max_sum;
	}
};
```
**Explanation:**
	Цель: Найти макимальную сумму, такого подмассива, в котором все элементы уникальны.
	Решение: Создать вектор для 10000 элементов, где каждому индексу соответсвует элемент, а значение - количество повторений, и с помощью [[Sliding window]] пройтись по всему вектору.
	Решение аналогично с предыдущим, только теперь элементы не удаляются, а сохраняется в векторе количество их повторов, чтобы повторов всегда было один.