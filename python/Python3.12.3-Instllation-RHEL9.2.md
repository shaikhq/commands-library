# Building and Installing Python 3.12.3 on Red Hat Enterprise Linux 9.2

In this document, I will show you the steps of building and installing Python 3.12.3 on a Red Hat Enterprise Linux 9.2. These steps worked for me. Completing these steps took me about 30 minutes. 

If you want to install a different python release, the steps will probably work, but you will have to download your target Python release from python.org and change references in the following steps to your target Python release number. 

1. Download Python 3.12.3 source code into your Linux system:
```shell
curl -O https://www.python.org/ftp/python/3.12.3/Python-3.12.3.tgz
```
Note: `-O` is letter O, not digit 0. 

Next you'll build this python from the download source code. Here's the build process:
2. Install the dependencies for building Python:
sudo yum install gcc openssl-devel bzip2-devel libffi-devel

3. Uncompress the Python source code from the download `.tgz` file:
```shell
tar xzf Python-3.12.3.tgz
```

4. Go to the uncompressed folder:
```shell
cd Python-3.12.3
```

5. Configure build:
```shell
./configure --enable-optimizations
```

6. Now build the Python and install it using the following command:
```shell
sudo make altinstall
```

7. Verify the installed Python version:
```shell
python3.12 --version
```