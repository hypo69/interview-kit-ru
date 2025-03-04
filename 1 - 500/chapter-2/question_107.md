### `question_107.md`

**Вопрос 107.** В Python, чем отличается использование цикла `while` от цикла `for`?

- A.  Цикл `while` обычно используется, когда количество итераций заранее не определено и должно продолжаться до тех пор, пока не изменится определенное условие.
- B.  Цикл `while` выполняет блок кода, пока список, предоставленный ему, содержит элементы.
- C.  Цикл `for` используется только для итерации по последовательностям (например, списки или строки) и не может использоваться для условного цикла.
- D.  Цикл `for` обычно используется, когда вам нужно выполнить блок кода определенное количество раз, обычно на основе счетчика или итерируемого объекта.

**Правильный ответ: A**

**Объяснение:**

Циклы `while` и `for` — это два основных типа циклов в Python, но они используются в разных ситуациях.

*   **Вариант A** верен: `while` используется, когда количество итераций заранее неизвестно, и цикл продолжается до тех пор, пока условие истинно.

*   **Вариант B** не верен: Цикл `while`  работает на основе *условия*, а не проверяет наличие элементов.
*   **Вариант C** не верен: Цикл `for` можно использовать и для условных циклов, если он итерируется, например, по диапазону.
*   **Вариант D** не верен: Цикл `for` также может итерироваться по последовательностям, а не только по счетчику.

**Основные различия:**

1.  **`for`:**
    *   Используется для итерации по последовательности (списку, кортежу, строке и т.д.) или итерируемому объекту.
    *   Количество итераций определяется длиной последовательности или итерируемого объекта.
    *   Подходит, когда известно, по каким элементам нужно итерировать.

2.  **`while`:**
    *   Используется для выполнения блока кода до тех пор, пока условие истинно.
    *   Количество итераций заранее неизвестно, и цикл может продолжаться до тех пор, пока условие не станет ложным.
    *   Подходит, когда нужно выполнять код, пока выполняется определенное условие.

**Примеры:**

```python
# Пример цикла for
my_list: list[int] = [1, 2, 3, 4, 5]
for number in my_list:
    print(number)

# Пример цикла while
x: int = 0
while x < 5:
    print(x)
    x += 1

# Пример while, когда количество итераций заранее неизвестно
user_input: str = ""
while user_input != "stop":
    user_input = input("Введите команду (или 'stop' для выхода): ")
    print(f"Вы ввели: {user_input}")
```

**В результате:**
* Цикл `for` используется для перебора заранее известных элементов списка.
* Цикл `while`  используется, когда количество итераций заранее неизвестно и зависит от значения переменной `x`.

Таким образом, **вариант A** является правильным.
