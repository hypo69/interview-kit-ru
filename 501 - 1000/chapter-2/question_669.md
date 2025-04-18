### `question_669.md`

**Вопрос 669.** Как можно удалить дубликаты из несортированного связанного списка в Python? Опишите два подхода к решению этой задачи: с использованием двух указателей и с использованием хеш-таблицы (множества).

-   A. Для удаления дубликатов из связного списка нужно сначала отсортировать список, а затем удалить дубликаты.
-   B. Удаление дубликатов возможно только с помощью рекурсии, так как нужно отслеживать уже посещенные элементы.
-   C. Удаление дубликатов возможно с помощью движения по списку используя два указателя, или используя хеш-таблицы (множества).
-   D. Для удаления дубликатов используется метод `remove_duplicates()`, который можно использовать только для отсортированных списков.

**Правильный ответ: C**

**Объяснение:**

Для удаления дубликатов из несортированного связанного списка в Python, можно использовать два основных подхода: метод с двумя указателями и метод с использованием хеш-таблицы (множества).

1.  **Метод с двумя указателями:**
    *   **Два указателя:** Используются два указателя для перемещения по списку.
    *   **`nextone` (внешний указатель):** Перемещается по списку и указывает на текущий элемент.
    *   **`runner` (внутренний указатель):** Используется для перемещения по списку, начиная с `nextone`, и поиска дубликатов для текущего элемента.
    *  **Сравнение значений:**  Если `runner` находит дубликат значения, то оно удаляется.
     *  **Вложенные циклы:** Используются два вложенных цикла `while` для перебора элементов.
    *   **Изменение указателей:** Когда дубликат удаляется, указатели перенаправляются, для корректного удаления элементов.
2.  **Метод с использованием хеш-таблицы (множества):**
    *  **Множество для отслеживания уникальных значений:** Создается `set()`, чтобы отслеживать, какие элементы уже были пройдены (уникальные значения).
    *   **Перебор списка:**  Перебираем список, используя три указателя: `current` для текущего элемента, `prev` для предыдущего, и `seen` для уже пройденных значений.
    *   **Проверка и удаление:** Если текущее значение есть в множестве `seen` (дубликат), удаляется текущий элемент; если нет, то добавляется во множество и переходим к следующему элементу.

**Примеры:**
```python
# Пример структуры данных - ListNode для связного списка
class ListNode:
    def __init__(self, val, next=None):
        self.val = val
        self.next = next

# Пример 1: Удаление дубликатов с помощью двух указателей
def remove_duplicates_two_pointers(first):
   if not first:
       return

   nextone = first

   while nextone:
       runner = nextone
       while runner.next:
           if runner.next.val == nextone.val:
               runner.next = runner.next.next
           else:
               runner = runner.next
       nextone = nextone.next
   return first

# Пример 2: Удаление дубликатов с помощью хеш таблицы (множества)

def remove_duplicates_hash_table(list_head):
    if not list_head:
        return

    seen = set()
    current = list_head
    prev = None

    while current:
        if current.val in seen:
            prev.next = current.next
        else:
            seen.add(current.val)
            prev = current
        current = current.next

    return list_head


# Пример списка для тестирования
list1 = ListNode(1, ListNode(2, ListNode(3, ListNode(2, ListNode(4, ListNode(1))))))

list2 = ListNode(1, ListNode(1, ListNode(1, ListNode(1))))


# Вывод и удаление дубликатов с двух указателей
def print_list(head):
   while head:
      print(head.val, end = " ")
      head = head.next
   print("")
print("Исходный список 1:")
print_list(list1)
remove_duplicates_two_pointers(list1)
print("Список 1 без дубликатов (два указателя):")
print_list(list1) #  1 2 3 4
print("Исходный список 2:")
print_list(list2)
remove_duplicates_two_pointers(list2)
print("Список 2 без дубликатов (два указателя):")
print_list(list2) # 1


# Вывод и удаление дубликатов с хеш таблицей (множеством)
list1_copy = ListNode(1, ListNode(2, ListNode(3, ListNode(2, ListNode(4, ListNode(1))))))
list2_copy = ListNode(1, ListNode(1, ListNode(1, ListNode(1)))))

print("Исходный список 1:")
print_list(list1_copy)
remove_duplicates_hash_table(list1_copy)
print("Список 1 без дубликатов (хеш таблица):")
print_list(list1_copy) #  1 2 3 4

print("Исходный список 2:")
print_list(list2_copy)
remove_duplicates_hash_table(list2_copy)
print("Список 2 без дубликатов (хеш таблица):")
print_list(list2_copy) # 1
```
**Разбор вариантов:**
*   **A. Для удаления дубликатов из связного списка нужно сначала отсортировать список, а затем удалить дубликаты.:** Неправильно. Сортировка не обязательна.
*   **B. Удаление дубликатов возможно только с помощью рекурсии, так как нужно отслеживать уже посещенные элементы.:** Неправильно.
*  **C. Удаление дубликатов возможно с помощью движения по списку используя два указателя, или используя хеш-таблицы (множества).:** Правильно.
*   **D. Для удаления дубликатов используется метод `remove_duplicates()`, который можно использовать только для отсортированных списков.:** Неправильно.

**В результате:**
*  Оба описанных подхода (с двумя указателями и с хеш-таблицей) позволяют удалить дубликаты.
*  Выбор конкретного подхода может зависеть от эффективности и сложности реализации.
*  Метод с хеш-таблицей обычно является более оптимальным, так как имеет среднюю сложность O(n), в то время как метод с двумя указателями имеет сложность O(n^2).

Таким образом, правильным ответом является **C. Удаление дубликатов возможно с помощью движения по списку используя два указателя, или используя хеш-таблицы (множества).**
