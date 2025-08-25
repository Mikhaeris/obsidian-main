**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	vector<string> divideString(string s, int k, char fill) {  
	    vector<string> result; int off = 0;  
	    for (int i = 0; i < s.length(); i++) {  
	        string temp_s = "";  
	        for (int j = 0; i < s.length() && j < k; j++, i++) {  
	            temp_s += s[i];  
	        }  
	        result.push_back(temp_s);  
	        i--;  
	    }  
	  
	    if (result[result.size()-1].size() != k) {  
	        while (result[result.size()-1].size() != k) {  
	            result[result.size()-1].push_back(fill);  
	        }  
	    }  
	  
	    return result;  
	}
};
```
**Explanation:**
	Цель: Дано слово, его нужно разделить на слова размерностью k, в последней последовательнсоти, если надо, то добавить в конце fill.
	Решение: Проходится и заполнять слово, потом пихать его в вектор. В конце проверить последнюю последовательность и если надо добавить fill.