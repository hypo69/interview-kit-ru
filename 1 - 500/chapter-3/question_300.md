### `question_300.md`

**Вопрос 300.** Каково назначение функции `filter()` в Python и чем она отличается от функции `map()` с точки зрения того, что она возвращает?

A. Функция `filter()` применяет функцию к каждому элементу в итерируемом объекте и возвращает отфильтрованную версию с элементами, которые соответствуют условию `True`. Функция `map()` применяет функцию к каждому элементу и возвращает измененную версию оригинального итерируемого объекта.
B. Функция `filter()` применяет функцию к итерируемому объекту и возвращает кортеж из всех элементов в итерируемом объекте. Функция `map()` возвращает список всех значений в итерируемом объекте.
C. Функция `filter()` выполняет вычисления над итерируемым объектом и возвращает числовое значение, а `map()` выполняет логические операции.
D. И `filter()`, и `map()` возвращают одинаковый результат, без функциональной разницы между ними.

**Правильный ответ: A**

**Объяснение:**

Функции `filter()` и `map()` являются встроенными функциями Python, которые используются для обработки итерируемых объектов (например, списков, кортежей), но они выполняют разные задачи и возвращают разные результаты.

*   **`filter(function, iterable)`:**
    *   Применяет функцию `function` к *каждому элементу* `iterable`. Функция должна возвращать `True` или `False`.
    *   Возвращает *итератор*, содержащий только те элементы из `iterable`, для которых функция вернула `True`.
    *   Предназначена для *фильтрации* элементов в последовательности.
*   **`map(function, iterable)`:**
     *   Применяет функцию `function` к *каждому элементу* `iterable`.
     *   Возвращает *итератор*, содержащий результаты применения `function` к каждому элементу `iterable`.
     *   Предназначена для *трансформации* каждого элемента последовательности.

*   **Вариант A верен:** Это правильное описание различий в назначении и результатах функций `filter()` и `map()`.
*   **Вариант B не верен:**  `filter` возвращает *итератор* (не кортеж),  а не все элементы, а только отфильтрованные. `map()` возвращает итератор, а не список.
*   **Вариант C не верен:**  `filter` выполняет логическую фильтрацию, а `map` - трансформацию элементов. Ни одна из функций не возвращает числовое значение, если только вызываемая функция не возвращает число.
*   **Вариант D не верен:** `filter()` и `map()` выполняют разные задачи и возвращают разные результаты.

**Пример:**

```python
numbers = [1, 2, 3, 4, 5, 6]

# Использование filter() для отбора четных чисел
even_numbers = list(filter(lambda x: x % 2 == 0, numbers)) # Returns [2,4,6]
print(even_numbers) # Output: [2, 4, 6]

# Использование map() для умножения всех чисел на 2
multiplied_numbers = list(map(lambda x: x * 2, numbers)) # Returns [2,4,6,8,10,12]
print(multiplied_numbers) # Output: [2, 4, 6, 8, 10, 12]
```
**В результате:**

`filter()` применяется для отбора элементов из последовательности на основе заданного условия, а `map()` применяется для преобразования каждого элемента последовательности.  `filter()` возвращает итератор с *отфильтрованными* элементами, а `map()` - с *преобразованными*.

Таким образом, вариант A является правильным.

---

Готов к следующему вопросу!
