go-pyjson
=========

A forked version of the golang standard library JSON parser that supports
NaN/Infinity as supported by the Python JSON implementation.

Why?
----

`NaN` and `Infinity` are not allowed by the JSON spec, but the Python JSON
implementation allows it. This is useful for interoperability with Python JSON
implementations when floating point data is being exchanged.

Here's what python does:

```pycon
>>> json.dumps([math.nan, math.inf, -math.inf])
'[NaN, Infinity, -Infinity]'
```

It seems likely that the golang project will not support adding this option
to the standard library implementation.

* https://github.com/golang/go/issues/3480
* https://github.com/golang/go/issues/25721

License
-------

This is just a modification of the standard library's JSON parser, so it is
provided under the same BSD-style license.
