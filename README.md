# numcas

**CAS for NumWorks, Modernized.**

numcas lets you run [Xcas](https://www-fourier.ujf-grenoble.fr/~parisse/giac.html) on your [NumWorks calculator](https://www.numworks.com) — modernized for current firmware, with new features on top.

[![Build](https://github.com/sdphadke/numcas/actions/workflows/build.yml/badge.svg)](https://github.com/sdphadke/numcas/actions/workflows/build.yml)

## What's new

- `steps()` — after a `factor`, `diff`, or `integrate` computation, call `steps()` (or `last_steps()`) to see a step-by-step explanation of the computation.
- Targets NumWorks firmware v26.

## Install the app

Installing is rather easy:
1. Download the latest `numcas.nwa` file from the [Releases](https://github.com/sdphadke/numcas/releases) page
2. Get a [Nwagra](https://www.nwagyu.com/pages/extended-memory/) pill
3. Head to [my.numworks.com/apps](https://my.numworks.com/apps) to send the `nwa` file on your calculator

## Build the app

To build numcas, you will need to install the [embedded ARM toolchain](https://developer.arm.com/Tools%20and%20Software/GNU%20Toolchain) and [nwlink](https://www.npmjs.com/package/nwlink).

```shell
brew install numworks/tap/arm-none-eabi-gcc node # Or equivalent on your OS
npm install -g nwlink
make clean && make build
```

The built app lands at `output/numcas.nwa`. Every push is also built automatically by GitHub Actions — grab the artifact from the Actions tab, or download a tagged release.

## Dependencies

numcas is built on four libraries:

|Library|Version|
|-|-|
|[gmp](https://gmplib.org/)|6.2.1|
|[mpfr](https://www.mpfr.org/)|4.1.0|
|[mpfi](http://perso.ens-lyon.fr/nathalie.revol/software.html)|1.5.4|
|[giac](https://www-fourier.ujf-grenoble.fr/~parisse/giac.html)|1.9.0-21|

## Credits

Forked from [nwagyu/khicas](https://github.com/nwagyu/khicas), which ports Xcas/Giac to NumWorks.
