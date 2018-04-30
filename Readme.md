# Measurement Kit Libs

This repository contains pre-compiled static libraries for measurement-kit

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
