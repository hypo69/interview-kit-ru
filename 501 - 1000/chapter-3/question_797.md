### `question_428.md`

**Вопрос 428.** Дан двумерный массив (матрица) `grid` размера `n x n`, где `1` представляет сушу, а `0` представляет воду. Известно, что в матрице ровно два острова. Разработайте алгоритм на Python для нахождения минимального количества `0`, которые нужно изменить на `1`, чтобы соединить два острова в один.

**Примеры:**

**Изображение матрицы в виде ASCII:**
```
  0 0 1 0 0
  0 1 0 1 0
  0 1 1 1 0
```

```
Ввод: grid = [[0,0,1,0,0],[0,1,0,1,0],[0,1,1,1,0]]
Вывод: 1
```
**Объяснение:** Необходимо заменить 1  `0` на `1` для соединения  острова, минимальное количество "шагов", для того чтобы коснутся другого острова.

```
Ввод: grid = [[0,0,0,0,0],[0,1,0,0,0],[0,0,0,1,0],[0,0,0,0,0]]
Вывод: 2
```
**Объяснение:** Необходимо заменить 2  `0` на `1` для соединения  острова, минимальное количество "шагов", для того чтобы коснутся другого острова.

- A.  Для решения задачи нужно использовать алгоритм  поиска в глубину (DFS) для  каждого острова, и  выбрать наименьшее кол-во шагов.
-   B. Для решения задачи нужно перебрать все возможные комбинации путей и выбрать наименьшую.
-   C. Для решения задачи необходимо использовать алгоритм  поиска в ширину (BFS), с помощью  очереди, и после обнаружения первого острова, продолжать поиск до  второго, при этом отслеживая  минимальное количество необходимых шагов.
-   D. Для решения задачи  нужно сначала отсортировать все ячейки, а потом посчитать кратчайшее расстояние.

**Правильный ответ: C**

**Объяснение:**

Для решения задачи нахождения минимального количества `0`, которые нужно изменить на `1`, чтобы соединить два острова в один, оптимальным является использование комбинации поиска в глубину (DFS) и поиска в ширину (BFS). DFS используется для нахождения первого острова и  сохранения всех  координат  в очереди, а затем BFS используется  для поиска ближайшего  пути до следующего острова, перебирая варианты последовательно.

*   **Алгоритм (DFS+BFS):**
    1.  **Поиск первого острова:**
       * Используется рекурсивный обход в глубину (DFS),  и при этом мы ищем все 1 из первого острова и меняем их значения на 2, попутно добавляя координаты  ячеек в очередь `queue`.
    2.  **Поиск кратчайшего пути (BFS):**  Используем алгоритм поиска в ширину, с помощью очереди,  для прохода по  матрице и  поиска  второго острова:
         *  Проходим по очереди, до  тех пор пока она не станет пустой:
           *   Извлекаем из очереди текущие координаты `(row, col)`  и расстояние до острова `step`
            *  Перебираем все четыре направления (`(0, 1), (1, 0), (-1, 0), (0, -1)`)  от текущих  координат.
                *  Если новые координаты  не выходят за пределы матрицы и не посещены, а  значение равно  1  - то мы достигли второго острова и можем вернуть  `step`.
              *    Если значения  равны 0, то мы  добавляем  эти координаты в  очередь и помечаем  ячейки  как посещенные (`grid[x][y] = 2`) и  увеличиваем  `step` на `1`.
    3.  **Не найден путь:**  Если очередь пуста,  то это означает что все пути  были перебраны, и  второй остров не  достижим, тогда возвращаем `-1`.

*   **Преимущества алгоритма:**
    *  **BFS для кратчайшего пути:** Использование BFS  обеспечивает поиск  кратчайшего  пути до второго острова.
    *  **DFS для первого острова:** Использование  DFS позволяет  просто  найти все ячейки первого острова.
      *    **Эффективность:** Алгоритм эффективен, поскольку  не перебирает все возможные варианты, а  гарантирует нахождение кратчайшего пути.

**Примеры (псевдокод):**

