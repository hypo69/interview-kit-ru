### `question_134.md`

**Вопрос 34.** Какой тип цикла в Python лучше всего подходит для перебора элементов списка?

A. Цикл `while`.
B. Цикл `for`.
C. Рекурсивный вызов функции.
D. Условный оператор `if`.

**Правильный ответ: B**

**Объяснение:**

Цикл `for` является наиболее подходящим для перебора элементов списка (или любого другого итерируемого объекта) в Python.

*   **Вариант A** не верен: `while` подходит для выполнения кода, пока условие истинно, а не для перебора элементов в коллекции.
*   **Вариант B** верен: Цикл `for` предназначен для итерации по последовательностям, таким как списки, кортежи и строки.
*   **Вариант C** не верен: Рекурсия - это альтернативный способ выполнения повторяющихся задач, но обычно менее эффективный, чем циклы для перебора списков.
*   **Вариант D** не верен: Условный оператор `if` используется для выполнения кода в зависимости от условия, а не для перебора элементов.

**Как работает цикл `for` для списка:**

1.  Цикл `for` проходит по каждому элементу в списке.
2.  На каждой итерации переменная цикла принимает значение текущего элемента.
3.  После обработки текущего элемента, цикл переходит к следующему элементу.
4.  Цикл завершается, когда все элементы в списке будут перебраны.

**Пример:**

```python
my_list: list[str] = ["яблоко", "банан", "вишня"]

for item in my_list:
    print(item) # вывод каждого элемента

# Вывод:
# яблоко
# банан
# вишня
```

**В результате:**

*   Цикл `for` позволяет легко перебрать все элементы списка `my_list`.
*   На каждой итерации переменная `item` принимает значение очередного элемента.

Таким образом, **вариант B** является правильным ответом.