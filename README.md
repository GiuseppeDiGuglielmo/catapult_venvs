# Workstation Setup for Catapult AI NN

This repository provides help for setting up Catapult AI NN, including scripts for creating Python virtual environments and applying hotfixes.

A Python virtual environment is typically created once, the first time you run a Catapult AI NN project. By default, Catapult AI NN places the environment in your home directory under the `ccs_venv` subdirectory (`$HOME/ccs_venv`). On some Linux distributions, the default scripts may fail, and this repository provides fixes for those cases.

The scripts here create a distro-specific Python virtual environment for Catapult AI NN (`$HOME/ccs_venv`). Each directory corresponds to a specific Catapult release, such as `2024.2_1`, and some directories include configuration files for different Linux distributions. Refer to the README file in each directory for details.

You can use `diff` to compare the contents of these directories to monitor changes between releases. Additionally, you can reference the original scripts provided by Siemens in your Catapult installation directory at `$MGC_HOME/shared/pkgs/ccs_hls4ml/create_env.sh`.

In addition solutions are provided for the most common issues you may notice.
