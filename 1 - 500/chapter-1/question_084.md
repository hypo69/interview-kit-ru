### `question_130.md`

**Вопрос 130.** Какой результат будет получен при выполнении следующего кода Python?

```python
def anagram(word1, word2):
    word1 = word1.lower()
    word2 = word2.lower()
    return sorted(word1) == sorted(word2)

print(anagram("cinema", "iceman"))
print(anagram("cool", "loco"))
print(anagram("men", "women"))
print(anagram("python", "pythno"))
```

-   A.  `True True True True`
-   B.  `True False True False`
-   C.  `False True False True`
-   D.  `True True False True`

**Правильный ответ: D**

**Объяснение:**

Этот код демонстрирует проверку слов на анаграммы, то есть на наличие одинаковых символов, но в разном порядке, с использованием Python.

1. **Функция `anagram(word1, word2)`:**
    *   Преобразует оба слова в нижний регистр с помощью `lower()` (для сравнения без учета регистра).
    *   Сортирует символы каждого слова с помощью `sorted()`.
    *  Возвращает `True`, если отсортированные списки символов равны (слова являются анаграммами), иначе `False`.

2. **Вызовы `print(anagram(...))`:**
   *  `print(anagram("cinema", "iceman"))`: `"cinema"` и `"iceman"`  являются анаграммами, так как содержат одни и те же буквы, поэтому возвращается `True`.
   *  `print(anagram("cool", "loco"))`: `"cool"` и `"loco"` являются анаграммами, так как содержат одни и те же буквы, поэтому возвращается `True`.
   *  `print(anagram("men", "women"))`: `"men"` и `"women"` не являются анаграммами, так как содержат разные буквы, поэтому возвращается `False`.
   * `print(anagram("python", "pythno"))`: `"python"` и `"pythno"`  являются анаграммами, так как содержат одни и те же буквы, поэтому возвращается `True`.

**Разбор вариантов:**
*   **A. `True True True True`**: Неправильно.
*   **B. `True False True False`**: Неправильно.
*   **C. `False True False True`**: Неправильно.
*   **D. `True True False True`**: Правильно.

**В результате:**
*   Функция `anagram` эффективно определяет, являются ли два слова анаграммами.
*   Методы строк `lower()` и функция `sorted()` помогают упростить проверку анаграмм.

Таким образом, правильным ответом является **D. `True True False True`**.
