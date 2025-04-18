### `question_201.md`

**Вопрос 201.** В Python, какое ключевое слово используется для создания генератора?

A. `return`
B. `yield`
C. `generator`
D. `yield from`

**Правильный ответ: B**

**Объяснение:**

Ключевое слово `yield` используется для создания генераторов в Python. Генераторы — это специальные функции, которые могут приостанавливать свое выполнение и возвращать значение, сохраняя при этом свое состояние.

*   **Вариант A** не верен: `return` завершает функцию и возвращает одно значение.
*   **Вариант B** верен: `yield` используется для создания генераторов.
*   **Вариант C** не верен: `generator` не является ключевым словом Python.
*   **Вариант D** не верен: `yield from` используется для делегирования итераций в генераторах.

**Как работает `yield`:**

1.  Функция с `yield` становится генератором.
2.  Когда вызывается функция-генератор, код функции не выполняется сразу.
3.  Генератор возвращает объект-итератор, который управляет выполнением функции.
4.  Когда вызывается метод `next()` у итератора, код функции выполняется до оператора `yield`.
5.  После `yield` выполнение приостанавливается, и возвращается значение.
6.  При следующем вызове метод `next()` выполнение возобновляется с места приостановки.

**Пример:**

```python
def my_generator(n: int):
    for i in range(n):
      yield i * 2 # приостановка и возврат значения

gen = my_generator(5)
print(next(gen)) # Вывод: 0
print(next(gen)) # Вывод: 2
print(next(gen)) # Вывод: 4
print(next(gen)) # Вывод: 6
print(next(gen)) # Вывод: 8
# print(next(gen)) # StopIteration
for value in my_generator(3):
    print(value) # Вывод:
              # 0
              # 2
              # 4

```
**В результате:**
* В функции `my_generator` ключевое слово `yield` приостанавливает выполнение функции и возвращает очередное значение.
* При использовании `next()` можно получить следующее значение генератора.
* Можно итерироваться по генератору, используя цикл `for`.

Таким образом, **вариант B** является правильным.
