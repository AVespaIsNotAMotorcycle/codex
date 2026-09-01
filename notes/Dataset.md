# Dataset

Dataset stores the samples and their corresponding labels.
Any custom dataset must implement three functions:
- __init__: constructor
  kwargs:
  - transform: a function to run on the data. Built-in transforms can be found
    in `torchvision.transforms`
  - target_transform: a function to run on the labels
- __len__: returns number of samples as int
- __getitem__: given an `index` returns corresponding `sample, label`
- __iter__: not strictly required, but allows iter() to produce an iterable
