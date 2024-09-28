# Catapult 2024.2

## Linux distros

These scripts have been tested with the following Linux distributions:
- Fedora 8.10 ([requirements.txt](requirements.txt))
- AlmaLinux 9.4 ([requirements.txt](requirements.txt))
- Ubuntu 22.04 ([requirements.txt](requirements.txt))
- ScientificLinux 7.9 ([requirements-sl-7.9.txt](requirements-sl-7.9.txt))

## Setup of the environment variables (to create a Python virtual env)

To create the Python virtual environment, you **have to** use the Python binaries and libraries provided by Catapult. Thus, you need to export Cataput environment variables and tools. It greatly depends on your local configuration, and you may need to check with your system administrator.

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
That should return something like `/tools/Siemens/catapult/2024.2/Mgc_home/bin/python3`; if instead, it is `/usr/bin/python3`, then either `PATH` or `MGC_HOME` are not properly set.

## Create the Python virtual environment

Finally, run the following script:
```
./create_env.sh python3 $HOME/ccs_venv
```

Creating the Python virtual environment should take several minutes. On success:
```
=========================
HLS4ML installed properly
=========================

Done.
Execute: 'source $VENV/bin/activate' in a new shell to get environment configured
```

If the process fails, you will get:
```
HLS4ML install failed
```

## Other issues

If you get the following error when running an `hls4ml` design in Catapult AI NN
```
/usr/bin/ld: cannot find crt1.o: No such file or directory
```

Add the variable `LIBRARY_PATH` to the file `$MGC_HOME/shared/pkgs/ccs_hls4ml/hls4ml/hls4ml/templates/catapult/build_lib.sh`:
```
LIBRARY_PATH=/usr/lib/x86_64-linux-gnu \
    ${CC} ${CFLAGS} ${INCFLAGS} -shared ${PROJECT}.o ${PROJECT}_bridge.o -o firmware/${PROJECT}-${LIB_STAMP}.so
```
