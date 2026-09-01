# Tensor

Essentially an array or matrix with an arbitrary number of dimensions.
Can be created from a numpy array and vice versa.
Same for python lists.

## Methods:
- size(): returns the shape of the tensor.
- squeeze(): all dimensions of size 1 are removed
  e.g. [5, 1, 3, 1, 7] => [5, 3, 7]

- torch.ones_like(input_tensor): creates a tensor of the same shape as
  input_tensor, where every value is 1. Datatype is of the same as input_tensor,
  unless otherwise specified.
- torch.rand_like(input_tensor): same as torch.ones_like, except that values
  are random numbers on the interval [0, 1). The keyword argument `generator`
  can supply a `torch.Generator` to generate the numbers differently if needed.

## Properties
- shape: shape
- dtype: datatype
- device: CPU or GPU
