### `question_89.md`

**Вопрос 89.** Как можно объединить два списка в Python?

- A. `list3 = list1 + list2`
- B. `list3 = list1.append(list2)`
- C. `list3 = concat(list1, list2)`
- D. `list3 = list1.extend(list2)`

**Правильный ответ: A**

**Объяснение:**

В Python для объединения двух списков используется оператор `+` или метод `extend()`.

*   **Вариант A** верен: Оператор `+` создает новый список, который является результатом объединения двух исходных списков.

*   **Вариант B** не верен: Метод `append()` добавляет второй список как один элемент в конец первого списка, не объединяя их элементы.

*   **Вариант C** не верен: Функция `concat()` не является встроенной функцией Python.

*   **Вариант D** верен: Метод `extend()` добавляет все элементы второго списка в конец первого списка, изменяя исходный список.

**Оператор `+`:**

1.  Создает новый список, объединяя все элементы обоих списков в одном новом списке.
2.  Не изменяет исходные списки.

**Метод `extend()`:**

1.  Добавляет все элементы из второго списка в конец первого списка, *изменяя* первый список.
2.   Не возвращает новый список, а изменяет существующий список.

**Пример:**

```python
# Пример с оператором +
list1: list[int] = [1, 2, 3]
list2: list[int] = [4, 5, 6]
list3: list[int] = list1 + list2
print(f"list1: {list1}")
print(f"list2: {list2}")
print(f"list1 + list2: {list3}")
# Вывод:
# list1: [1, 2, 3]
# list2: [4, 5, 6]
# list1 + list2: [1, 2, 3, 4, 5, 6]

# Пример с методом extend()
list4: list[int] = [1, 2, 3]
list5: list[int] = [4, 5, 6]
list4.extend(list5)
print(f"list4 после extend(list5): {list4}") # Вывод: list4 после extend(list5): [1, 2, 3, 4, 5, 6]
```

**В результате:**
*  Оператор `+` создает *новый* список с элементами из `list1` и `list2`, не меняя исходные.
*   `extend`  изменяет `list4` на месте.

Таким образом, **вариант A** является верным вариантом для создания нового списка путем объединения двух исходных. Вариант D также корректен, но он модифицирует исходный список, а не создает новый.
