Utils to build autoconf-archive for CentOS
==========================================

If you need autoconf-archive on CentOS, there is no package available to Yum for install. This repository addresses this issue with a script that builds an RPM package from source and installs it.

Usage
-----

Just execute the `install` script with an optional `autoconf-archive` version.

    ./install 2016.09.16

The version defaults to `2016.09.16`.


Thanks \& See Also
------------------

* Repository inspired by [wendall911's earlier work](https://github.com/wendall911/autoconf-archive), which also explains using Mock.
* Also inspired by [meltwater's work](https://github.com/meltwater/autoconf-archive-rpm), which is cleaner at this stage, as self-contained.
