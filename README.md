Utils to build autoconf-archive for CentOS
==========================================

If you need autoconf-archive on CentOS, there is no package available to Yum for install. This repository addresses this issue with a script that builds an RPM package from source and installs it.

Usage
-----

Just execute the `install` script with an optional `autoconf-archive` version.

    ./install 2016.09.16

The version defaults to `2016.09.16`.


Notes
-----

* Tested on CentOS 5.11 (through a Docker image: `quay.io/pypa/manylinux1_x86_64`). The script builds on the target machine, and it was inspired by spec files for CentOS 6 and 7---assuming it works fine on these platforms, as the script uses the toolchain available on the machine.
* This utility is a simple automation for creating the RPM. At this stage, it tries to keep things clean by working in a separate directory, and cleaning up all generated files before ending. It however generate files under `/usr/src/redhat/{SRPMS|RPMS}`, which is better avoided. The log output gives the full paths, if you need manual cleaning after a failure. Successful completion of the install script removes all these files.
* The spec file ends with an empty changelog section. A later version of this script could rely on [autoconf-archive's source repository](https://www.gnu.org/software/autoconf-archive/Downloads.html#Downloads) to convert the Git log into the changelog (basically run what `autoconf-archive` build process does in its `bootstrap.sh` script). This looks overkill at this stage, so dropped at first.


Thanks \& See Also
------------------

* Repository inspired by [wendall911's earlier work](https://github.com/wendall911/autoconf-archive), which also explains using Mock.
* Also inspired by [meltwater's work](https://github.com/meltwater/autoconf-archive-rpm), which is cleaner at this stage, as self-contained.
