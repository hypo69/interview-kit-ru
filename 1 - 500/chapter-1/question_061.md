

### `question_61.md`

**Глава1. Вопрос 61.** Каков результат использования функции `len()` для словаря в Python, который содержит пять пар ключ-значение?

- A. Функция возвращает количество ключей в словаре.
- B. Она возвращает общее количество символов во всех ключах и значениях.
- C. Вывод — это количество значений в словаре.
- D. Она возвращает список, содержащий все ключи в словаре.

**Правильный ответ: A**

**Объяснение:**

Функция `len()` в Python используется для получения длины различных итерируемых объектов, таких как списки, строки, кортежи, а также словари.

*   **Вариант A** верен: При применении к словарю, `len()` возвращает количество ключей (или пар ключ-значение) в словаре.
*   **Вариант B** не верен: `len()` не подсчитывает символы в ключах и значениях словаря.
*   **Вариант C** не верен: `len()` не возвращает количество значений, это то же самое, что количество ключей.
*   **Вариант D** не верен:  `len()` возвращает одно число, а не список ключей. Для получения списка ключей используется метод `keys()` объекта `dict`.

**Как работает `len()` со словарями:**

1.  `len()` принимает словарь в качестве аргумента.
2.  Возвращает количество уникальных ключей, которые есть в словаре.
3.  Так как каждому ключу соответствует ровно одно значение, количество ключей равно количеству пар ключ-значение.

**Пример:**

```python
my_dict: dict[str, int] = {"a": 1, "b": 2, "c": 3, "d": 4, "e": 5}
length_of_dict: int = len(my_dict)
print(f"Длина словаря: {length_of_dict}") # Вывод: Длина словаря: 5
```
**В результате:**

Функция `len(my_dict)` возвращает `5`, поскольку в словаре `my_dict` содержится 5 пар ключ-значение (или, что то же самое, 5 ключей).

Таким образом, **вариант A** является правильным.