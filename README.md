# boot-fingerprint

Boot task to add a cache-buster query parameter 'fingerprint' to asset
references in html files. Asset references to be fingerprinted must be
wrapped in Enlives `replace-var` syntax. The asset fingerprint is
based on the sha1 of the asset file.

For example:

    <link rel="stylesheet" src="${css/main.css"} />

Assets dynamically created through other boot tasks can be included in
asset fingerprinting through task composition.

[![Clojars Project](http://clojars.org/boot-fingerprint/latest-version.svg)](http://clojars.org/boot-fingerprint)

## Usage

### Terminal

```
boot fingerprint
```
To re-fingerprint on changes, use boot's watch task:

```
boot watch fingerprint
```

### build.boot file

```clojure
(deftask run
  []
  (comp (watch) (fingerprint)))
```

## Examples

Refer to the examples directory for static and dynamic examples.

## Options

There are no options.

## Attribution

This project was inspired by [boot pages](https://github.com/DanThiffault/boot-pages) and the fingerprinting
implementation is an adaptation of the implementation found there.

## License

Copyright Point Slope, LLC 2015.

Distributed under the Eclipse Public License either version 1.0 or (at
your option) any later version.
