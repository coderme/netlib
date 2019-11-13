# NETLIB

`netlib` is a fork from [Gonum/netlib](https://github.com/gonum/netlib) which is in turn a wrapper providing an interface to the NETLIB C BLAS and LAPACKE implementations.

## Installation

```
  go get -d github.com/coderme/netlib/...
```


Install OpenBLAS:
```
  git clone https://github.com/xianyi/OpenBLAS
  cd OpenBLAS
  make
```

Then install the CGO BLAS wrapper package:
```sh
  CGO_LDFLAGS="-L/path/to/OpenBLAS -lopenblas" go install github.com/coderme/netlib/blas/netlib
```
or the CGO LAPACKE wrapper package:
```sh
  CGO_LDFLAGS="-L/path/to/OpenBLAS -lopenblas" go install github.com/coderme/netlib/lapack/netlib
```

For Windows you can download binary packages for OpenBLAS at
http://sourceforge.net/projects/openblas/files/

If you want to use a different BLAS package such as the Intel MKL you can
adjust the `CGO_LDFLAGS` variable:
```sh
  CGO_LDFLAGS="-lmkl_rt" go install github.com/coderme/netlib/...
```

## Packages

### blas/netlib

Binding to a C implementation of the cblas interface (e.g. ATLAS, OpenBLAS, Intel MKL)

The recommended (free) option for good performance on both Linux and Darwin is OpenBLAS.

### lapack/netlib

Binding to a C implementation of the lapacke interface (e.g. ATLAS, OpenBLAS, Intel MKL)

The recommended (free) option for good performance on both Linux and Darwin is OpenBLAS.

### lapack/lapacke

Low level binding to a C implementation of the lapacke interface (e.g. OpenBLAS or intel MKL)

The linker flags (i.e. path to the BLAS library and library name) might have to be adapted.

The recommended (free) option for good performance on both linux and darwin is OpenBLAS.

## License

Please see github.com/gonum for general license information, contributors, authors, etc on the Gonum suite of packages.
