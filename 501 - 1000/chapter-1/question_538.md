### `question_538.md`

**Вопрос 540.** Какой результат будет получен при выполнении следующего кода Python, 
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

- A. `Original array: [64, 34, 25, 12, 22, 11, 90] Sorted array: [90, 64, 34, 25, 22, 12, 11]`
- B. `Original array: [64, 34, 25, 12, 22, 11, 90] Sorted array: [11, 12, 22, 25, 34, 64, 90]`
- C. `Original array: [64, 34, 25, 12, 22, 11, 90] Sorted array: [11, 90, 12, 64, 22, 34, 25]`
- D. `Original array: [64, 34, 25, 12, 22, 11, 90] Sorted array: [64, 34, 25, 22, 12, 11, 90]`

**Правильный ответ: B**

**Объяснение:**

Предоставленный код реализует алгоритм сортировки кучей (Heap Sort) с использованием модуля `heapq` в Python.

*   **Алгоритм сортировки кучей:**
    *   Преобразует исходный массив в мин-кучу (heap).
    *   Извлекает элементы из кучи по одному и помещает их в отсортированный массив.
    *  Модуль `heapq` в Python реализует мин-кучу.
*   **Описание кода:**
    *   `import heapq`: Импортирует модуль `heapq` для работы с кучей.
    *   `heap_sort(arr)`: Функция, которая принимает массив `arr` в качестве аргумента.
        *   `heapq.heapify(arr)`: Преобразует список `arr` в мин-кучу "на месте", то есть изменяет порядок элементов в самом массиве.
        *   `sorted_arr = []`:  Инициализируется пустой список для хранения отсортированных элементов.
        *   `while arr:`:  Цикл выполняется, пока в куче есть элементы.
        *   `sorted_arr.append(heapq.heappop(arr))`: Извлекает наименьший элемент из кучи (корень), добавляет его в `sorted_arr` и перестраивает кучу.
        *   `return sorted_arr`: возвращает отсортированный массив.

**Разбор вариантов:**
*   **A. `Original array: [64, 34, 25, 12, 22, 11, 90] Sorted array: [90, 64, 34, 25, 22, 12, 11]`:** Неправильно. Это результат сортировки по убыванию.
*  **B. `Original array: [64, 34, 25, 12, 22, 11, 90] Sorted array: [11, 12, 22, 25, 34, 64, 90]`:** Правильно.  Результат сортировки в порядке возрастания.
*   **C. `Original array: [64, 34, 25, 12, 22, 11, 90] Sorted array: [11, 90, 12, 64, 22, 34, 25]`:** Неправильно.
*   **D. `Original array: [64, 34, 25, 12, 22, 11, 90] Sorted array: [64, 34, 25, 22, 12, 11, 90]`:** Неправильно.

**В результате:**
*   Код правильно реализует алгоритм сортировки кучей для сортировки массива в порядке возрастания.
*   Модуль `heapq` упрощает работу с кучей в Python.
*   Сортировка кучей гарантирует временную сложность O(n log n) и является эффективным алгоритмом.
*   Алгоритм сортирует данные "на месте" (in place), что означает, что использует минимум дополнительной памяти

Таким образом, правильным ответом является **B. `Original array: [64, 34, 25, 12, 22, 11, 90] Sorted array: [11, 12, 22, 25, 34, 64, 90]`**.