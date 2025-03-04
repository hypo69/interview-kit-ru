### `question_539.md`

**Вопрос 539.** Какой результат будет получен при выполнении следующего кода Python, 
реализующего алгоритм сортировки кучей?

```python
import heapq

def heap_sort(arr):
    heapq.heapify(arr)
    sorted_arr = []
    while arr:
        sorted_arr.append(heapq.heappop(arr))
    return sorted_arr

# Пример использования
arr = [64, 34, 25, 12, 22, 11, 90]
print("Original array:", arr)
sorted_arr = heap_sort(arr)
print("Sorted array:", sorted_arr)
```

-   A. `Original array: [64, 34, 25, 12, 22, 11, 90] Sorted array: [90, 64, 34, 25, 22, 12, 11]`
-   B. `Original array: [64, 34, 25, 12, 22, 11, 90] Sorted array: [11, 12, 22, 25, 34, 64, 90]`
-   C. `Original array: [64, 34, 25, 12, 22, 11, 90] Sorted array: [11, 90, 12, 64, 22, 34, 25]`
-   D. `Original array: [64, 34, 25, 12, 22, 11, 90] Sorted array: [64, 34, 25, 22, 12, 11, 90]`

**Правильный ответ: B**

**Объяснение:**

Предоставленный код реализует алгоритм сортировки кучей (heap sort) с использованием модуля `heapq` в Python.

*   **Алгоритм сортировки кучей:**
    *   Использует структуру данных "куча" (heap), которая представляет собой двоичное дерево, удовлетворяющее свойству кучи (каждый узел больше или равен своим потомкам).
    *   Строит кучу из массива.
    *   Постепенно извлекает наименьший (или наибольший) элемент из кучи, добавляя его в отсортированный массив.
*   **Описание кода:**
    *   `heap_sort(arr)`: Функция принимает массив `arr` в качестве аргумента.
        *   `heapq.heapify(arr)`: Преобразует массив в min-кучу (минимальный элемент всегда находится в корне).
        *   `sorted_arr = []`: Создает пустой список для хранения отсортированных элементов.
        *   `while arr`: Цикл, пока куча не пуста.
        *   `sorted_arr.append(heapq.heappop(arr))`: Извлекает минимальный элемент из кучи и добавляет его в отсортированный список.
        *   `return sorted_arr`: Возвращает отсортированный список.

**Разбор вариантов:**
*   **A. `Original array: [64, 34, 25, 12, 22, 11, 90] Sorted array: [90, 64, 34, 25, 22, 12, 11]`:** Неправильно, это сортировка по убыванию.
*   **B. `Original array: [64, 34, 25, 12, 22, 11, 90] Sorted array: [11, 12, 22, 25, 34, 64, 90]`:** Правильно. Результат сортировки в порядке возрастания.
*   **C. `Original array: [64, 34, 25, 12, 22, 11, 90] Sorted array: [11, 90, 12, 64, 22, 34, 25]`:** Неправильно.
*   **D. `Original array: [64, 34, 25, 12, 22, 11, 90] Sorted array: [64, 34, 25, 22, 12, 11, 90]`:** Неправильно.

**В результате:**
*   Код правильно реализует алгоритм сортировки кучей для сортировки массива в порядке возрастания.
*   Сортировка кучей является эффективным алгоритмом сортировки, имеющим гарантированную временную сложность O(n log n).
*   Используется стандартный модуль `heapq`, который предоставляет инструменты для работы с кучами.

Таким образом, правильным ответом является **B. `Original array: [64, 34, 25, 12, 22, 11, 90] Sorted array: [11, 12, 22, 25, 34, 64, 90]`**.

### `question_538.md`

**Вопрос 538.** Какой результат будет получен при выполнении следующего кода Python, реализующего алгоритм поразрядной сортировки?

