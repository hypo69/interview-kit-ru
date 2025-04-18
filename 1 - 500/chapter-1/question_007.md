### `question_007.md`
**Вопрос 7.** При создании функции в Python, которая вычисляет факториал числа с использованием рекурсии, какое из следующих определений функции реализовано правильно и соответствует принципам рекурсии?

- A  
```python
def factorial(n): 
    return n * factorial(n-1) if n > 1 else 1
```

- B  
```python
def factorial(n): return factorial(n-1) * n if n == 0 else 1
```

- C  
```python
def factorial(n): 
    factorial(n-1) * n
```

- D
```python
def factorial(n): 
    return n * factorial(n) if n > 1 else 1
    
```

**Правильный ответ: A**

**Объяснение:**

*   **Рекурсивная функция:** Рекурсивная функция — это функция, которая вызывает саму себя. Важной частью рекурсивной функции является наличие **базового случая** (base case), который прерывает рекурсию, и **рекурсивного случая**, который вызывает функцию с измененными входными данными для приближения к базовому случаю.

*   **Факториал:** Факториал числа `n` (обозначается как `n!`) — это произведение всех натуральных чисел до `n`. Например, `5! = 5 * 4 * 3 * 2 * 1 = 120`.

*   **Правильная реализация рекурсии:**
    *   **Базовый случай:** Для факториала базовым случаем является `n = 1` (или `n <= 1`, включая 0!). В этом случае факториал равен 1.
    *   **Рекурсивный случай:** Для `n > 1`, факториал вычисляется как `n * factorial(n-1)`, то есть текущее число умножается на факториал числа, меньшего на единицу.
*   **Проверка условия:** Важно чтобы вызов `factorial(n-1)` был только при `n>1`, иначе будет бесконечная рекурсия.

**Пример:**

```python
def factorial(n: int) -> int:
    if n > 1:
      return n * factorial(n-1)
    else:
      return 1


print(f"factorial(5): {factorial(5)}") # Вывод: factorial(5): 120

print(f"factorial(0): {factorial(0)}") # Вывод: factorial(0): 1

print(f"factorial(1): {factorial(1)}") # Вывод: factorial(1): 1
```

**В результате:**

*   Вариант **A** `def factorial(n): return n * factorial(n-1) if n > 1 else 1` правильно реализует рекурсивную функцию для вычисления факториала, с корректным базовым случаем и рекурсивным вызовом.
*   Вариант **B** `def factorial(n): return factorial(n-1) * n if n == 0 else 1` имеет неправильный базовый случай, который не будет обрабатывать положительные значения n.
*   Вариант **C** `def factorial(n): factorial(n-1) * n` не имеет базового случая и не возвращает значения, что приведет к бесконечной рекурсии и ошибке.
*    Вариант **D** `def factorial(n): return n * factorial(n) if n > 1 else 1` имеет бесконечную рекурсию, так как вызывает факториал от того же числа а не `n-1`.

Таким образом, ответ **A** является правильным, поскольку он содержит корректное определение рекурсивной функции, с базовым случаем и рекурсивным шагом, который уменьшает входные данные и приближает их к базовому случаю.
