# How to add a python installation to the global path so that all users can use them?
I have a RHEL system where I installed Python 3.12.3. I wanted to make this python available to all users of the system without them typing the full 
path to the python executable. Here are the steps I took for achieving this:

1. created a new script under `/etc/profile.d/` as the root user. 
```shell
sudo vi /etc/profile.d/python.sh
```

2. in the above file, `python.sh`, added the python executable path to the global `$PATH` variable:
```
export PATH=/usr/local/bin/python3.12:$PATH
```

If you're python executable is installed in a differet location, or you have a different python version, update the above executable path accordingly.

Saved and closed `python.sh`.

3. made the `python.sh` script executable:
```shell
chmod +x /etc/profile.d/python.sh
```

4. made the above change to the PATH effective immediately:
```shell
source /etc/profile
```

Next, I could invoke this Python from the command line as a non-root user:
```shell
python3.12 --version
```
Python 3.12.3

