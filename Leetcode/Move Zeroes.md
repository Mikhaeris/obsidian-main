**Complexity:** Easy
Answer1:
	Time Complexity: O(N)???
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    void moveZeroes1(vector<int>& nums) {
	    int left_ptr = nums.size() - 1;
	    for (int i = 0; i < left_ptr+1; ++i) {
	        if (nums[i] == 0) {
	            for (int j = i; j < left_ptr; ++j) {
	                swap(nums[j], nums[j+1]);
	            }
	            --left_ptr;
	            --i;
	        }
	    }
	}
};
```
**Explanation:**
	Цель: Нужно переместить все нули в конец.
	Решение: Решение в тупую - свапать нули вправо до конца.
	
Answer2:
	Time Complexity: O(N+M)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    void moveZeroes(vector<int>& nums) {
	    int left_ptr = 0;
	    for (int i = 0; i < nums.size(); ++i) {
	        if (nums[i] != 0) {
	            nums[left_ptr] = nums[i];
	            ++left_ptr;
	        }
	    }
	
	    for (int i = left_ptr; i < nums.size(); ++i) {
	        nums[i] = 0;
	    }
	}
};
```
**Explanation:**
	Цель: Нужно переместить все нули в конец.
	Решение: По двум указателям проходится по массиву. Один указывает на текущую позицию без нуля, второй на текущий индекс.
	Если данный элемент не равен нулю, то элемент на левом индексе приравнивается к этому.
	В конце добавляются нули.

Answer3:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    void moveZeroes(vector<int>& nums) {
	    int left = 0;
	    for (int right = 0; right < nums.size(); ++right) {
	        if (nums[right] != 0) {
	            swap(nums[left], nums[right]);
	            ++left;
	        }
	    }
	}
};
```
**Explanation:**
	Цель: Нужно переместить все нули в конец.
	Решение: Два указателя. Проходится по каждому элементу.
	Если правый указывает на не ноль, то менять местами левый и правый.