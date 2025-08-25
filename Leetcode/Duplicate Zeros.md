**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	void duplicateZeros(vector<int>& arr) {  
	    int count_zeroes = 0, size = arr.size();  
	    for (const auto& num : arr) {  
	        if (num == 0) {  
	            ++count_zeroes;  
	        }  
	    }  
	  
	    int l = size - 1, r = size - 1 + count_zeroes;  
	    for ( ; l < r; --l, --r) {  
	        if (r < size) {  
	            arr[r] = arr[l];  
	        }  
	        if (arr[l] == 0) {  
	            --r;  
	            if (r < size) {  
	                arr[r] = 0;  
	            }  
	        }  
	    }  
	}
};
```
**Explanation:**
	Цель: Дан массив, нужно дублировать нули, а все остальные элементы сдвинуть вправо. Без дополнительного пространства.
	Решение: Посчитать количество нулей. Два указателя, один левый считывает, другой правый пишут(только если в границах массива).
	Просиходит как бы симуляция записывания всех чисел в несуществующий массив,а индексы которые входят - записываются.