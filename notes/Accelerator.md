# Accelerator

An accelerator is a device used alongside a CPU to speed up computation.
Types:
- CUDA: interface for Nvidia GPUs
- MTIA: interface for Meta ASICs.
- XPU: interface for Intel GPUs.
- MPS: interface for Apple's Metal API.
  Not sure if Apple manufactures GPUs or simply has a custom API for their
  preferred GPUs.
- HPU: interface for hyperdimensional processing units, I think. No page in
  the PyTorch docs for this accelerator I fear.
- PrivateUse1: allows custom accelerator interfaces.
