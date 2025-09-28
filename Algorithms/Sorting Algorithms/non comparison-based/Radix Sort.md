Поразрядная сортировка - быстрый стабильный алгоритм сортировки.

Идея: Сортировать от меньших разардов к большим, с помощью сортировки подсчетом. Таким образом каждый проход будет формироваться массив бакетов размером 10(т.е. решение проблемы сортировки подсчетом).

Time Complexity: O(d * (n + b))
Space Complexity: O(n + b)

Алгоритм:
```cpp
void counting_sort(vector<int>& vec, int exp) {
    int n = vec.size();
    
    vector<int> output(n);
    vector<int> count(10);

    for (const auto& el : vec) {
        count[(el / exp) % 10]++;
    }
    
    /* prefix sum */
    for (int i = 0; i < 10; ++i) {
        count[i] += count[i - 1];
    }
    
    for (int i = n - 1; i >= 0; --i) {
        output[count[(vec[i] / exp) % 10]-1] = vec[i];
        count[(vec[i] / exp) % 10]--;
    }

    for (int i = 0; i < n; ++i) {
        vec[i] = output[i];
    }
}

void radix_sort(vector<int>& vec) {
    int max_el = 0;
    for (const auto& el : vec) {
        max_el = max(max_el, el);
    }

    for (int exp = 1; max_el / exp > 0; exp *= 10) {
        counting_sort(vec, exp);
    }
}
```
Объяснение: Находится макимальный элемент. Дальше проходится по его разрядам и сортировать элементы с помощью counting sort по разрядам стабильно.