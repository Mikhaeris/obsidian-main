**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	vector<int> twoSum(vector<int>& numbers, int target) {  
	    int l = 0, r = numbers.size()-1;  
	  
	    while (numbers[l] + numbers[r] != target) {  
	        if (numbers[l] + numbers[r] < target) {  
	            ++l;  
	        } else {  
	            --r;  
	        }  
	    }  
	  
	    return { ++l, ++r };  
	}
};
```
**Explanation:**
	Цель: В отсортировном массиве нужно найти два таких числа, что их сумма равняется искомому числу.
	Решение: С помощью двух указателей идти с начала и с конца массивы, пока два числа не будут равны искомому. Если сумма меньше искомого числа, то двигаем левый индекс вправо, иначе двигаем правый индекс влево. Нужно вернуть индексы (так как нумерация в задаче с одного то прибавть к индексам один).