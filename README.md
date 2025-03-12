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

- Support for non-unique keys using `Decoder#UniqueKeys`

Compatibility
-------------

The yaml package supports most of YAML 1.2, but preserves some behavior
from 1.1 for backwards compatibility.

Specifically, as of v3 of the yaml package:

- YAML 1.1 bools (_yes/no, on/off_) are supported as long as they are being
  decoded into a typed bool value. Otherwise they behave as a string. Booleans
  in YAML 1.2 are _true/false_ only.
- Octals encode and decode as _0777_ per YAML 1.1, rather than _0o777_
  as specified in YAML 1.2, because most parsers still use the old format.
  Octals in the  _0o777_ format are supported though, so new files work.
- Does not support base-60 floats. These are gone from YAML 1.2, and were
  actually never supported by this package as it's clearly a poor choice.

and offers backwards
compatibility with YAML 1.1 in some cases.
1.2, including support for
anchors, tags, map merging, etc. Multi-document unmarshalling is not yet
implemented, and base-60 floats from YAML 1.1 are purposefully not
supported since they're a poor design and are gone in YAML 1.2.

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

