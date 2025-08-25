**Complexity:** Medium
Answer1:
	Time Complexity: O(N + M)
	Space Complexity: O(N)
Code:
Solution:
```cpp
class Solution {
public:
	string removeStars(string s) {
		 stack<char> stack_char;
	
		 for (const auto& character : s) {
			 if (character != '*') {
				 stack_char.push(character);
			 }
			 else {
				 stack_char.pop();
			 }
		 }
	
		 string answer;
		 answer.reserve(stack_char.size());
		 while (!stack_char.empty()) {
			 answer += stack_char.top();
			 stack_char.pop();
		 }
	
		 reverse(answer.begin(), answer.end());
		 return answer;
	}
};
```
**Explanation:**
	Цель: В строке содержатся звездочки, нужно удалить сами звездочки и количество символов перед звездочками.
	Решение: Запихивать все в стек, если звездочка, то удалять голову стека, иначе добавлять символ.

Answer2:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    string removeStars(string& s) {
        int index = 0, position = 0;
        for (; index < s.size(); ++index) {
            if (s[index] == '*') {
                --position;
            }
            else {
                s[position] = s[index];
                ++position;
            }
        }
  
        s.resize(position);
        return s;
    }
};
```
**Explanation:**
	Цель: В строке содержатся звездочки, нужно удалить сами звездочки и количество символов перед звездочками.
	Решение: Два указателя, один идет по символам, другой указывает на текущую позицию учитывая количество звездочек.
	Если данный символ звездочка, то двигать указатель со звездочками.
	Иначе элемент на позиции где стоит указатель со звуздочками равняется текущему индексу.
	Суть переписывать уже в данной строке элементы.
	В конце отбросить лишние элементы справа(просто изменив размер на индекс с учетом звездочек) и вернуть данную строку.