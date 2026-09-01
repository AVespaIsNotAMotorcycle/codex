# DataLoader

A DataLoader wraps a Dataset and provides a means of interacting with it.

`The Dataset retrieves our dataset’s features and labels one sample at a time. While training a model, we typically want to pass samples in “minibatches”, reshuffle the data at every epoch to reduce model overfitting, and use Python’s multiprocessing to speed up data retrieval.

DataLoader is an iterable that abstracts this complexity for us in an easy API.`

## Methods:
- __init__: constructor
  Args:
  - data: a Dataset
  - batch_size: # of samples per batch
  - shuffle: boolean. If true, randomly reorder the data each epoch.
