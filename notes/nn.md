# torch.nn

- nn.Flatten(tensor): collapses all dimensions from `start` to end.
  kwargs:
  - start = 1
  - end = -1
  ex. given a tensor of size (32, 1, 5, 5), nn.Flatten => (32, 25)
  ex. given the same tensor, nn.Flatten(start=0) => (800,)
  ex. given the same tensor, nn.Flatten(0, 2) => (100, 5)
- nn.Module: base class for models, layers, anything that takes in
  vectors and puts out vectors, basically. Can contain other Modules
  within it. For example, a Module representing a feed-forward neural
  network may contain Modules representing linear layers and activation
  functions.
- nn.Linear: multiplies an input tensor by weights and adds biases.
- nn.ReLU: applies the ReLU activation function to an input tensor.
- nn.Sequential: an ordered container of modules. The constructor takes
  a list of modules as arguments (not a python List, just a set of args)
  and then when you call the object it passes the input through each
  module in order.
  ex.
  `seq = nn.Sequential(a, b, c)
   out = seq(in)
   out == c(b(a(in)))`
- nn.Softmax: applies softmax function to the input.
  `Softmax(x_i) = e^(x_i) / (e^(x_1) + ... + e^(x_j))`
  for each x_i in a set of j elements.
  Produces a set of probabilities that sum to 1.
