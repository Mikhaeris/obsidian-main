**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	int areaOfMaxDiagonal(vector<vector<int>>& dimensions) {
		int long_diag = 0, max_area = 0;
		for (const auto& sides : dimensions) {
			int len_cdiag = sides[0]*sides[0] + sides[1]*sides[1];
			int curr_area = sides[0]*sides[1];
			  
			if (long_diag < len_cdiag) {
				max_area = curr_area;
				long_diag = len_cdiag;
			} else if (long_diag == len_cdiag) {
				max_area = max(max_area, curr_area);
			}
		}
		  
		return max_area;
	}
};
```
**Explanation:**
	Цель: Дан массив сторон прямоугольников. Нужно найти площадь прямоугольника, у которого самая длиная диагональ. Если диагонали равны, то вернут максимальную площадь из этим прямоуголььников.
	Решение: Проходится по прямоугольникам и сравнивать самую длинную диагональ с текущей. Если текущая больше, то максимальная площадь равняется текущей площади и максимальная даигональ равняется текущей диагонали. Если диагонали равны, то максимальная площадь равняется макисмальной из двух этих прямоугольников.