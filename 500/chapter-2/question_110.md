### `question_110.md`

**Глава2. Вопрос 10.** Каково основное применение функции `zip()` в управлении потоком цикла `for` в Python?

A.  Она завершает цикл, как только все элементы в любом из итераторов будут исчерпаны.
B.  Она объединяет несколько списков в один, упрощая итерацию по нескольким последовательностям в одном цикле `for`.
C.  Она извлекает первый элемент из каждого переданного итератора, пропускает остальные и переходит к следующему набору элементов.
D.  Она используется для создания списка булевых значений, указывающих, какие элементы цикла соответствуют определенному условию.

**Правильный ответ: B**

**Объяснение:**

Функция `zip()` в Python используется для объединения нескольких итерируемых объектов (списков, кортежей и др.) в один итерируемый объект, который представляет собой последовательность кортежей. Каждый кортеж содержит элементы из соответствующих позиций каждого итерируемого объекта.

*   **Вариант A** не верен: Функция `zip` не завершает цикл,  она просто прекращает итерирование, когда один из итерируемых объектов закончился.
*   **Вариант B** верен: Функция `zip` объединяет элементы из нескольких итерируемых объектов в кортежи, что упрощает параллельную итерацию по ним.
*   **Вариант C** не верен: Функция `zip` не пропускает элементы, а объединяет их по их индексам.
*   **Вариант D** не верен: Функция `zip` не генерирует список булевых значений.

**Как работает `zip()`:**

1.  Принимает на вход несколько итерируемых объектов (списки, кортежи и т.д.).
2.  Возвращает итератор, который производит кортежи.
3.  Каждый кортеж содержит элементы с одинаковым индексом из переданных последовательностей.
4.  Количество итераций ограничено наименьшей последовательностью.

**Использование `zip()` в циклах `for`:**

*   Позволяет итерировать по нескольким последовательностям одновременно.
*   Можно использовать для параллельной обработки данных, когда нужно одновременно обрабатывать элементы с одинаковым индексом из нескольких последовательностей.

**Пример:**

```python
names: list[str] = ["Alice", "Bob", "Charlie"]
ages: list[int] = [25, 30, 35]
cities: list[str] = ["New York", "London", "Paris"]

# Итерация по нескольким спискам одновременно
for name, age, city in zip(names, ages, cities):
    print(f"{name} is {age} years old and lives in {city}")
# Вывод:
# Alice is 25 years old and lives in New York
# Bob is 30 years old and lives in London
# Charlie is 35 years old and lives in Paris

# Пример с созданием словаря
data: dict[str, int] = dict(zip(names, ages))
print(data) # Вывод: {'Alice': 25, 'Bob': 30, 'Charlie': 35}
```

**В результате:**

*   Цикл `for` итерируется по трем спискам одновременно, извлекая имя, возраст и город для каждого человека, используя `zip()`.
*   `zip()` возвращает итерируемый объект, который был сконвертирован в словарь.
  
Таким образом, **вариант B** является верным ответом.