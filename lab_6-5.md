```python
import numpy as np
import pandas as pd

# 1. Генерация 200 нормально распределённых значений
s = pd.Series(np.random.normal(size=200))

# 2. Возводим значения в квадрат и сдвигаем индексы на 2
s = s**2
s.index = s.index + 2

# 3. Количество значений больше 2
count_gt_2 = (s > 2).sum()

# 4. Сумма элементов < 2 и с нечётными индексами
mask = (s < 2) & (s.index % 2 == 1)
sum_lt_2_odd_idx = s[mask].sum()

# Выводим результаты
print("Количество значений > 2:", count_gt_2)
print("Сумма значений < 2 с нечётными индексами:", sum_lt_2_odd_idx)
```
