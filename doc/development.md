# Development Instructions

## Building

```bash
./scripts/lein-modules do clean, install
```

## Running tests

```bash
./scripts/test.sh clj
./scripts/test.sh cljs
```

## Documentation

The documentation lives under `doc` and it is hosted on [cljdoc](https://cljdoc.org). See their
documentation for [library authors](https://github.com/cljdoc/cljdoc/blob/master/doc/userguide/for-library-authors.adoc)

## Making a release

We use [Break Versioning][breakver]. Remember our promise: patch-level bumps never include breaking changes!

[breakver]: https://github.com/ptaoussanis/encore/blob/master/BREAK-VERSIONING.md

```bash
# Check that you're using Java 8! Making the release with a newer Java version
# means that it is broken when used with Java 8.
java -version

# new version
./scripts/set-version "1.0.0"
./scripts/lein-modules install

# works
lein test

# deploy to clojars
./scripts/lein-modules do clean, deploy clojars
```
