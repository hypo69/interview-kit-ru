### `question_165.md`

**Вопрос 65.** Каково основное отличие между методом `append()` и методом `extend()` при использовании их со списками в Python?

A.  Метод `append()` добавляет элементы одного списка к другому, а метод `extend()` добавляет только один элемент в конец списка.
B.  Метод `append()` добавляет один элемент в конец списка, а метод `extend()` добавляет элементы из итерируемого объекта в конец списка.
C.  Метод `append()` добавляет элементы в начало списка, а метод `extend()` добавляет в конец.
D.  Метод `append()` создает новый список, а метод `extend()` модифицирует существующий.

**Правильный ответ: B**

**Объяснение:**

Методы `append()` и `extend()` служат для добавления элементов в конец списка, но они работают по-разному.

*   **Вариант A** не верен: `append()` добавляет один элемент, а `extend()` добавляет несколько.
*   **Вариант B** верен: `append()` добавляет *один* элемент, `extend()` добавляет *элементы* из итерируемого объекта.
*   **Вариант C** не верен: Оба метода добавляют элементы в конец списка, а не в начало.
*   **Вариант D** не верен: Оба метода модифицируют существующий список, а не создают новый.

**Как работают `append()` и `extend()`:**

1.  `append(element)`: Добавляет `element` как единое целое в конец списка. Если `element` — это список, то он будет добавлен как вложенный список.
2.  `extend(iterable)`: Добавляет элементы из итерируемого объекта (списка, кортежа, строки и т. д.) в конец списка, делая их частью текущего списка.

**Пример:**

```python
list1: list[int] = [1, 2, 3]
list2: list[int] = [4, 5, 6]

# Пример append()
list1.append(list2)
print(f"list1 после append: {list1}") # Вывод: list1 после append: [1, 2, 3, [4, 5, 6]]


list3: list[int] = [1, 2, 3]
list4: list[int] = [4, 5, 6]
# Пример extend()
list3.extend(list4)
print(f"list3 после extend: {list3}") # Вывод: list3 после extend: [1, 2, 3, 4, 5, 6]

```

**В результате:**

*   Метод `append()` добавляет `list2` как один элемент в конец `list1`, что приводит к вложению списка.
*   Метод `extend()` добавляет элементы из `list4` в конец `list3` по отдельности.

Таким образом, **вариант B** является правильным ответом.