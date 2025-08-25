**Complexity:** Medium
Answer1:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	vector<int> asteroidCollision(vector<int>& asteroids) {
        for (int i = 0; i < asteroids.size(); ++i) {
            if (asteroids[i] < 0) {
                while (true && i > 0) {
                    if (asteroids[i-1] > 0) {
                        if (asteroids[i-1] > abs(asteroids[i])) {
                            asteroids.erase(asteroids.begin()+i);
                            --i;
                            break;
                        }
                        else if (asteroids[i-1] == abs(asteroids[i])) {
                            asteroids.erase(asteroids.begin()+i-1);
                            asteroids.erase(asteroids.begin()+i-1);
                            i -= 2;
                            break;
                        }
                        else {
                            asteroids.erase(asteroids.begin()+i-1);
                            i -= 2;
                            break;
                        }
                    }
                    else {
                        break;
                    }
                }
            }
        }
  
        return asteroids;
    }
};
```
**Explanation:**
	Цель: Есть массив астероидов, число - это вес, а знкак - направление. Если астероиды летят на встречу друг другу, то если один меньше - он уничтожается, если они равны, то уничтодаются оба.
	Решение: Проходится по каждому и смотерть, если он меньше нуля, то смотреть что будет просиходить в левыми от него, если знаки равны, то переходить к следующему астероиду. Если другой летит на встречу, то смотреть массу и либо удалять один, либо удалять оба.
	Примечание: Решение бьется по памяти на 100%, но очень плохо по скорости.

Answer2:
	Time Complexity: O(N+N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
class Solution {
public:
    vector<int> asteroidCollision(vector<int>& asteroids) {
        stack<int> st_asteroids;
  
        for (int& asteroid : asteroids) {
            if (asteroid > 0) {
                st_asteroids.push(asteroid);
            }
            else {
                while (!st_asteroids.empty() && st_asteroids.top() > 0 && st_asteroids.top() < -asteroid) {
                    st_asteroids.pop();
                }
  
                if (st_asteroids.empty() || st_asteroids.top() < 0) {
                    st_asteroids.push(asteroid);
                }
  
                if (!st_asteroids.empty() && st_asteroids.top() == -asteroid) {
                    st_asteroids.pop();
                }
            }
        }
  
        asteroids.resize(st_asteroids.size());
  
        for (int i = asteroids.size() - 1; i >= 0; --i) {
            asteroids[i] = st_asteroids.top();
            st_asteroids.pop();
        }
  
        return asteroids;
    }
};
```
**Explanation:**
	Цель: Есть массив астероидов, число - это вес, а знкак - направление. Если астероиды летят на встречу друг другу, то если один меньше - он уничтожается, если они равны, то уничтодаются оба.
	Решение: Решение с помощью [[Stack]]. Проходится по каждому элементу в массиве,
	Если он больше 0, то добавлять в стек.
	Если меньше 0, то если стек не пустой и голова стека больше 0 и голова меньше этого астероида по модулю, то удалять.
		если стек пустой или голова стека меньше нуля, то добавить данный астероид в стек.
		если стек не пустой и голова стека равна жтому астероиду по модулю, то удалить.
	Изменить размер начального массива и перезаписывать все элементы из стека в этот массив с конца. Вернуть данный массив.
	Примечание: Решение бьется по рантайму на 100%, но по памяти не очень хорошо.