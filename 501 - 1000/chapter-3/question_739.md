### `question_431.md`

**Вопрос 431.** Дан граф, представленный в виде списка рейсов `flights`, где `flights[i] = [from_i, to_i, price_i]` означает, что существует рейс из города `from_i` в город `to_i` со стоимостью `price_i`. Также даны исходный город `src`, целевой город `dst` и максимальное количество пересадок `k`. Разработайте алгоритм, который возвращает минимальную стоимость перелета из `src` в `dst` не более чем с `k` пересадками. Если такого маршрута не существует, вернуть `-1`.

**Представление графа в виде ASCII:**

```
      0
     /  \
  100/   \100
   1     2
 600 \ /100 \200
     3
```

**Примеры:**
```
Ввод: n = 4, flights = [[0,1,100],[1,2,100],[2,0,100],[1,3,600],[2,3,200]], src = 0, dst = 3, k = 1
Вывод: 700
Объяснение: Самый дешевый путь  0 -> 1 -> 3 (0 -> 1 с ценой 100 и 1 -> 3 с ценой 600, пересадок 1, суммарно 700)

Ввод: n = 3, flights = [[0,1,100],[1,2,100],[0,2,500]], src = 0, dst = 2, k = 1
Вывод: 200
Объяснение: Самый дешевый путь  0 -> 1 -> 2 (0 -> 1 с ценой 100 и 1 -> 2 с ценой 100, пересадок 1, суммарно 200)
```

-   A. Для решения задачи нужно использовать жадный алгоритм.
-   B. Для решения задачи нужно использовать поиск в ширину (BFS), но не учитывать ограничение k.
-   C. Для решения задачи нужно использовать алгоритм Дейкстры, не учитывая ограничения на количество пересадок.
-   D.  Для решения задачи можно использовать алгоритм поиска в ширину (BFS), и отслеживать не только расстояние (цену), но и количество пересадок.

**Правильный ответ: D**

**Объяснение:**

Для решения задачи поиска кратчайшего пути с ограничением на количество пересадок (k), используется алгоритм поиска в ширину (BFS) с использованием очереди. Данный подход позволяет не только находить кратчайший путь, но и учитывать ограничения на пересадки, предоставляя оптимальное решение.

*   **Алгоритм (BFS с ограничением пересадок):**
    1.  **Инициализация:**
        *   Создается  словарь `distances`, который будет содержать стоимость  перелета до каждого города (начальное значение всех ключей, кроме начальной точки,  равно бесконечности).  `distances[src]` = 0.
        *  Создается очередь `queue` и добавляется в нее  начальный  город и число пересадок `(src, 0)`.
        *  Сохраняется `k`  в переменную `stops`.
    2.  **BFS:** Пока очередь не пуста:
       *  Извлекаем  из очереди текущий город `current_city` и кол-во пересадок `current_stops`.
         *   **Проверка:**  Если число пересадок превышает `k`, то текущий путь не перспективный.
          *   **Итерирование по рейсам:**  Проходим по всем рейсам  `from_city, to_city, price` из `flights`.
        * **Проверка соответствия:** Если  `from_city`  равен `current_city`,  то обновляем цену до города  `to_city`, если `distances[to_city] > distances[current_city] + price`, и добавляем `to_city` в очередь с количеством остановок `stops+1`
    3.   **Результат:** После  обработки всех вариантов возвращаем `distances[dst]`, или  `-1`, если целевой город не был достигнут.

*   **Преимущества алгоритма:**
    *   **Кратчайший путь:**  BFS гарантирует нахождение кратчайшего пути.
    *   **Учет пересадок:** Алгоритм учитывает ограничение на максимальное количество пересадок.
    *  **Оптимальная сложность:** Имеет временную сложность  `O(n*m)`, где n - кол-во узлов, и `m` кол-во рейсов.

**Примеры (псевдокод):**
```
function find_cheapest_price(n, flights, src, dst, k):
    distances = a dictionary with keys of city, default to infinity
    distances[src] = 0
    queue = a queue with initial (src, 0)  # (city, stops)
    while queue is not empty:
      current_city, stops = queue.pop()
        if stops > k:
             continue
        for from_i, to_i, price in flights:
            if from_i == current_city:
              if distances[to_i] > distances[current_city] + price:
                distances[to_i] = distances[current_city] + price
                queue.add((to_i, stops +1))

    if distances[dst] is not infinity:
      return distances[dst]
    else:
      return -1
```
**Примеры реализации в Python:**

```python
from collections import deque

def find_cheapest_price(n, flights, src, dst, k):
    distances = {city: float('inf') for city in range(n)}
    distances[src] = 0
    queue = deque()
    queue.append((src, 0))  # (city, stops)

    while queue:
        current_city, stops = queue.popleft()
        if stops > k:
            continue
        for from_i, to_i, price in flights:
            if from_i == current_city:
                if distances[to_i] > distances[current_city] + price:
                   distances[to_i] = distances[current_city] + price
                   queue.append((to_i, stops +1))

    return distances[dst] if distances[dst] != float('inf') else -1


n1 = 4
flights1 = [[0,1,100],[1,2,100],[2,0,100],[1,3,600],[2,3,200]]
src1 = 0
dst1 = 3
k1 = 1
print(f"Ввод: n = {n1}, flights = {flights1}, src = {src1}, dst = {dst1}, k = {k1}")
print(f"Вывод: {find_cheapest_price(n1, flights1, src1, dst1, k1)}") # Выведет: 700


n2 = 3
flights2 = [[0,1,100],[1,2,100],[0,2,500]]
src2 = 0
dst2 = 2
k2 = 1
print(f"Ввод: n = {n2}, flights = {flights2}, src = {src2}, dst = {dst2}, k = {k2}")
print(f"Вывод: {find_cheapest_price(n2, flights2, src2, dst2, k2)}") # Выведет: 200
```
**Разбор вариантов:**

*   **A. Для решения задачи нужно использовать жадный алгоритм.:** Неправильно. Жадный алгоритм не гарантирует нахождение оптимального решения.
*  **B. Для решения задачи нужно использовать поиск в ширину (BFS), но не учитывать ограничение k.:** Неправильно, условие k - является  ключевым.
*   **C. Для решения задачи нужно использовать алгоритм Дейкстры, не учитывая ограничения на количество пересадок.:** Неправильно. Алгоритм Дейкстры не предназначен для работы с ограничением на кол-во пересадок.
*   **D. Для решения задачи можно использовать алгоритм поиска в ширину (BFS), и отслеживать не только расстояние (цену), но и количество пересадок.:** Правильно.

**В результате:**
* BFS позволяет гарантировать нахождения минимальной стоимости с учетом пересадок.
* Алгоритм не рассматривает не перспективные варианты (которые выходят за пределы ограничений).

Таким образом, правильным ответом является **D. 
Для решения задачи можно использовать алгоритм поиска в ширину (BFS), 
и отслеживать не только расстояние (цену), но и количество пересадок.**