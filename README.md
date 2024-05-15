# simplebox

[![Build Status](https://github.com/brandur/simplebox/actions/workflows/ci.yaml/badge.svg?branch=master)](https://github.com/brandur/simplebox/actions) [![GoDoc](https://godoc.org/github.com/brandur/simplebox?status.png)](https://godoc.org/github.com/brandur/simplebox)

Package simplebox provides a simple, easy-to-use cryptographic API where all of
the hard decisions have been made for you in advance. The backing cryptography
is XSalsa20 and Poly1305, which are known to be secure and fast.

This package is a Golang port of the [RbNaCl module of the same name][rbnacl].

## Installation and Usage

``` sh
go get github.com/brandur/simplebox
```

Please see [godoc for usage information and examples][godoc].

## Run tests

``` sh
go test ./...
```

## Cut a release

1. Fetch changes to the repo and any new tags. Export `VERSION` by incrementing the last tag according to semantic versioning:

    ``` sh
    git checkout master && git pull --rebase
    export VERSION=v0.x.y
    ```

2. Prepare a PR with the changes, updating `CHANGELOG.md` with any necessary additions at the same time. Have it reviewed and merged.

3. Upon merge, pull down the changes, tag each module with the new version, and push the new tags:

    ``` sh
    git pull origin master
    git tag $VERSION
    git push --tags
    ```

4. Cut a new GitHub release by visiting [new release](https://github.com/brandur/simplebox/releases/new), selecting the new tag, and copying in the version's `CHANGELOG.md` content as the release body.

[godoc]: https://godoc.org/github.com/brandur/simplebox
[rbnacl]: https://github.com/cryptosphere/rbnacl/wiki/SimpleBox
