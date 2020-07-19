
# Install Python 3.x

Getting your Python setup right on your system is important.
Otherwise you find yourself in the realm of confusing error messages.
This documents focuses on getting Python 3 up and running on
Debian/Ubuntu Linux based systems as well as on macOS via MacPorts.
Your milleage may very.

> If you are running on an Intel style processor (e.g. most Macs and Windows
> machines) you can use a Python distribution called [Miniconda](https://docs.conda.io/en/latest/miniconda.html).
> This is often the easiest approach to getting a modern Python on your machine. Otherwise continue
> on reading.

## Python versions issues

It is possible to use your default OS provided python if it is version
greater than 3.x. Many distributions still ship with version 2.7 out of the box
and pipy's pip corresponding to version 2.7. On some systems, a version of 3.x
is available using the commands `python3` and `pip3`. Others let you install 
Python 3 and its pip via their package manager and use the package manager
select default versions and/or names. This is true on Debian/Ubuntu based systems as
well as macOS's MacPorts.


## Getting the right Python and Pip

### Debian/Ubuntu

Debian based systems still ship with older versions of Python by
default. We want to use a modern Python 3.x. Make sure it is 
installed and available along with the related version of pip.

```
    sudo apt install python3 python3-pip
```

### macOS with MacPorts

If you are using macOS and MacPorts you can take a similar
approach (presumably Homebrew for macOS uses the Debian
style commands)

```
    sudo port install python38
    sudo port install py38-pip
```

At this point you should be able to envoke the Python interpreter
using the `python3` command. You should see the version
of python and pip with these commands.

```
    python3 --version
    python3 -m pip --version
```

### Install Python modules using the right pip

Often you'll need some additional modules with your
Python development environment. To make sure we're using the right
Python and pip you can use the `-m` interpreter option to 
install the desired module.  Example of installing `py_dataset`
and Elasticsearch python modules.

```shell
    python3 -m pip install py_dataset
    python3 -m pip install elasticsearch
```

