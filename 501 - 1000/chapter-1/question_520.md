### `question_520.md`

**Вопрос 520.** Какой результат выведет на экран следующий код Python?

```python
def foo(x, y, z):
    x[0] = 10
    y = 20
    z = [5]
    return y,z

my_list = [1,2,3]
my_int = 5
my_list2 = [100]
a, b = foo(my_list,my_int, my_list2)
print(my_list, my_int, a, b, my_list2)
```

-   A.  `[10, 2, 3] 5 20 [5] [100]`
-   B.  `[1, 2, 3] 5 20 [5] [100]`
-   C.  `[10, 2, 3] 5 20 [5] [10]`
-  D.  `[10, 2, 3] 5 20 [5] [5]`

**Правильный ответ: A**

**Объяснение:**

Этот код иллюстрирует разницу между изменением изменяемых (мутабельных) и неизменяемых (иммутабельных) объектов в Python, а также как это влияет на передачу аргументов в функции.

1.  **Инициализация переменных:**
    *   `my_list` инициализируется списком `[1, 2, 3]`.
    *   `my_int` инициализируется целым числом `5`.
    *   `my_list2` инициализируется списком `[100]`.
2.  **Функция `foo`:**
    *   Принимает три аргумента: `x`, `y`, `z`.
    *   `x[0] = 10`: Изменяет *первый элемент* списка `x`. Так как список является мутабельным объектом, то это изменение затронет и `my_list` в глобальной области видимости, так как `x` является ссылкой на `my_list`.
    *   `y = 20`: Присваивает переменной `y` новое значение `20`. Целые числа являются неизменяемыми объектами, поэтому это изменение происходит только внутри функции, и не меняет `my_int`.
    *   `z = [5]`: Присваивает переменной `z` новый список `[5]`. Списки мутабельные, но происходит переприсваивание переменной `z` внутри функции, что не влияет на `my_list2`
    *   `return y, z`: Функция возвращает новые значения переменных `y` и `z`.
3.  **Вызов `foo`:**
    *   `a, b = foo(my_list, my_int, my_list2)`: Функция `foo` вызывается с аргументами `my_list`, `my_int`, `my_list2`, а ее возвращаемые значения присваиваются переменным `a` и `b`.
4. **Вывод:** `print(my_list, my_int, a, b, my_list2)`: Выводятся все переменные.

**Анализ мутабельности:**
* Списки (list) - мутабельные типы данных. Это означает, что они могут быть изменены напрямую, и если передать список в функцию, то функция может изменить исходный список.
* Целые числа (int) - иммутабельные типы данных. Изменение переменной не затрагивает исходный объект, а создает новый.

**Разбор вариантов:**
*   **A.  `[10, 2, 3] 5 20 [5] [100]`**: Правильно, `my_list` был изменен функцией, `my_int` не изменился, a = 20, b = [5], `my_list2` не изменился.
*   **B. `[1, 2, 3] 5 20 [5] [100]`**: Неправильно, так как `my_list` должен был изменится внутри функции.
*   **C. `[10, 2, 3] 5 20 [5] [10]`**: Неправильно, так как `my_list2`  не должен был измениться.
*  **D. `[10, 2, 3] 5 20 [5] [5]`**: Неправильно, так как `my_list2` не должен был измениться.

**В результате:**
*   Функция `foo` изменяет список `my_list` (мутабельный объект), но не меняет целое число `my_int` (иммутабельный объект).
*  Переменные `a` и `b` получают возвращаемые значения из функции.
*   Важно понимать, как мутабельные и иммутабельные объекты обрабатываются при передаче в функции, это может повлиять на неожиданные побочные эффекты.

Таким образом, правильным ответом является **A. `[10, 2, 3] 5 20 [5] [100]`**.
