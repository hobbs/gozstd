[![Build Status](https://travis-ci.org/valyala/gozstd.svg)](https://travis-ci.org/valyala/gozstd)
[![GoDoc](https://godoc.org/github.com/valyala/gozstd?status.svg)](http://godoc.org/github.com/valyala/gozstd)
[![Go Report](https://goreportcard.com/badge/github.com/valyala/gozstd)](https://goreportcard.com/report/github.com/valyala/gozstd)
[![codecov](https://codecov.io/gh/valyala/gozstd/branch/master/graph/badge.svg)](https://codecov.io/gh/valyala/gozstd)

# gozstd - go wrapper for [zstd](http://facebook.github.io/zstd/)


## Features

  * Vendors upstream [zstd](https://github.com/facebook/zstd) without any modifications.
  * [Simple API](https://godoc.org/github.com/valyala/gozstd).
  * Optimized for speed. The API may be easily used in zero allocations mode.
  * `Compress*` and `Decompress*` functions are optimized for high concurrency.
  * Proper [Writer.Flush](https://godoc.org/github.com/valyala/gozstd#Writer.Flush)
    for network apps.
  * Supports [zstd dictionaries](https://github.com/facebook/zstd#the-case-for-small-data-compression)
    for better small data compression.


## Quick start


### How to install `gozstd`?

```
go get -u github.com/valyala/gozstd
```

### How to compress data?

The easiest way is just to use [Compress](https://godoc.org/github.com/valyala/gozstd#Compress):

```go
	compressedData := Compress(nil, data)
```

There is also [StreamCompress](https://godoc.org/github.com/valyala/gozstd#StreamCompress)
and [Writer](https://godoc.org/github.com/valyala/gozstd#Writer) for stream compression.

### How to decompress data?

The easiest way is just to use [Decompress](https://godoc.org/github.com/valyala/gozstd#Decompress):

```go
	data, err := Decompress(nil, compressedData)
```

There is also [StreamDecompress](https://godoc.org/github.com/valyala/gozstd#StreamDecompress)
and [Reader](https://godoc.org/github.com/valyala/gozstd#Reader) for stream decompression.


## FAQ

  * Q: _Which go version is supported?_
    A: `go1.10` and newer. Pull requests for older go versions support
       are accepted.

  * Q: _Which platforms/architectures are supported?_
    A: `linux/amd64`. Pull requests for other platforms/architectures support
       are accepted.
