### `question_689.md`

**Вопрос 689.** Дан массив строк `words`. Разработайте алгоритм, который возвращает новый список, содержащий только те строки, которые могут быть набраны с помощью клавиш только одной строки на стандартной QWERTY-клавиатуре.

**Пример:**
```
Ввод: words = ["Hello","Alaska","Dad","Peace"]
Вывод: ["Alaska","Dad"]

Ввод: words = ["omk"]
Вывод: []
```

-  A.  Для решения задачи необходимо использовать вложенные циклы и для каждого слова проверять, из какой строки оно.
-   B. Для решения задачи нужно использовать регулярные выражения.
-   C. Для решения задачи нужно  создать множество символов для каждого ряда клавиатуры и проверять для каждого слова, что все его символы есть только в одном из этих множеств.
-   D.  Для решения задачи можно сначала отсортировать список слов по их длине и затем проверять их.

**Правильный ответ: C**

**Объяснение:**

Для решения задачи отбора слов, которые можно набрать на одной строке клавиатуры, оптимальным подходом будет создание множеств для каждой строки и последующая проверка каждого слова на принадлежность символов к одному множеству.

*   **Алгоритм с множествами:**
    1. **Создание множеств:** Создаются множества (sets) символов для каждого ряда клавиатуры.
    2.  **Итерация по словам:** Проходим по каждому слову в массиве `words`.
    3. **Проверка принадлежности к строке:**  Проверяем, что все символы каждого слова,  принадлежат одному из множеств.
     *  Для этого преобразовываем слово в множество и проверяем, что пересечение с каждым рядом клавиатуры дает либо множество символов слова, либо пустой set, так как оно должно содержаться  только в одной строке.
     * Если это условие выполняется, то добавляем слово в результирующий список.
    4. **Результат:** Возвращаем отфильтрованный список строк.

* **Преимущества алгоритма:**
    * **Эффективный поиск:**  Множества обеспечивают быстрый поиск (O(1) average time complexity)  при проверке наличия элементов.
    * **Простота:** Код становится более  читаемым и лаконичным.

**Примеры (псевдокод):**
```
function find_words_from_keyboard_row(words):
    row1 = {'q', 'w', 'e', 'r', 't', 'y', 'u', 'i', 'o', 'p'}
    row2 = {'a', 's', 'd', 'f', 'g', 'h', 'j', 'k', 'l'}
    row3 = {'z', 'x', 'c', 'v', 'b', 'n', 'm'}

    result = []
    for word in words:
       word_set = set(word.lower())
       if word_set.issubset(row1) or  word_set.issubset(row2) or word_set.issubset(row3):
         result.append(word)
    return result
```
**Примеры реализации в Python:**
```python
def find_words_from_keyboard_row(words):
    row1 = {'q', 'w', 'e', 'r', 't', 'y', 'u', 'i', 'o', 'p'}
    row2 = {'a', 's', 'd', 'f', 'g', 'h', 'j', 'k', 'l'}
    row3 = {'z', 'x', 'c', 'v', 'b', 'n', 'm'}

    result = []
    for word in words:
       word_set = set(word.lower())
       if word_set.issubset(row1) or  word_set.issubset(row2) or word_set.issubset(row3):
         result.append(word)
    return result
words = ["Hello","Alaska","Dad","Peace"]
print(f"Вход: words = {words}")
print(f"Выход: {find_words_from_keyboard_row(words)}") # Выведет ['Alaska', 'Dad']

words2 = ["omk"]
print(f"Вход: words = {words2}")
print(f"Выход: {find_words_from_keyboard_row(words2)}")  # Выведет: []

words3 = ["adsf","qwer","mxcv","asdfghjkl", "qwertyuiop"]
print(f"Вход: words = {words3}")
print(f"Выход: {find_words_from_keyboard_row(words3)}") # Выведет: ['adsf', 'qwer', 'mxcv', 'asdfghjkl', 'qwertyuiop']
```
**Разбор вариантов:**
*   **A. Для решения задачи необходимо использовать вложенные циклы и для каждого слова проверять, из какой строки оно.:** Неправильно. Хотя и можно использовать циклы, множества обеспечивают более эффективное решение.
*   **B. Для решения задачи нужно использовать регулярные выражения.:** Неправильно.
*  **C. Для решения задачи нужно  создать множество символов для каждого ряда клавиатуры и проверять для каждого слова, что все его символы есть только в одном из этих множеств.:** Правильно.
* **D. Для решения задачи можно сначала отсортировать список слов по их длине и затем проверять их.:** Неправильно.

**В результате:**
*  Создание множества символов для каждой строки клавиатуры, позволяет эффективно проверить, является ли слово набранным  с одной строчки.
*  Множества обеспечивают быстрый поиск и проверку вхождения элементов.

Таким образом, правильным ответом является **C. Для решения задачи нужно  создать множество символов для каждого ряда клавиатуры и проверять для каждого слова, что все его символы есть только в одном из этих множеств.**