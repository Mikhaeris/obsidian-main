**Complexity:** Medium
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
```cpp
class Solution {
public:
    int evalRPN(vector<string>& tokens) {
        stack<int> st;
        int num1, num2;
        for (const auto& str : tokens) {
            if (isdigit(str[str.size()-1])) {
                st.push(stoi(str));
            } else {
                num1 = st.top();
                st.pop();
                num2 = st.top();
                st.pop();
                switch (str[0]) {
                    case '+':
                        st.push(num1 + num2);
                        break;
                    case '-':
                        st.push(num2 - num1);
                        break;
                    case '*':
                        st.push(num1 * num2);
                        break;
                    case '/':
                        st.push(num2 / num1);
                        break;
                    default:
                        return 0;
                }
            }
        }
        return st.top();
    }
};
```
**Explanation:**
	Цель: Дан массив из строк в виде обратной польсокй записи. Требуется узнать ответ.
	Pешение: Простая реализация калькулятора для обратной польской записи. Если последний символ цифра, значит строку переделать в число и запистаь в стек, иначе провести нужную арифметическую операцию.