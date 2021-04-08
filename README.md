[![Build Status](https://travis-ci.com/thohemp/electrum-onion.svg?branch=master)](https://travis-ci.com/thohemp/electrum-onion)

electrum-onion - Lightweight DeepOnion client
==========================================

electrum-onion is a port of Electrum, the Bitcoin wallet, to DeepOnion.

    Licence: MIT Licence
    Original Author: Thomas Voegtlin
    Port Maintainer: thohemp
    Language: Python (>= 3.6)
    Homepage: https://deeponion.org/






Getting started
===============

electrum-onion itself is pure Python, and so are most of the required dependencies,
but not everything. The following sections describe how to run from source, but here
is a TL;DR::

    sudo apt-get install libsecp256k1-0
    python3 -m pip install --user .[gui,crypto]

Not pure-python dependencies
----------------------------

If you want to use the Qt interface, install the Qt dependencies::

    sudo apt-get install python3-pyqt5

For elliptic curve operations, `libsecp256k1`_ is a required dependency::

    sudo apt-get install libsecp256k1-0

Alternatively, when running from a cloned repository, a script is provided to build
libsecp256k1 yourself::

    sudo apt-get install automake libtool
    ./contrib/make_libsecp256k1.sh

Due to the need for fast symmetric ciphers, `cryptography`_ is required.
Install from your package manager (or from pip)::

    sudo apt-get install python3-cryptography


If you would like hardware wallet support, see `this`_.

.. _libsecp256k1: https://github.com/bitcoin-core/secp256k1
.. _pycryptodomex: https://github.com/Legrandin/pycryptodome
.. _cryptography: https://github.com/pyca/cryptography
.. _this: https://github.com/spesmilo/electrum-docs/blob/master/hardware-linux.rst

Running from tar.gz
-------------------

If you downloaded the official package (tar.gz), you can run
electrum-onion from its root directory without installing it on your
system; all the pure python dependencies are included in the 'packages'
directory. To run electrum-onion from its root directory, just do::

    ./run_electrum

You can also install electrum-onion on your system, by running this command::

    sudo apt-get install python3-setuptools python3-pip
    python3 -m pip install --user .

This will download and install the Python dependencies used by
electrum-onion instead of using the 'packages' directory.
It will also place an executable named :code:`electrum-onion` in :code:`~/.local/bin`,
so make sure that is on your :code:`PATH` variable.


Development version (git clone)
-------------------------------

Check out the code from GitHub::

    git clone git://github.com/thohemp/electrum-onion.git
    cd electrum-onion
    git submodule update --init

Run install (this should install dependencies)::

    python3 -m pip install --user -e .


Create translations (optional)::

    sudo apt-get install python-requests gettext
    ./contrib/pull_locale

Finally, to start electrum-onion::

    ./run_electrum



Creating Binaries
=================

Linux (tarball)
---------------

See :code:`contrib/build-linux/sdist/README.md`.


Linux (AppImage)
----------------

See :code:`contrib/build-linux/appimage/README.md`.


Mac OS X / macOS
----------------

See :code:`contrib/osx/README.md`.


Windows
-------

See :code:`contrib/build-wine/README.md`.


Android
-------

See :code:`contrib/android/Readme.md`.
