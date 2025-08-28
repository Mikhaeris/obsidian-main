**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
class MyQueue {
public:
	MyQueue() {}
	void push(int x) {
	write.push(x);
	}
	int pop() {
	peek();
	  
	int ans = read.top();
	read.pop();
	  
	return ans;
	}
	int peek() {
	if (read.empty()) {
	while (!write.empty()) {
	read.push(write.top());
	write.pop();
	}
	}
	return read.top();
	}
	bool empty() {
	return write.empty() && read.empty();
	}
	  
private:
	stack<int> write, read;
};
```
**Explanation:**
	Цель: Дана строка, нужно вернуть индекс первого элемента, который не повторяется в массиве.
	Решение: Проходится первый раз по строке и прибавлять количество повторений для этой буквы в массиве из 26 элементов(т.е. индекс в этом массиве указывает на букву в алфавите, а значение индекса - количество повторений это буквы в этом слове). Дальше пройтись второй раз по этой строке и если в массиве букв эта буква встречается один раз то вернуть текущий индекс. Иначе сообщить, что не повторяющихся элементов нет.