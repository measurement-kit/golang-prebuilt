# Measurement Kit Prebuilt Libs for Golang

⚠️⚠️⚠️: This repository is now unused and is being archived.

This repository contains pre-compiled static libraries for Measurement
Kit inside of a specific release. We would normally use our
[measurement-kit/prebuilt](https://github.com/measurement-kit/prebuilt)
repository (and specifically its [releases](
https://github.com/measurement-kit/prebuilt/releases))
to publish prebuilt binaries, however for historical reasons we use
this separate repository instead. We may or may not want to unify
the two repositories as part of our future work.

This repository is used by [measurement-kit/go-measurement-kit](
https://github.com/measurement-kit/go-measurement-kit) to actually
build golang binaries for the platforms and architectures for which
we want to have Measurement Kit Golang binaries. Specifically, you should
take a look to the `download-libs.sh` script in [go-measurement-kit](
https://github.com/measurement-kit/go-measurement-kit).
