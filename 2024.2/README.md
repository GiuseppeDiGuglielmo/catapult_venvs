# Catapult 2024.2

## Linux distros

These scripts were tested with the following Linux distributions:
- Fedora 8.10 ([requirements.txt](requirements.txt))
- AlmaLinux 9.4 ([requirements.txt](requirements.txt))
- Ubuntu 22.04 ([requirements.txt](requirements.txt))
- ScientificLinux 7.9 ([requirements-sl-7.9.txt](requirements-sl-7.9.txt))

## Setup environment variables

To create the Python virtual environment, you will use the Python binaries and libraries provided by Catapult. Thus, you need to export Cataput environment variables and tools. It greatly depends on your local configuration, and you may need to check with your system administrator.

In particular, you need the `MGC_HOME` environment variable defined in your Linux shell. You can check it with
```
echo $MGC_HOME
```
It should point to your local installation of Catapult, for example, `/tools/Siemens/catapult/2024.2/Mgc_home`. 

If empty, you can define it, for example:
```
export MGC_HOME=/tools/Siemens/catapult/2024.2/Mgc_home # make it sure to use your installation path
```

You also need the directory with Catapult binaries to be at the top of your `PATH` variable:
```
export PATH=${MGC_HOME}/bin:${PATH}
```

Finally, check if the Python executable comes from the Catapult installation directory:
```
which python3
```
That should be something like `/tools/Siemens/catapult/2024.2/Mgc_home/bin/python3`; if instead, it is `/usr/bin/python`, then either `PATH` or `MGC_HOME` are not properly set.

## Create the Python virtual environment

Finally, run the following script:
```
./create_env.sh python3 $HOME/ccs_venv
```
