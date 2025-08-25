**Complexity:** Medium
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    double findMaxAverage(vector<int>& nums, int k) {
        double max_summ = 0, current_summ = 0;
  
        for (int i = 0; i < k; ++i) {
            current_summ += nums[i];
        }
        
        max_summ = current_summ;
        for (int i = k; i < nums.size(); ++i) {
	        current_summ -= nums[i - k];
            current_summ += nums[i];
  
            if (max_summ < current_summ) {
                max_summ = current_summ;
            }
            //max_summ = max(max_summ, current_summ);
        }
  
        return max_summ / k;
    }
};
```
**Explanation:**
	Цель: Найти подмассив длинной k, с масксимальным среднем значием.
	Решение: Два указател.
	Посчитать заранее сумму первого окна.
	Потом проходится по элементно и вычитать предыдущий элемент на левом указатели и прибалять правый элемент.
	Если данная сумма больше максимальной, то максимальная равняется данной.
	Вернуть максимальную сумму деленную на количество элементов.