# KPI
![DEMO](https://i.imgur.com/D9w8YF0.png)

The Official package manager for KOOMPI & KRAMA OS

## Objectives

There a point that bring every package in one place.

kpi is based on the design of [yaourt](https://github.com/archlinuxfr/yaourt), [apacman](https://github.com/oshazard/apacman), [pacaur](https://github.com/rmarquis/pacaur), [yay](https://github.com/Jguer/yay). We're arming to:

* Provide an interface for pacman
* Yaourt-style interactive search/install
* Minimal dependencies
* Minimize user input
* Know when git packages are due for upgrades
* Combine all cambodia packages in one place


## Features

* Perform advanced dependency solving
* Download PKGBUILDs from ABS or AUR
* Tab-complete the AUR
* Query user up-front for all input (prior to starting builds)
* Narrow search terms (`kpi linux header` will first search `linux` and then narrow on `header`)
* Find matching package providers during search and allow selection
* Remove make dependencies at the end of the build process
* Run without sourcing PKGBUILD

## Installation

You may need to clone from our repo and some done : 
```sh
git clone https://github.com/LyhourChhen/kpi.git
cd kpi
make 
sudo make install
```

### Dependencies

kpi depends on:

* go (make only)
* git
* base-devel

Note: kpi also depends on a few other projects (as vendored dependencies). These
projects are stored in `vendor/`, are built into yay at build time, and do not
need to be installed separately. These files are managed by
[dep](https://github.com/golang/dep) and should not be modified manually.

Following are the dependencies managed under dep:

* https://github.com/Jguer/go-alpm
* https://github.com/Morganamilo/go-srcinfo
* https://github.com/Morganamilo/go-pacmanconf
* https://github.com/mikkeloscar/aur

### Building

Run `make` to build kpi. This command will generate a binary called `kpi` in
the same directory as the Makefile.

Note: kpi's Makefile sources its dependencies from `vendor/`. When
building manually, dependencies will instead be sourced from `GOPATH`. To
build against `vendor/` you must specify `-mod=vendor` in the build command.


### Testing

Run `make test` to test kpi. This command will verify that the code is
formatted correctly, run the code through `go vet`, and run unit tests.


