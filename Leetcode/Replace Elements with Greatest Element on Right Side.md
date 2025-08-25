**Complexity:** Medium
Answer:
	Time Complexity: ~O(N\*N^2)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	vector<int> replaceElements(vector<int>& arr) {
		int size = arr.size();
		  
		int max_prev = -1;
		for (int i = size-1; i >= 0; --i) {
			if (arr[i] > max_prev) {
				int temp = max_prev;
				max_prev = arr[i];
				arr[i] = temp;
				continue;
			}
			  
			arr[i] = max_prev;
		}
		  
		return arr;
	}
};
```
**Explanation:**
	Цель: Каждый элемент в массиве заменить наибольшим справа от него.
	Решение: Идти с конца массива, заменяя все элементы текущем макимальным.