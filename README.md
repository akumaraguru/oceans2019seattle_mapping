# Install instructions

## Set up repos
$ git submodule update --init

## Install most Python deps
$ pipenv install --dev
$ pipenv shell

## Build GEOS from source
$ apt install proj-bin libproj-dev
$ cd external/geos
$ mkdir -p build build/install
$ cd build
$ cmake -DCMAKE_INSTALL_PREFIX="$(pwd)/install" ..
$ make
$ make install
$ GEOS_LIB="$(pwd)/install/lib"
$ GEOS_INC="$(pwd)/install/include"

## Build Cartopy
$ cd external/cartopy
$ python setup.py build_ext -I$GEOS_INC -L$GEOS_LIB
$ python setup.py install
