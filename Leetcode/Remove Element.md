**Complexity:** Easy
Answer1:
	Time Complexity: O(N^ln(nums.count(val)))?
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	int removeElement(vector<int>& nums, int val) {
		int count = 0;
		for (int i = 0; i < nums.size(); i++) {
			if (nums[i] == val) {
				nums.erase(nums.begin() + i);
				i--;
				count++;
			}
		}

		return nums.size();
	}
};
```
**Explanation:**
	Цель: Удалить все вхождения val в массив и вернуть количество элементов без val.
	Решение: Просто удалять из вектора все жлементы равные val.

Answer2:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	int removeElement(vector<int>& nums, int val) {  
	    int k = 0;
	  
	    for (int i = 0; i < nums.size(); ++i) {  
	        if (nums[i] != val) {  
	            nums[k] = nums[i]; 
	            ++k;  
	        }  
	    }  
	  
	    return k;  
	}
};
```
**Explanation:**
	Цель: Удалить все вхождения val в массив и вернуть количество элементов без val.
	Решение: Первый индекс идет по всем элементам в массиве, второй только по элементам не являющимися val. Если элементы не равен val, значит нужно заменять отстающий индекс на текуший индекс.
	Как бы получается что один индекс бежит в каждом шаге увеличиваясь на один, а второй как бы не ходит по val вообще.