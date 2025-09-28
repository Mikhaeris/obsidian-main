Быстрая сортировка - сортировка массива на месте, выбирая элемент, который вставляется на место, а все элементы меньше него перещаются влево(т.е. большие окажутся справа), пока не будут отсортированы все элементы.

Идея: Разделять большую задачу на меленькие подзадачи. Проще сортировать едениченые элементы, чем все целиком.

Time Complexity: O(N\*logN)
Space Complexity: O(1)

Алгоритм:
```cpp
int lomuto_partition(vector<int>& arr, int low, int high) {
    int key = arr[high];
    int i = low - 1;
    for (int j = low; j < high; j++) {
        if (arr[j] < key) {
            i++;
            swap(arr[i], arr[j]);
        }
    }
    
    swap(arr[i + 1], arr[high]);  
    return i + 1;
}

int hoares_partition(vector<int>& arr, int low, int high) {
    int pi_idx = low;
    int key = arr[low];
    
    low++;
    while (low < high) {
        if (arr[low] < key) {
            low++;
            continue;
        }

        if (arr[high] > key) {
            high--;
            continue;
        }
        
        swap(arr[low++], arr[high--]);
    }

    int idx = (arr[low] < key) ? low : low - 1;
    swap(arr[pi_idx], arr[idx]);
    return idx;
}

void quickSort(vector<int>& arr, int low, int high) {
    if (low >= high) {
        return;
    }
      
    int pi = hoares_partition(arr, low, high);
    if (pi > low) {
        quickSort(arr, low, pi - 1);
    }
    quickSort(arr, pi + 1, high);
}
```
Объяснение: Выбирать элемент(левый крайний или правый крайний или рандомный), слева от которого ставятся меньшие элементы, а справа большие(тут есть два наиболее популярных алгоритма:
	Алгоритм Ломуто - пивот элемент выбирается последним, все элементы меньше пивот элемента ставятся слева, пивот элемент ставится в свое место.
	Алгоритм Хоаре - пивот элемент берется первым(в данном случае), с помощью двух указателей находить слева элементы больше пивота, а справа меньше пивота и менять их местами, пока два указателя не встретяться местами. Этот алгоритм предпочтительнее.)
далее рекурсивно повторять эти действия для левой и правой части, пока все элементы не встанут на свои места.