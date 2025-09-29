**Complexity:** Easy
Answer:
	Time Complexity: O(N!)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int countPrefixSuffixPairs(vector<string>& words) {
        int count = 0;
        for (int i = 0; i < words.size(); ++i) {
            for (int j = i + 1; j < words.size(); ++j) {
                count += isPrefixAndSuffix(words[i], words[j]);
            }
        }
        return count;
    }
    
private:
    bool isPrefixAndSuffix(string& str1, string& str2) {
        if (str1.length() > str2.length()) {
            return false;
        }

        for (int i = 0; i < str1.length(); ++i) {
            if (str1[i] != str2[i]) {
                return false;
            }
        }

        int j = str2.length() - 1;
        for (int i = str1.length() - 1; i >= 0; --i) {
            if (str1[i] != str2[j]) {
                return false;
            }
            --j;
        }

        return true;
    }
};
```
**Explanation:**
	Цель: Нужно найти количество пар, в котрых строка str1 является префиксом и суффиксом строки str2.
	Pешение: Проходится по всем варинтам и сравнивать строки.