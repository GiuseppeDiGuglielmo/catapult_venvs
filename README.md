# Create Python Virtual Env for Catapult AI NN

A Python virtual environment is usually created only once, the first time you run a Catapult AI NN project. Catapult AI NN places the environment in your home directory in the `ccs_venv` subdirectory (`$HOME/ccs_venv`). On some Linux distributions, Catapult's scripts may fail. This repo tries to address those issues.

The scripts in this repository create a distro-customized Python virtual environment for Catapult AI NN (`$HOME/ccs_venv`). Each directory in this repo provides scripts for the associated release of Catapult, e.g. `2024.2_1`. Some directories come with multiple configuration files to support different Linux distros. For more details, see the README in each directory.

You can `diff` the content between directories here provided to monitor changes among releases; you can also check the scripts from Siemens at your Catapult installation path `$MGC_HOME/shared/pkgs/ccs_hls4ml/create_env.sh`.
