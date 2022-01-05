# Go Get Started

Go doesn't come pre-installed, and in order to get the full features of
Go, there is some environment setup (at least on Linux).

## Linux

0. Download Go tarball
1. Run `tar -C ~/.local -xzf go1.17.5.linux-amd64.tar.gz`
1. Add the following to `~/.bashrc`

```BASH
export GOBIN="$HOME/.local/go/bin"
export GOPATH="$HOME/.local/go"
export PATH="$PATH:$GOBIN"
```

## Windows

TODO

## OSX

TODO

Related:

* Go Install Documentation
	<https://go.dev/doc/install>
* Download Go tarball
	<https://go.dev/dl/go1.17.5.linux-amd64.tar.gz>
