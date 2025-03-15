# YAML support for the Go language

> This is a fork of the [gopkg.in/yaml.v3](https://gopkg.in/yaml.v3) package.

Introduction
------------

The yaml package enables Go programs to comfortably encode and decode YAML
values. It was developed within [Canonical](https://www.canonical.com) as
part of the [juju](https://juju.ubuntu.com) project, and is based on a
pure Go port of the well-known [libyaml](http://pyyaml.org/wiki/LibYAML)
C library to parse and generate YAML data quickly and reliably.

As the YAML library is pretty much unmaintained and I needed to support non-unique keys,
I decided to fork the project and maintain it myself.

Difference to the original project
----------------------------------

- Support for non-unique keys using `Decoder#UniqueKeys`.
- Provide mapping of nodes in a line using `Decoder#LineNumberMapping`, when activated with
  `Decoder#WithLineNumberMapping` before decoding.

Compatibility
-------------

This package is fully compatible with the original [yaml.v3](https://gopkg.in/yaml.v3) package
and can be used as a drop-in replacement.

It only adds additional features and does not change the existing API to ensure compile time compatibility.

Installation and usage
----------------------

The import path for the package is *github.com/timo-reymann/go-yaml*.

To install it, run:

```sh
go get github.com/timo-reymann/go-yaml
```

And replace the yaml package in your go.mod:

```text
replace gopkg.in/yaml.v3 => github.com/timo-reymann/go-yaml <version>
```

API documentation
-----------------

If opened in a browser, the import path itself leads to the API documentation:

- [pkg.go.dev/github.com/timo-reymann/go-yaml](https://pkg.go.dev/github.com/timo-reymann/go-yaml)

API stability
-------------

The package API for the package will remain stable.

License
-------

The yaml package is licensed under the MIT and Apache License 2.0 licenses.
Please see the LICENSE file for details.

