### `question_029.md`

**Вопрос 29.** Дан следующий словарь Python, как вы получите доступ к значению, связанному с ключом `'color'`?

```python
car = {"brand": "Ford", "model": "Mustang", "year": 1964, "color": "red"}
```

- A. `car[1]`
- B. `car.get("color")`
- C. `car[color]`
- D. `car['color']`

**Правильный ответ: D**

**Объяснение:**

В Python для доступа к значениям словаря используются ключи, заключенные в квадратные скобки.

*   **Вариант A** не верен: `car[1]` - попытается получить доступ к элементу по числовому индексу `1`, а не по ключу `'color'`. Это приведет к ошибке, поскольку словари не поддерживают числовую индексацию.

*   **Вариант B** верен: `car.get("color")` - это правильный способ доступа к значению по ключу с помощью метода `get()`, который также позволяет вернуть значение по умолчанию в случае отсутствия ключа.

*   **Вариант C** не верен: `car[color]` -  попытается использовать переменную `color`, а не строковый ключ `"color"`. Это приведет к ошибке, если переменная `color` не объявлена.

*   **Вариант D** верен:  `car['color']` -  это прямой и наиболее распространенный способ доступа к значению по ключу, заключенному в кавычки.

**Пример:**

```python
car: dict[str, str | int] = {"brand": "Ford", "model": "Mustang", "year": 1964, "color": "red"}

# Правильный способ (вариант D)
color_value_d: str = car['color']
print(f"Значение ключа 'color': {color_value_d}") # Вывод: Значение ключа 'color': red

# Правильный способ (вариант B)
color_value_b: str = car.get("color")
print(f"Значение ключа 'color': {color_value_b}")  # Вывод: Значение ключа 'color': red

# Неправильный способ (вариант A) - вызовет KeyError
try:
    color_value_a: str = car[1]
except KeyError as e:
    print(e) # Вывод: 1

# Неправильный способ (вариант C) - вызовет NameError если переменная color не объявлена
# try:
#   color_value_c = car[color] # NameError: name 'color' is not defined
# except NameError as e:
#   print(e)
```

**В результате:**

*  Варианты `B` и `D`  дают правильный результат и позволяют получить значение ключа `'color'`,  выводя на экран строку `"red"`.
*  Вариант `A` вызывает исключение `KeyError`, так как в словаре нет числовых ключей.
*  Вариант `C` вызывает исключение `NameError`, если переменная `color` не объявлена.

Таким образом, **вариант D** является наиболее распространенным и прямым способом доступа к значению по ключу в словаре, а **вариант B** является корректным, хотя и немного более многословным.
