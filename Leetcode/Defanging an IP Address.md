**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(2N)
Code:
Solution:
```cpp
class Solution {
public:
    string defangIPaddr(string address) {
        string defanger_address = "";
        for (int i = 0; i < address.size(); ++i) {
            if (address[i] != '.') {
                 defanger_address += address[i];
            }
            else {
                defanger_address += "[.]";
            }
        }
  
        return defanger_address;
    }
};
```
**Explanation:**
	Цель: Дан айпи адресс в виде строки, в нем нужно обернуть все точки в квадратные скобки.
	Решение: Проходится по каждому элементу строки, если это точка, то добавлять в конец новой строки обернутую точки, иначе просто добавлять i-й элемент в новую строку.