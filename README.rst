===========
pyhessioxxx
===========

CTA Python wrapper for hessio event format that is used in output of simtel_array.

* Code: https://github.com/cta-observatory/pyhessio 

This is a temporaly solution for testing ctapipe with real CTA MC data.
It should not be used once CTA data format DL0 will be accpeted and implemented.

This package is composed of two libraries:

* libhessio: Part of sim_telarray program : https://www.mpi-hd.mpg.de/hfm/~bernlohr/sim_telarray
* pyhessio : libhessio Python wrapper


===========
Quick Start
===========

Anaconda
--------
First install Anaconda python distribution for Python3.4
http://continuum.io/downloads#py34

If you already use anaconda, but with python 2.7, you can create a
second anaconda virtual environment for python3 following the instructions here:
http://continuum.io/blog/anaconda-python-3)::
  
    # only if you already run anaconda: install a new virtualenv for
    # cta development:
    conda create -n cta python=3.4 anaconda
    source activate cta  # to switch to the cta python virtualenv

later you can switch back to your the root environment (or another) by running::
    
    source activate root  
    
Anaconda's distribution doesn't interfere with your local python
distribution if you have one, and can be installed without root
privileges. It contains all the required packages. To "activate"
Anaconda's python, just put it's bin directory in your path: (e.g.
`export PATH=$HOME/anaconda/bin:$PATH`).

After installing anaconda and setting your PATH, run the following to update the packages (for now we have no version restrictions, so the latest ones usually work)::

    conda update --all

CMake
-----
You need to install CMake to allow anaconda to build C libhessio library

https://cmake.org

build and install
-----------------
Next you need to check out the ~pyhessio~ module build it and install it::

    git clone https://github.com/cta-observatory/pyhessio
    conda build pyhessio
    conda install --use-local pyhessio
    cd pyhessio
    python setup.py develop

Note For MacOSX:
````````````````
CMake does not work with anaconda on MacOSX. 

You need to run cmake manually::

    cd pyhessio
    mkdir build
    cd build
    cmake ..
    make
    sudo make install
    cd ..
    python setup.py install

