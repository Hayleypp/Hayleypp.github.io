## Today I Learn 02    


```python
import pandas as pd

practice_set = pd.read_csv('../input/data_ver1.csv')

attributes = practice_set.columns[10:].tolist() # extract 10 variables by weekly basis
data_over_time = []
for i in range (len(attributes)):
	label_sum = practice_set.groupby(['time_weeklly']).[attributes[i]].agg('sum')
    over_time.append(label_sum.tolist())
```
