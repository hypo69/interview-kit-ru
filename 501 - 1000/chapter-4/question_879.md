### `question_879.md`

**Вопрос 879.** Как в Python происходит одновременный обмен значениями между двумя переменными с использованием синтаксиса `a, b = b, a`, и какие преимущества этот способ имеет по сравнению с традиционным подходом с использованием временной переменной?

A.  Python выполняет эту операцию, создавая временную переменную для хранения одного из значений, как и в других языках программирования.
B.  Python выполняет эту операцию, последовательно присваивая значения справа налево, поэтому временная переменная не требуется.
C.  Python сначала создает кортеж из значений в правой части выражения, а затем распаковывает этот кортеж в переменные слева, выполняя все в один шаг без явного создания временной переменной.
D.  Этот синтаксис является просто сокращением для двух отдельных операций присваивания и не имеет никакого отношения к кортежам.

**Правильный ответ: C**

**Объяснение:**

В Python одновременный обмен значениями с использованием синтаксиса `a, b = b, a` является элегантным и эффективным способом поменять значения двух переменных местами.

1.  **Кортеж (Tuple) Packing:** Сначала Python вычисляет значения в правой части выражения (`b, a`) и упаковывает их в кортеж.
2.  **Кортеж (Tuple) Unpacking:** Затем этот кортеж распаковывается в переменные, указанные слева (`a, b`). Важно, что обе операции (упаковка и распаковка) выполняются *одновременно*.

*   **Преимущества:**
    *   **Отсутствие временной переменной:** Нет необходимости создавать временную переменную для хранения одного из значений, что делает код более кратким и читаемым.
    *   **Атомарность:** Операция выполняется как единое целое. Это позволяет избежать проблем, которые могли бы возникнуть при частичном выполнении операции (например, при возникновении исключения).
    *   **Эффективность:** Python оптимизирован для работы с кортежами, поэтому одновременное присваивание выполняется достаточно быстро.

*   **Вариант A не верен:** В Python эта операция не требует временной переменной.
*   **Вариант B не верен:** Присваивание не происходит последовательно.
*   **Вариант C верен:** Это правильное описание работы данного синтаксиса.
*   **Вариант D не верен:** Синтаксис напрямую связан с созданием кортежа.

**Пример:**

```python
a = 10
b = 20
print(f"Before swap: a = {a}, b = {b}")

a, b = b, a  # одновременный обмен значениями

print(f"After swap: a = {a}, b = {b}")
```

**В результате:**

Python сначала создает кортеж из значений в правой части выражения `b, a`, а затем распаковывает этот кортеж в переменные `a` и `b`, что позволяет выполнить одновременный обмен значениями без использования временной переменной.

Таким образом, вариант C является правильным.