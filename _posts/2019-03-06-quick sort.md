## Quick Sort

   


```python
def quick_sort_sub(result, s, e):
	if e - s <= 0:
    	return result
    
    
    pivot = result[e]
	i = s
	for j in range (s, e):
		if result[j] < pivot:
			result[i], result[j] = result[j], result[i]
			i += 1
	
	result[i], result[e] = result[e], result[i]
	
	# recursion
	quick_sort_sub(result, s, i-1)
	quick_sort_sub(result, i+1, e)
	
def quick_sort(result):
	quick_sort_sub(result, 0, len(result)-1)
```



​																			python for everyone