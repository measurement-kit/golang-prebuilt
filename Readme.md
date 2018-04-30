# Measurement Kit Prebuilt Libs for Golang

This repository contains pre-compiled static libraries for Measurement
Kit. We would normally use our [measurement-kit/prebuilt](
https://github.com/measurement-kit/prebuilt) repository (and
specifically its
[releases](https://github.com/measurement-kit/prebuilt/releases)
to publish prebuilt binaries, however the Golang build does not
support invoking any shell script to fetch binaries. Hence, this
repository that contains the binaries that you would get by calling
the `./install` script in our [measurement-kit/script-build-unix](
https://github.com/measurement-kit/script-build-unix) repository,
i.e. the repository that we use to cross compile Measurement Kit
and its dependencies on Unix and Mingw systems.

## Windows

```
(cd script-build-unix && git pull origin master)
grep mingw ./script-build-unix/SHA256SUMS
./script-build-unix/install <packages-found-by-grepping>
git rm -rf ./mingw
mv MK_DIST/mingw ./mingw
rm -f *.tar.gz
git add ./mingw
```

Example of running `./script-build-unix/install` valid in the moment in
which this file is being updated:

```
./script-build-unix/install mingw-geoip-api-c-1.6.12-2 mingw-libressl-2.6.4-3  \
  mingw-libevent-2.1.8-3 mingw-measurement-kit-0.9.0-alpha-3
```
