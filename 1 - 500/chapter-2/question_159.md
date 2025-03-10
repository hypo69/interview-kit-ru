### `question_159.md`

**Вопрос 59.** Какова цель использования блоков `try` и `except` в Python?

A. Для улучшения читаемости кода.
B. Для увеличения скорости выполнения кода.
C. Для обработки исключений и предотвращения аварийного завершения программы.
D. Для создания итераторов.

**Правильный ответ: C**

**Объяснение:**

Блоки `try` и `except` используются для обработки исключений в Python. Это важный механизм для создания надежных программ, способных корректно обрабатывать ошибки во время выполнения.

*   **Вариант A** не верен: `try-except` не используются для улучшения читаемости кода.
*   **Вариант B** не верен: `try-except` не ускоряют код.
*   **Вариант C** верен: `try-except` используются для перехвата исключений и корректной обработки ошибок.
*  **Вариант D** не верен: для создания итераторов используются генераторы (`yield`) или классы, реализующие протокол итератора.

**Как работает `try-except`:**

1.  Код, который потенциально может вызвать исключение, помещается в блок `try`.
2.  Если во время выполнения кода в блоке `try` происходит исключение, Python прекращает выполнение блока `try` и ищет соответствующий блок `except` для обработки исключения.
3.  Если подходящий блок `except` найден, то код внутри него выполняется, позволяя корректно обработать ошибку. Если нет, программа завершится с необработанным исключением.
4.  Если в блоке `try` не было ошибок, то код в блоке `except` не выполняется.

**Пример:**

```python
try:
    result: int = 10 / 0
except ZeroDivisionError:
    print("Произошла ошибка: Деление на ноль!")

try:
    result: int = int("abc")
except ValueError as e:
   print(f"Произошла ошибка: {e}")
```

**В результате:**

* В первом примере,  `try` блок  вызывает исключение `ZeroDivisionError`, которое обрабатывается в блоке `except`.
* Во втором примере, `try`  блок вызывает `ValueError`, который обрабатывается в блоке `except`, с возможностью получить сообщение.

Таким образом, **вариант C** является правильным.
