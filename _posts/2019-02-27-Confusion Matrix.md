### Today I Learn 04

The visualisation of the performance of a classifier


```python
# import library
from sklearn.metrics import confusion_matrix
from sklearn.metrics import classification_report

#create confusion matrix
confisuon_m = confusion_matrix(gt_labels, pred_labels)

#visualisation
plt.title('Confusion Matrix')
plt.show()
```

