### `question_111.md`

**Вопрос 11.** Чем отличается цепочка `if-elif-else` от серии операторов `if` в Python при обработке множественных условий?

- A.  `if-elif-else` выполняет только один блок кода из нескольких условий, в то время как множественные инструкции `if` могут выполнить все блоки кода, условия которых выполняются.
- B.  Нет никакой разницы; оба варианта вычисляют все предоставленные условия и выполняют один и тот же блок кода.
- C.  Множественные инструкции `if` используются для проверок одного условия, тогда как `if-elif-else` используется для множественных, не связанных между собой условий.
- D.  `if-elif-else` может выполнять несколько блоков кода последовательно без переоценки условий.

**Правильный ответ: A**

**Объяснение:**

В Python условные операторы `if`, `elif` (сокращение от "else if") и `else` позволяют создавать сложные конструкции для проверки нескольких условий. Ключевая разница между использованием цепочки `if-elif-else` и серии отдельных операторов `if` заключается в том, как они обрабатывают проверку и выполнение блоков кода.

*   **Вариант A** верен: `if-elif-else` выполняет только один блок кода из всех, тогда как несколько `if` выполнят все блоки, чьи условия будут `True`.
*   **Вариант B** не верен: Каждый из вариантов ведет себя по-разному, в отличии от выбора между `if-elif-else` и серии `if` операторов.
*   **Вариант C** не верен: и  `if-elif-else`, и отдельные `if` могут обрабатывать любые условия.
*   **Вариант D** не верен: `if-elif-else` выполняет только один из блоков, а не выполняет их последовательно.

**Как работает `if-elif-else`:**

1.  Сначала вычисляется условие в операторе `if`.
2.  Если условие `if` истинно, то выполняется соответствующий блок кода, а все остальные блоки `elif` и `else` пропускаются.
3.  Если условие `if` ложно, проверяется условие в первом операторе `elif`.
4.  Если условие `elif` истинно, выполняется соответствующий блок кода, а все остальные блоки пропускаются.
5.  Этот процесс повторяется для каждого `elif`, пока не будет найдено условие, которое является истинным, или пока не будет достигнут блок `else`.
6. Если ни одно из условий `if` или `elif` не является истинным, выполняется блок `else`.

**Как работают последовательные операторы `if`:**

1.  Каждый оператор `if` проверяется независимо.
2.  Блок кода каждого оператора `if` выполняется только в том случае, если его условие истинно.
3.  Если несколько условий истинны, то выполнятся несколько соответствующих блоков кода.

**Пример:**

```python
x: int = 10
print("Пример if-elif-else:")
if x > 15:
  print("x больше 15")
elif x > 5:
  print("x больше 5, но не больше 15") # Вывод: x больше 5, но не больше 15
elif x > 0:
  print("x больше 0, но не больше 5")
else:
  print("x <= 0")

print("Пример последовательных if:")
if x > 15:
  print("x больше 15")
if x > 5:
  print("x больше 5") # Вывод: x больше 5
if x > 0:
    print("x больше 0") # Вывод: x больше 0
```
**В результате:**
*  В примере `if-elif-else`, только один блок выполняется. После того как условие `x > 5` было истинным, другие `elif` и `else` не проверяются.
*  В примере с отдельными `if` операторами, проверяются все условия, и выводятся соответствующие результаты.

Таким образом, **вариант A** является верным.