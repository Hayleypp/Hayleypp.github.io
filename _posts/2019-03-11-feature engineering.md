## Dealing with data (feature engineering)

* frozenset

  : washable

    retunrs an unchageable object

  

* Join in data frame

  ```python
  for i pred_df in enumerate(pred_dfs):
      	how = "inner" if i == 0 else "left"
      	train_df = join_pred(train_df, pred_df, how=how)
     
  ```

- assert 

  : verify expectations

  ```python
  assert len(patient_columns) == len(set(patient_columns)) # verifying redundant value
  ```

  