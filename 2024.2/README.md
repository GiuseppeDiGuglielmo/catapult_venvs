# Catapult 2024.2

## Linux distros

These scripts were tested with the following Linux distributions:
- Fedora 8.10 ([requirements.txt](requirements.txt))
- AlmaLinux 9.4 ([requirements.txt](requirements.txt))
- Ubuntu 22.04 ([requirements.txt](requirements.txt))
- ScientificLinux 7.9 ([requirements-sl-7.9.txt](requirements-sl-7.9.txt))

## How to
Export Cataput environment variables and tools. 

In particular, you need `MGC_HOME` and 
```
export PATH=${MGC_HOME}/bin:${PATH}
```

Check if the Python executable comes from the Catapult installation directory:
```
which python3
```
That should be `${MGC_HOME}/bin/python3`.

Finally, run the following script:
```
./create_env.sh python3 $HOME/ccs_venv
```
