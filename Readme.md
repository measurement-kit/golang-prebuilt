# Measurement Kit Prebuilt Libs for Golang

This repository contains pre-compiled static libraries for Measurement
Kit. We would normally use our [measurement-kit/prebuilt](
https://github.com/measurement-kit/prebuilt) repository (and
specifically its
[releases](https://github.com/measurement-kit/prebuilt/releases))
to publish prebuilt binaries, however the Golang build does not
support invoking any shell script to fetch binaries. Hence, this
repository that contains the binaries that you would get by calling
the `./install` script in our [measurement-kit/script-build-unix](
https://github.com/measurement-kit/script-build-unix) repository,
i.e. the repository that we use to cross compile Measurement Kit
and its dependencies on Unix and Mingw systems.

This repository is used by [measurement-kit/golang-measurement-kit](
https://github.com/measurement-kit/golang-measurement-kit) to actually
build golang binaries for the platforms and architectures for which
we want to have Measurement Kit Golang binaries.

The prebuilt dependencies are published as assets to the releases.

The latest release is currently: 0.9.0-alpha.2-1

## Windows

```
(cd script-build-unix && git pull origin master)
grep mingw ./script-build-unix/SHA256SUMS
./script-build-unix/install <packages-found-by-grepping>
git rm -rf ./mingw
mv MK_DIST/mingw ./mingw
rm -f *.tar.gz
git add ./mingw
git commit -am "Update prebuilt Windows packages"
```

Calling `./script-build-unix/install` installs the specified binaries into
the `./MK_DIST` folder. The following commands move the binaries outside
of `./MK_DIST` into the `./mingw` folder, which we make sure does not contain
anything to avoid adding too many binaries in there.

When passing packages name to `./script-build-unix/install`, make sure you
remove the `.tar.gz` extension. Binaries are validated against their SHA256 sum
when downloaded. For additional clarity, here's an example of running
`./script-build-unix/install` with the most current packages in the moment
in which this Readme.md file is being updated:

```
# NOTE: Just an example, use most current packages please!
./script-build-unix/install mingw-geoip-api-c-1.6.12-2 mingw-libressl-2.6.4-3  \
  mingw-libevent-2.1.8-3 mingw-measurement-kit-0.9.0-alpha-3
```
