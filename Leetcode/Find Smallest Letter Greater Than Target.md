**Complexity:** Easy  
Answer1:  
- Time Complexity: O(N)
- Space Complexity: O(1)

Code:  
```cpp
class Solution {
public:
    char nextGreatestLetter(vector<char>& letters, char target) {
        for (int i = 0; i < letters.size(); ++i) {
            if (letters[i] > target) {
                return letters[i];
            }
        }
        return letters[0];
    }
};
```
**Explanation:**
- Цель: Дан массив отсортированных символов и симовол таргет. Нужно найти минимальный символ, который больше таргет.
- Pешение: Линейно проверять каждый символ.

Answer2:  
- Time Complexity: O(log(N))
- Space Complexity: O(1)

Code:  
```cpp
class Solution {
public:
    char nextGreatestLetter(vector<char>& letters, char target) {
        int l = 0, r = letters.size()-1;
        int ans = letters[0];
        while (l <= r) {
            int mid = l + (r - l) / 2;

            if (letters[mid] > target) {
                ans = letters[mid];
                r = mid - 1;
            } else {
                l = mid + 1;
            }
        }
        return ans;
    }
};
```
**Explanation:**
- Цель: Дан массив отсортированных символов и симовол таргет. Нужно найти минимальный символ, который больше таргет.
- Pешение: С помощью бинарного поиска.