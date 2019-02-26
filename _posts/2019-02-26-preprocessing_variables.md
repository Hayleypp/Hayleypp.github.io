## preprocessing



### dealing with variables

* categorical variable

  .factorize()

* numerical variable : conversion from object to integer type

  .unique() 

### data type/ map()

* self.____class____:  a reference to the type of the instance

  

  ```python
  df['monthly_closing'] = df = ['monthly_closing'].map(lambda x: 0.0 if x__class__ is float
  	else float (x.split('-')[1])).astype(np.int8)
  ```
  

  

  