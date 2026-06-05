[update-readmes]   Mode: rewrite — migrating to template structure...
# liquorix-package

[![Built with Ona](https://ona.com/build-with-ona.svg)](https://app.ona.com/#https://github.com/Interested-Deving-1896/liquorix-package)

<!-- AI:start:what-it-does -->
_Description pending._
<!-- AI:end:what-it-does -->

## Architecture

<!-- AI:start:architecture -->
_Architecture documentation pending._
<!-- AI:end:architecture -->

## Install

<!-- Add installation instructions here. This section is yours — the AI will not modify it. -->

```bash
git clone https://github.com/Interested-Deving-1896/liquorix-package.git
cd liquorix-package
```

## Usage


### Bootstrap Docker Images

Before any builds can be executed, the prepared docker images must be bootstrapped.  To bootstrap all supported images, execute:

```shell
./scripts/debian/docker_bootstrap.sh
```

Subsequent executions of `docker_bootstrap.sh` will update the existing images rather than performing a full build.

### Build Source and Binary Packages

The `debian/docker_build-source.sh` script require two operands, the distribution and release.  For example, to build for Ubuntu Focal, you would execute below:

```shell
./scripts/debian/docker_build-source.sh debian bookworm
```

Once complete, you need to build the binary:

```shell
./scripts/debian/docker_build-binary.sh amd64 debian bookworm
```

If the build completes successfully, the build for Debian Bookworm will be found under `artifacts/debian/bookworm`.

At this time, only AMD64 is supported and is the only architecture that will build successfully.

### Package Signing

If you run into trouble with errors for signing or don't desire signed packages, look for instances in the scripts folder of `dpkg-buildpackage` and add the `--no-sign` flag to all lines.

For example, from the root of this project, execute the following script to find all instances and edit each file as necessary:

```shell
find scripts/ -type f | xargs grep -H 'dpkg-buildpackage'
```

If signing is desired, make sure to update the changelog with `dch -i --auto-nmu` and set the author to match your signing key you set up with GnuPG.

## Configuration

<!-- Document configuration options here. This section is yours — the AI will not modify it. -->

## CI

<!-- AI:start:ci -->
_CI documentation pending._
<!-- AI:end:ci -->

## Mirror chain

<!-- AI:start:mirror-chain -->
This repo is maintained in [`Interested-Deving-1896/liquorix-package`](https://github.com/Interested-Deving-1896/liquorix-package) and mirrored through:

```
Interested-Deving-1896/liquorix-package  ──►  OpenOS-Project-OSP/liquorix-package  ──►  OpenOS-Project-Ecosystem-OOC/liquorix-package
```

Changes flow downstream automatically via the hourly mirror chain in
[`fork-sync-all`](https://github.com/Interested-Deving-1896/fork-sync-all).
Direct commits to OSP or OOC are detected and opened as PRs back to `Interested-Deving-1896`.
<!-- AI:end:mirror-chain -->

## Contributors

<!-- AI:start:contributors -->
_Contributors pending._
<!-- AI:end:contributors -->

## Origins

<!-- AI:start:origins -->
_Original project — no upstream fork._
<!-- AI:end:origins -->

## Resources

<!-- AI:start:resources -->
_No additional resource files found._
<!-- AI:end:resources -->

## License

<!-- AI:start:license -->
[GPL-2.0](https://github.com/Interested-Deving-1896/liquorix-package/blob/6.15/master/LICENSE) © 2026 [Interested-Deving-1896](https://github.com/Interested-Deving-1896)
<!-- AI:end:license -->