```
function find_min_bridge(grid):
    function dfs(row, col):
      if boundaries or grid[row][col] != 1
         return
        grid[row][col] = 2 # mark as seen
        queue.add([row, col,0]) # add to queue for bfs
        dfs(row-1, col); dfs(row+1, col); dfs(row, col+1);dfs(row, col -1);
   n = length(grid)
    queue = []
    for i in range(n):
       for j in range(n):
           if grid[i][j] == 1
             dfs(i,j) # start with dfs from first island
          break when found first island

     dirct = [(0, 1), (1, 0), (-1, 0), (0, -1)]
      while queue is not empty:
          x, y, step = queue.removeHead(); # remove from front
           for dx, dy in dirct:
               x1 = x+dx, y1 = y + dy
               if boundaries of matrix are invalid, continue
               if grid[x1][y1] == 1
                  return step;
              if grid[x1][y1] == 0
                 grid[x1][y1] = 2
                 queue.append([x1, y1, step + 1])

     return -1 # не найдено
```

**Примеры реализации в Python:**

```python
from collections import deque
def shortestBridge(grid):
    n = len(grid)
    queue = deque()

    def dfs(x, y):
        if not (0 <= x < n and 0 <= y < n and grid[x][y] == 1):
            return
        grid[x][y] = 2
        queue.append((x, y, 0)) # 0 - стартовая дистанция
        dfs(x - 1, y)
        dfs(x, y - 1)
        dfs(x + 1, y)
        dfs(x, y + 1)

    found = False
    for i in range(n):
        for j in range(n):
            if grid[i][j] == 1:
                dfs(i, j)
                found = True
                break
        if found:
            break
    dirct = [(0, 1), (1, 0), (-1, 0), (0, -1)]
    while queue:
        x, y, step = queue.popleft()
        for dx, dy in dirct:
            x1 = x+dx
            y1 = y+dy
            if not (0 <= x1 < n and 0 <= y1 < n):
               continue
            if grid[x1][y1] == 1:
              return step
            if grid[x1][y1] == 0:
                 grid[x1][y1] = 2 # mark as visited
                 queue.append((x1, y1, step + 1))
    return -1

grid1 = [[0,0,1,0,0,0,0,1,0,0,0,0,0],[0,0,0,0,0,0,0,1,1,1,0,0,0],[0,1,1,0,1,0,0,0,0,0,0,0,0],[0,1,0,0,1,1,0,0,1,0,1,0,0],[0,1,0,0,1,1,0,0,1,1,1,0,0],[0,0,0,0,0,0,0,0,0,0,1,0,0],[0,0,0,0,0,0,0,1,1,1,0,0,0],[0,0,0,0,0,0,0,1,1,0,0,0,0]]
print(f"Ввод: grid = {grid1}")
print(f"Вывод: {shortestBridge(grid1)}") #  Выведет 1

grid2 = [[-1]]
print(f"Ввод: grid = {grid2}")
print(f"Вывод: {shortestBridge(grid2)}")  #  Выведет -1
grid3 = [[0,0,0,0,0],[0,1,0,0,0],[0,0,0,1,0],[0,0,0,0,0]]
print(f"Ввод: grid = {grid3}")
print(f"Вывод: {shortestBridge(grid3)}")  # Выведет 2
```

**Разбор вариантов:**

*   **A. Для решения задачи нужно использовать алгоритм поиска в глубину (DFS) для каждого острова, и выбрать наименьшее кол-во шагов.:** Неправильно. DFS не гарантирует нахождение кратчайшего расстояния.
*   **B. Для решения задачи нужно перебрать все возможные комбинации путей и выбрать наименьшую.:** Неправильно, полный перебор не является оптимальным решением.
*  **C. Для решения задачи нужно использовать алгоритм поиска в ширину (BFS),  чтобы найти кратчайший путь между островами.:** Правильно, но тут необходимо уточнить, что нужно  использовать DFS  для  одного из островов.
*   **D. Для решения задачи нужно сначала отсортировать все ячейки, а потом посчитать кратчайшее расстояние.:** Неправильно,  сортировка  тут не нужна.

**В результате:**
*   Использование комбинации DFS и BFS  позволяет  эффективно решить данную задачу.
*  DFS  используется для того чтобы пометить все узлы одного из островов, и сохранить их  координаты.
*   BFS  позволяет найти  кратчайший путь от начального множества островов до второго острова.

Таким образом, правильным ответом является **C. Для решения задачи нужно использовать алгоритм поиска в ширину (BFS), с помощью  очереди, и после обнаружения первого острова, продолжать поиск до  второго, при этом отслеживая  минимальное количество необходимых шагов.**