### `question_780.md`

**Вопрос 780.** Как в Python можно осуществить поиск подстроки в строке с помощью регулярных выражений? Опишите как работают методы `re.findall()` и `re.match()`.

-  A. Метод `re.findall()` ищет первое вхождение подстроки, а метод `re.match()` проверяет соответствие всей строки шаблону.
-   B. Метод `re.findall()` используется для поиска всех перекрывающихся вхождений, а `re.match()` -  неперекрывающихся.
-   C. Метод `re.findall()` используется для поиска всех вхождений подстроки в строке,  а метод  `re.match()` используется для поиска соответствия с начала строки.
-   D.  Метод `re.findall()` возвращает только первый элемент, а  `re.match()` возвращает `None`  если нет совпадений.

**Правильный ответ: C**

**Объяснение:**

В Python для работы с регулярными выражениями (regular expressions) используется модуль `re`. В этом модуле есть  методы `re.findall()` и `re.match()`, которые выполняют  разные виды поиска подстрок.

*   **Модуль `re`:**
    *   **Регулярные выражения:** Используются для  поиска и обработки  текста по шаблону.
    *    **Функции:** Предоставляет  методы для поиска, сопоставления, разбиения и  изменения строк на основе шаблонов.
*   **Метод `re.findall(pattern, string)`:**
    *   **Поиск всех вхождений:** Ищет все неперекрывающиеся совпадения шаблона (`pattern`) в строке  (`string`).
    *  **Список результатов:** Возвращает список подстрок, которые соответствуют шаблону.
    *  **Множественные совпадения:** Может найти несколько  совпадений.
*   **Метод `re.match(pattern, string)`:**
    *  **Поиск с начала строки:** Пытается сопоставить шаблон  `pattern`  с  началом строки  `string`.
   *   **Совпадение:** Если  шаблон совпадает с начала строки, то  возвращает объект `Match`.
     *  **`None`:**  Если нету совпадений, то возвращает `None`.
    *   **Группировка:**  С помощью круглых скобок в шаблоне можно  создавать группы,  которые можно получить  с помощью  `m.groups()`.

**Примеры:**
```python
import re

# Пример 1: поиск всех вхождений с помощью re.findall
text = "He was carefully disguised but captured quickly by police."
result1 = re.findall(r"\w+ly\b", text)
print(f"Строка '{text}'. Результат re.findall: {result1}") # Выведет: Строка 'He was carefully disguised but captured quickly by police.'. Результат re.findall: ['carefully', 'quickly']

# Пример 2: сопоставление с начала строки с re.match() и группировкой
m = re.match(r"(\d+)\.(\d+)", "24.1632")
if m:
    print(f"Сопоставление с начала строки  (groups): {m.groups()}")  # Выведет: Сопоставление с начала строки  (groups): ('24', '1632')

# Пример 3: сопоставление с начала строки без группировки
m2 = re.match(r"a+", "aaaaabc")
if m2:
    print(f"Сопоставление с начала строки (group(0)): {m2.group(0)}")  # Выведет: Сопоставление с начала строки (group(0)): aaaa

# Пример 4 : поиск в строке без match
text3 = "this is a string with numbers 1234 and 5678"
print(f"re.findall(\d+ , {text3}) : {re.findall(r"\d+", text3)}") # Выведет re.findall(\d+ , this is a string with numbers 1234 and 5678) : ['1234', '5678']

# Пример 5: match в середине строки
text4 = "some other 123 string"
m3 = re.match(r"\w+\s+(\d+)", text4)
if m3:
   print(f"Сопоставление c помощью match: {m3.groups()}") # Не выведется, так как match применяется к началу
text5 = "123 some other string"
m4 = re.match(r"(\d+)\s+\w+", text5)
if m4:
   print(f"Сопоставление c помощью match: {m4.groups()}") # Выведет: Сопоставление c помощью match: ('123',)

```
**Разбор вариантов:**
* **A. Метод `re.findall()` ищет первое вхождение подстроки, а метод `re.match()` проверяет соответствие всей строки шаблону.:** Неправильно.
*   **B. Метод `re.findall()` используется для поиска всех перекрывающихся вхождений, а `re.match()` -  неперекрывающихся.:** Неправильно.
*   **C. Метод `re.findall()` используется для поиска всех вхождений подстроки в строке, а метод  `re.match()` используется для поиска соответствия с начала строки.:** Правильно.
*   **D. Метод `re.findall()` возвращает только первый элемент, а `re.match()` возвращает `None`  если нет совпадений.:** Неправильно.

**В результате:**
*  `re.findall` позволяет получить все  совпадения в строке.
* `re.match` проверяет совпадение  с начала строки,  и позволяет группировать значения.
*  Разные методы `re`  позволяют  гибко  работать со строками.

Таким образом, правильным ответом является **C. Метод `re.findall()` используется для поиска всех вхождений подстроки в строке,  а метод  `re.match()` используется для поиска соответствия с начала строки.**
