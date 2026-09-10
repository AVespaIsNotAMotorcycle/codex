# Tensor

Essentially an array or matrix with an arbitrary number of dimensions.
Can be created from a numpy array and vice versa.
Same for python lists.

## Methods:
- size(): returns the shape of the tensor.
- squeeze(): all dimensions of size 1 are removed
  e.g. [5, 1, 3, 1, 7] => [5, 3, 7]
- requires_grad_(bool b): toggles whether to compute a gradient of the
  loss function with respect to this tensor. Can also be set with the
  `requires_grad` kwarg of `__init__`
- backward(): computes the gradient of the tensor wrt graph leaves. That is,
  other tensors which
  - are inputs used to compute this output tensor, and
  - have `requires_grad=True`
  Each `backward` call resets the *directed acyclic graph (DAG)*, so it must
  be calculated again with a new forward pass.
  If passed a vector as an argument, `backward` will assume that the vector
  is an input for which it will create a Jacobian product.

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
- grad: gradient of the loss function wrt the tensor. Set by calling .backward()
  on a loss object which was initialized with this tensor. Only available if
  `requires_grad` is `True`
- grad_fn: reference to the backward propogation function. Keeps track of how
  this particular tensor relates to leaf nodes (inputs) and root nodes (outputs).
  If `backward()` is called, this function is used to compute the gradient. i.e.,
  this function is the derivative of the loss with respect to this tensor, and
  backward calculates the derivative for a given loss.
