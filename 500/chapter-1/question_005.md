### `question_005.md`

**Глава1. Вопрос 5.** При определении функции в Python можно установить значения параметров по умолчанию, что обеспечивает большую гибкость при вызове функции. Каков будет результат вызова следующей функции: `def multiply(a, b=2): return a * b`, если функция вызывается как `multiply(5)`?

A. Функция вернет 5.

B. Функция вызовет `TypeError` из-за отсутствующего аргумента.

C. Функция вернет 10, так как будет использовано значение по умолчанию `b`.

D. Функция вернет `None`, поскольку предоставлен только один параметр.

**Правильный ответ: C**

**Объяснение:**

*   **Параметры по умолчанию:** В Python можно задавать значения по умолчанию для параметров функции. Это означает, что если при вызове функции аргумент для этого параметра не указан, то будет использовано значение по умолчанию.

*   **Применение значения по умолчанию:** Если функция `multiply` вызывается с одним аргументом, например `multiply(5)`, то переданное значение `5` будет присвоено параметру `a`, а для параметра `b` будет использовано значение по умолчанию, которое равно `2`.
*  **Результат:** Функция вернет результат умножения переданного значения `a` на значение по умолчанию `b`, то есть 5 * 2 = 10.

**Пример:**

```python
def multiply(a: int, b: int = 2) -> int:
    return a * b

result1: int = multiply(5)
print(f"multiply(5): {result1}") # Вывод: multiply(5): 10

result2: int = multiply(5, 3)
print(f"multiply(5, 3): {result2}") # Вывод: multiply(5, 3): 15
```

**В результате:**

*   При вызове `multiply(5)` значение `5` присваивается параметру `a`, а параметр `b` принимает свое значение по умолчанию `2`. Функция возвращает `5 * 2 = 10`.

*   При вызове `multiply(5, 3)` значение `5` присваивается параметру `a`, значение `3` присваивается параметру `b`. Функция возвращает `5 * 3 = 15`.

Таким образом, ответ **C** является правильным, поскольку он точно описывает результат вызова функции `multiply(5)` с использованием значения по умолчанию для параметра `b`.