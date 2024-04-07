# Installing Python 3.12 using Pyenv on RedHat Enterprise Linux Server 7.9

I recently tried to install Python 3.12 on Red Hat Enterprise Linux server edition 7.9. The system already had an older version of Python installed. Because the system is shared with others, I didn’t want to overwrite the default Python at the system level. My intention was to install the latest Python specifically for my projects. To complete this task, I started by installing pyenv, a tool for managing Python versions, and then used it to install the latest Python version on the system. 

During the installation of Python 3.12, I encountered an error stating that OpenSSL was missing from the system. Next, I installed OpenSSL with no errors. Next, I returned to the python 3.12 installation step, only to encounter the following error. 

Traceback (most recent call last): File "", line 1, in File "/home/myvm/.pyenv/versions/3.12.2/lib/python3.12/ssl.py", line 100, in import _ssl # if we can't import it, let the error propagate ^^^^^^^^^^^ ModuleNotFoundError: No module named '_ssl' ERROR: The Python ssl extension was not compiled. Missing the OpenSSL lib?

It was confusing because I knew the system had OpenSSL. What was going on? After conducting some research, I thought it would be a good idea to check the minimum OpenSSL version needed for Python 3.12 and compare it to the version I have installed. I found that the default OpenSSL version chosen by RedHat, 1.01, was not compatible with Python 3.12 which required at least 1.1.1. Subsequently, I installed the correct OpenSSL version and successfully completed the installation of Python 3.12.


```shell
sudo yum install openssl-devel
```

I ran the following command to list the available openssl versions that I can choose from to install:
```shell
yum list available | grep openssl
```

From that list, I choose openssl11.x86_64 1:1.1.1k-7.el7 and installed it as follows:


Install openssl11:
``` shell
sudo yum install openssl11-devel
```

3. Confirm that openssl11 was successfully installed:
``` shell
openssl11 version
```

4. Find the openssl header file and library locations:
``` shell
whereis openssl11
```

Alternatively, try:
``` shell
sudo find / -name openssl11
```

openssl11: /usr/bin/openssl11 /usr/lib64/openssl11 /usr/include/openssl11

5. Add openssl11 to the PATH variables:
``` shell
export LDFLAGS="-L/usr/lib64/openssl11"
export CPPFLAGS="-I/usr/include/openssl11"
```

6. Install Python 3.12.2 using pyenv:
``` shell
pyenv install 3.12.2
```
