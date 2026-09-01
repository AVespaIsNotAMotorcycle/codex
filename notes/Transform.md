# Transform

A transform is an operation carried out on either data (`transform`)
or labels (`target_transform`) to put it into the correct format for
the model. Transforms are given as kwargs to a dataset. Builtin
transforms can be found in `torchvision.transforms`.

## Built-In
- v2
  - Compose(array): takes an array of transforms and performs them in
    sequence on each element in the dataset.
  - ToImage(): converts a PIL Image or NumPy ndarray into a
    `torchvision.tv_tensors.Image` tensor.
  - ToDtype(data_type): converts the given tensor to `data_type`.
    kwargs:
    - scale: normalizes the tensor
  - Lambda(lambda_function): accepts a user-defined lambda function to
    perform on the dataset.
