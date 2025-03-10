### `question_068.md`

**Вопрос 068.** Дан массив целых чисел `nums`, содержащий `n` элементов, и целое число `k`. Разработайте алгоритм для поиска непрерывного подмассива (subarray) длины `k` в массиве `nums`, который имеет максимальное среднее значение. Возвратите это максимальное среднее значение.

**Примеры:**

```
Ввод: nums = [1,12,-5,-6,50,3], k = 4
Вывод: 12.75000

Ввод: nums = [5], k = 1
Вывод: 5.00000
```

-  A. Для решения задачи нужно использовать жадный алгоритм и выбирать на каждом шаге самый большой элемент из списка.
-  B. Для решения задачи нужно использовать алгоритм поиска в ширину (BFS).
- C. Для решения задачи нужно использовать метод "скользящего окна" для эффективного поиска максимального среднего.
- D. Для решения задачи, необходимо использовать рекурсивный обход всех вариантов.

**Правильный ответ: C**

**Объяснение:**

Для решения задачи поиска подмассива с максимальным средним значением и фиксированной длиной `k` в массиве чисел, оптимальным является применение метода "скользящего окна". Этот метод обеспечивает линейную временную сложность `O(n)`, позволяя обойти массив только один раз.

*   **Алгоритм (скользящее окно):**
    1.  **Инициализация:**
         *  Вычисляем сумму первых `k` элементов массива, и сохраняем их в переменной `current_sum`.
         *    Максимальная сумма `max_sum`  инициализируется  значением `current_sum`.
    2. **Скользящее окно:**
         *    Начиная с  `k`-го элемента до конца массива (для индекса  `i`),  поддерживаем окно размера k:
              *  Из `current_sum` вычитаем элемент из начала окна (`nums[i-k]`).
             * К `current_sum` добавляем новый элемент в конце окна `nums[i]`.
         *   Сравниваем  `current_sum`  с `max_sum` и если  больше то `max_sum = current_sum`
    3.  **Возвращаем результат:**  После перебора всех элементов, возвращаем `max_sum / k`,  что соответствует  максимальному среднему значению подмассива.

*   **Преимущества алгоритма:**
    *   **Линейная сложность:**  Обеспечивает временную сложность O(n).
    *   **Постоянная память:**  Использует постоянное количество дополнительной памяти.
    *   **Простота:** Легок в реализации.

**Примеры (псевдокод):**

```
function find_max_avg(nums, k):
    n = length(nums)
    current_sum = sum(nums[0] to nums[k-1])
    max_sum = current_sum
    for i in range from k to n:
        current_sum = current_sum - nums[i - k] + nums[i]
        max_sum = max(max_sum, current_sum)
    return max_sum/k
```

**Примеры реализации в Python:**
```python
def find_max_avg(nums, k):
    n = len(nums)
    current_sum = sum(nums[:k])
    max_sum = current_sum
    for i in range(k, n):
      current_sum = current_sum - nums[i - k] + nums[i]
      max_sum = max(max_sum, current_sum)
    return max_sum / k

nums1 = [1, 12, -5, -6, 50, 3]
k1 = 4
print(f"Ввод: nums = {nums1}, k = {k1}")
print(f"Вывод: {find_max_avg(nums1, k1)}") # Выведет: 12.75

nums2 = [5]
k2 = 1
print(f"Ввод: nums = {nums2}, k = {k2}")
print(f"Вывод: {find_max_avg(nums2, k2)}")  # Выведет: 5.0
```
**Разбор вариантов:**
*   **A. Для решения задачи нужно сначала отсортировать массив capacity, затем последовательно заполнять сумки, пока не закончатся камни.:** Неправильно.
*  **B. Для решения задачи нужно использовать алгоритм поиска в ширину (BFS).:** Неправильно. BFS не является подходящим для этой задачи.
*  **C. Для решения задачи нужно использовать метод "скользящего окна" для эффективного поиска максимального среднего.:** Правильно.
* **D. Для решения задачи нужно использовать только рекурсивный алгоритм.:** Неправильно. Рекурсивный алгоритм не подходит.

**В результате:**
*  Алгоритм скользящего окна позволяет эффективно находить подмассив с максимальным средним значением.
*  Итерируясь по массиву только один раз достигается  сложность O(n)
*  Результирующее среднее  значение будет получено с помощью деления  максимальной суммы на размер подмассива `k`

Таким образом, правильным ответом является **C. Для решения задачи нужно использовать метод "скользящего окна" для эффективного поиска максимального среднего.**