```python
def radix_sort(arr):
    max_val = max(arr)
    exp = 1
    while max_val // exp > 0:
        counting_sort(arr, exp)
        exp *= 10
    return arr

def counting_sort(arr, exp):
    n = len(arr)
    output = [0] * n
    count = [0] * 10

    for i in range(n):
        index = (arr[i] // exp) % 10
        count[index] += 1

    for i in range(1, 10):
        count[i] += count[i - 1]

    for i in range(n - 1, -1, -1):
        index = (arr[i] // exp) % 10
        output[count[index] - 1] = arr[i]
        count[index] -= 1

    for i in range(n):
        arr[i] = output[i]


# Пример использования
arr = [170, 45, 75, 90, 802, 24, 2, 66]
print("Original array:", arr)
sorted_arr = radix_sort(arr)
print("Sorted array:", sorted_arr)
```

-   A. `Original array: [170, 45, 75, 90, 802, 24, 2, 66] Sorted array: [802, 170, 90, 75, 66, 45, 24, 2]`
-   B. `Original array: [170, 45, 75, 90, 802, 24, 2, 66] Sorted array: [2, 24, 45, 66, 75, 90, 170, 802]`
-   C. `Original array: [170, 45, 75, 90, 802, 24, 2, 66] Sorted array: [2, 170, 24, 45, 66, 75, 90, 802]`
-   D. `Original array: [170, 45, 75, 90, 802, 24, 2, 66] Sorted array: [170, 45, 2, 24, 66, 75, 90, 802]`

**Правильный ответ: B**

**Объяснение:**

Предоставленный код реализует алгоритм поразрядной сортировки (radix sort), который является не основанным на сравнении алгоритмом.

*   **Алгоритм поразрядной сортировки:**
    *   Сортирует элементы, начиная с младшего разряда (единицы) и далее к старшим разрядам.
    *   Использует стабильную сортировку подсчетом для сортировки элементов по разряду.
*   **Описание кода:**
    *   `radix_sort(arr)`: Функция принимает массив `arr` в качестве аргумента.
        *   `max_val = max(arr)`: Находит максимальное значение для определения количества разрядов.
        *   `exp = 1`: Инициализирует переменную `exp` для разряда (1, 10, 100, ...).
        *   `while max_val // exp > 0`: Цикл проходит по всем разрядам.
        *  `counting_sort(arr, exp)`: Сортирует массив по текущему разряду.
    *   `counting_sort(arr, exp)`: Функция выполняет сортировку подсчетом для текущего разряда.
        *  `n = len(arr)`: Длина массива.
        *  `output = [0] * n`: Создает список для хранения отсортированных элементов.
        *  `count = [0] * 10`:  Создает список для подсчета частоты цифр в текущем разряде (0-9).
        *   `for i in range(n)`: Цикл подсчитывает частоту цифр в текущем разряде.
        *   `for i in range(1, 10)`: Цикл преобразовывает `count` массив, что бы он хранил позиции цифр в `output`.
        * `for i in range(n - 1, -1, -1)`: Цикл  ставит элементы на правильную позицию, уменьшая count[index].
        *  `for i in range(n)`: Копирует значения из `output` в `arr`
**Разбор вариантов:**
*   **A. `Original array: [170, 45, 75, 90, 802, 24, 2, 66] Sorted array: [802, 170, 90, 75, 66, 45, 24, 2]`:** Неправильно. Это сортировка в порядке убывания.
*   **B. `Original array: [170, 45, 75, 90, 802, 24, 2, 66] Sorted array: [2, 24, 45, 66, 75, 90, 170, 802]`:** Правильно. Результат сортировки в порядке возрастания.
*   **C. `Original array: [170, 45, 75, 90, 802, 24, 2, 66] Sorted array: [2, 170, 24, 45, 66, 75, 90, 802]`:** Неправильно.
*   **D. `Original array: [170, 45, 75, 90, 802, 24, 2, 66] Sorted array: [170, 45, 2, 24, 66, 75, 90, 802]`:** Неправильно.

**В результате:**
*   Код правильно реализует алгоритм поразрядной сортировки для сортировки массива в порядке возрастания.
*   Поразрядная сортировка подходит для сортировки элементов, значения которых находятся в определенном диапазоне, и может быть эффективнее алгоритмов на основе сравнения, если диапазон значений не слишком велик.

Таким образом, правильным ответом является **B. `Original array: [170, 45, 75, 90, 802, 24, 2, 66] Sorted array: [2, 24, 45, 66, 75, 90, 170, 802]`**.
