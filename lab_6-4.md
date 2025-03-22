```python
import pandas as pd

transaction = [120, -31, '20.1', 12.3, 'bank', 12, -4, -7, 150, 'mr.', 23, 32, 21]

# Создание Series с индексами от 10 до 22 включительно
t = pd.Series(transaction, index=range(10, 23))

# Отбор только целых чисел (типа int)
t = t[t.apply(lambda x: isinstance(x, int))]

# Вычисление несмещённой дисперсии и среднего значения
variance = t.var(ddof=1)
mean = t.mean()

print("Дисперсия:", variance)
print("Среднее:", mean)

```
