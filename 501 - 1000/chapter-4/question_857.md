### `question_857.md`

**Вопрос 857.** Что будет выведено на экран в результате выполнения следующего Python-кода?

```python
list_example = [1, 2, 3, 4, 5]
another_list = list_example
another_list[0] = 100
print(list_example)
```

A.  `[1, 2, 3, 4, 5]`
B.  `[100, 2, 3, 4, 5]`
C.  `[1, 100, 3, 4, 5]`
D.  `Error`

**Правильный ответ: B**

**Объяснение:**

Этот код демонстрирует концепцию *поверхностного копирования* и изменяемости списков в Python.

1.  **`list_example = [1, 2, 3, 4, 5]`:**
    *   Создается список с именем `list_example`, содержащий целые числа.

2.  **`another_list = list_example`:**
    *   Переменной `another_list` присваивается *не копия*, а *ссылка* на тот же самый список, на который указывает `list_example`. Это называется *поверхностным копированием*.  Обе переменные теперь указывают на один и тот же объект в памяти.

3.  **`another_list[0] = 100`:**
    *   Изменяется элемент с индексом 0 в списке, на который указывает `another_list`. Так как `another_list` и `list_example` указывают на *один и тот же* список, изменение `another_list` также отразится на `list_example`.

4.  **`print(list_example)`:**
    *   Выводится на экран содержимое списка, на который указывает `list_example`.

*   **Вариант A не верен:** Список `list_example` был изменен.
*   **Вариант B верен:** Этот ответ отражает правильное понимание.
*   **Вариант C не верен:**  Изменялся элемент с индексом 0, а не 1.
*   **Вариант D не верен:** Код не выдает ошибок.

**Ключевые понятия:**

*   **Поверхностное копирование:** Создается новая переменная, которая ссылается на тот же объект, что и исходная переменная. Изменения, внесенные через одну переменную, отражаются в другой.
*   **Изменяемость:** Списки являются изменяемыми объектами, то есть их содержимое можно менять после создания.

**В результате:**

Поскольку `another_list` является лишь другой ссылкой на тот же список, что и `list_example`, изменение значения `another_list[0]` приводит к изменению *оригинального* списка `list_example`. Поэтому на экран будет выведено `[100, 2, 3, 4, 5]`.

Таким образом, вариант B является правильным.
