**Complexity:** Medium
Answer:
	Time Complexity: O(2N)?
	Space Complexity: O(1)
Solution1:
```cpp
class Solution {
public:
    string reverseWords_first(string s) {
	
	    while (s[0] == ' ') {
	        s.erase(s.begin());
	    }
	
	    while (s[s.size() - 1] == ' ') {
	        s.erase(s.end() - 1);
	    }
	
	    s.insert(s.end(), ' ');
	    
	    int right_ptr = 0, right_ptr_st = 0;
	    for (int i = 0; i < s.size(); ++i) {
	        while (s[0] != ' ') {
	            s.insert(s.end() - right_ptr_st, s[0]);
	            s.erase(s.begin());
	            ++right_ptr;
	            ++i;
	        }
	        
	        s.insert(s.end() - right_ptr_st, ' ');
	        
	        while (s[0] == ' ') {
	            s.erase(s.begin());
	        }
	        
	        right_ptr_st = ++right_ptr;
	    }
	    
	    s.erase(s.end() - 1);
	    return s;
	}
};
```
**Explanation:**
	Цель: Перевернуть строку по словам.
	Решение: Переносить буквы спереди назад со смещением влево.

Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Solution2:
```cpp
class Solution {
public:
    string reverseWords(string s) {
        reverse(s.begin(), s.end());
  
        for (int left = 0, right = 1; right < s.size(); ++right) {
            while (s[left] == ' ') {
                s.erase(s.begin()+left);
            }
  
            while (s[right] != ' ' && right < s.size()) {
                ++right;
            }
  
            reverse(s.begin() + left, s.begin() + right);
            left = ++right;
        }
  
        while (s[s.size() - 1] == ' ') {
            s.erase(s.end() - 1);
        }
  
        return s;
    }
};
```
**Explanation:**
	Цель: Перевернуть строку по словам.
	Решение: Перевернуть всю строку и потом переворачить отдельные слова, удаляя лишние пробелы.