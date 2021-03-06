# Fortran Package Manager

This is the repository of the Fortran Package Manager (fpm).
If you are looking for the Effing Package Management instead, see
[jordansissel/fpm](https://github.com/jordansissel/fpm).

Fortran Package Manager is an early prototype.
You can use it to build and package your Fortran projects, as
well as to include supported Fortran dependency projects.
As a prototype, changes to fpm's behavior and inputs may occur as development continues.
Please follow the [issues](https://github.com/fortran-lang/fpm/issues)
to contribute and/or stay up to date with the development.
As the prototype matures and we enter production, we will do our best to stay backwards compatible.

## Getting started

### Install Haskell

To install [Haskell Stack](https://haskellstack.org/) on
Linux without root access, follow the [manual download](https://docs.haskellstack.org/en/stable/install_and_upgrade/#manual-download_2) procedure:
```
wget https://get.haskellstack.org/stable/linux-x86_64-static.tar.gz
tar xaf linux-x86_64-static.tar.gz
```
and put the `stack` binary in your path, for example:
```
export PATH="$PATH:`pwd`/stack-2.1.3-linux-x86_64-static/"
```

### Download this repository

```
git clone https://github.com/fortran-lang/fpm
cd fpm
```

### Build and Test fpm

Make sure that the development library of `gmp` is installed (e.g. `sudo apt install libgmp-dev` on Debian-derived Linux distributions)

Build fpm using:
```
stack build
```
To test:
```
stack test
```
To install:
```
stack install
```

On Linux, the above command installs `fpm` to `${HOME}/.local/bin`.

### Building your Fortran project with fpm

fpm understands the basic commands:

* `fpm build` - build your library, executables and tests
* `fpm run` - run executables
* `fpm test`- run tests

The command `fpm run` can optionally accept the name of the specific executable
to run, as can `fpm test`; like `fpm run specifc_executable`. Command line
arguments can also be passed to the executable(s) or test(s) with the option
`--args "some arguments"`.

See additional instructions in the [Packaging guide](PACKAGING.md).
