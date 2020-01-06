# Install instructions

## Set up repos
```
$ git submodule update --init
$ cd external/cartopy
$ git checkout tags/0.17.0  # .gitmodules won't check out tags
$ cd -
```

## Install most Python deps
```
$ pipenv install --dev
$ pipenv shell
```

## Build Cartopy
```
$ apt install proj-bin libproj-dev libgeos-dev
$ cd external/cartopy
$ python setup.py build_ext -I$GEOS_INC -L$GEOS_LIB
$ python setup.py install
```

Download the remaining course materials from [the NOAA website](https://coastwatch.noaa.gov/cw/oceans.html)
