* Global Variable & Local Variable 
  Not recommend declaration 'Global Variable' frequently

```python

sec_per_min = 60 #o ne minutes equals 60 seconds

def min_to_sec(minutes):
	seconds = minutes * sec_per_min
	return seconds
	
print(min_to_sec(3)) # 180 will be printed 
print(seconds) # Error occurs as we call local variable 

```



* the difference in between "setdefault" and "update"

  'setdefault', only possible to enter the additional pairs of key and value. 

  Even if trying to change the pair of them, nothing happen in the dictionary.
  On the contrary, 'update' being able to change both key & value

```python
week_dict = dict()
week_dict['Mon'] = 'Sunny'
week_dict['Tue'] = 'Cloudy'
week_dict['Sat'] = 'Rainy'

weather = week_dict.setdefault('Fri','Breezy')
print(week_dict) # {'Mon':'Sunny', 'Tue':'Cloudy', 'Sat':'Rainy, 'Fri':'Breezy'}

weather = week_dict.setdefault('Mon','Breezy')
print(weather) # 'Sunny'
```

