# Cytnx

The Cytnx Library for Tensor Networks

## Build from source

FAQ:

If you encounter this problem during runtime, we recommend you to compile and install OpenBLAS by yourself. It seems that some of the binary package of libopenblas does not contain symbols related to LAPACKE.

```shell
ImportError: /usr/local/cytnx/cytnx.cpython-312-x86_64-linux-gnu.so: undefined symbol: LAPACKE_dstev
```
