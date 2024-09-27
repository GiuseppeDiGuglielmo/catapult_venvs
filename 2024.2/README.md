# HOWTO

Export Cataput environment variables and tools. 

In particular you need `MGC_HOME` and 
```
export PATH=${MGC_HOME}/bin:${PATH}
```

Check if the Python executable in from Catapult installation directory:
```
which python3
```
That should be `${MGC_HOME}/bin/python3`.

Finally run the following script:
```
./create_env.sh python3 $HOME/ccs_venv
```
