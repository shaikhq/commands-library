check the version of the currently installed sqllite3 on your OS:

```shell
sqllite3 --version
```

If it's below, which should be the case since you're getting the above error, uninstall it:
```shell
sudo dnf remove sqlite
```

Also, search for sqlite3 installed via alternate methods:
```shell
sudo find /usr/local -name '*sqlite3*'
```

For me, it came back as follows:
```
sudo find /usr/local -name '*sqlite3*'
/usr/local/bin/sqlite3
/usr/local/include/sqlite3.h
/usr/local/include/sqlite3ext.h
/usr/local/lib/pkgconfig/sqlite3.pc
/usr/local/lib/libsqlite3.so.3.49.1
/usr/local/lib/libsqlite3.so
/usr/local/lib/libsqlite3.so.0
/usr/local/lib/libsqlite3.a
/usr/local/share/man/man1/sqlite3.1
```

I removed them as follows:
```shell
sudo rm /usr/local/bin/sqlite3
sudo rm /usr/local/include/sqlite3.h
sudo rm /usr/local/include/sqlite3ext.h
sudo rm /usr/local/lib/pkgconfig/sqlite3.pc
sudo rm /usr/local/lib/libsqlite3.so.3.49.1
sudo rm /usr/local/lib/libsqlite3.so
sudo rm /usr/local/lib/libsqlite3.so.0
sudo rm /usr/local/lib/libsqlite3.a
sudo rm /usr/local/share/man/man1/sqlite3.1
```

Then I checked the paths for any refences to sqlite3:
```
echo $PATH
echo $LD_LIBRARY_PATH
echo $PKG_CONFIG_PATH
```

Nothing was there. Then I cleared the cache:
```shell
sudo ldconfig

```

At this point, my system doesn't have any sqlite3. 

Now ensure, your python interpreter isn't linked to a previous installation of sqlite3:

```shell
python3.12 -c "import sqlite3; print('SQLite version:', sqlite3.sqlite_version)"
```

I still see this:
```
 python3.12 -c "import sqlite3; print('SQLite version:', sqlite3.sqlite_version)"
SQLite version: 3.34.1
```

The Python sqlite3 module is a wrapper around the SQLite library that was present on your system when Python was compiled. Therefore, the version of SQLite that sqlite3 uses is determined at the time Python is built and isn't dynamically linked to the system's SQLite library. This means that even if you've updated the SQLite version on your system, the sqlite3 module will continue to use the older version it was originally compiled with.

1. Uninstalling Python 3.12:

To remove Python 3.12, execute:

bash
Copy
Edit
sudo dnf remove python3.12
Caution: Removing Python can affect system utilities that depend on it. Ensure that removing this specific version won't disrupt your system.

Download the install the latest sqlite3 as follows:

2. Download the Latest SQLite Source Code:

Download the source code for SQLite version 3.49.1:

bash
Copy
Edit
wget https://www.sqlite.org/2025/sqlite-autoconf-3490100.tar.gz
3. Extract the Downloaded Archive:

Extract the contents of the tarball:

bash
Copy
Edit
tar xvfz sqlite-autoconf-3490100.tar.gz
4. Compile and Install SQLite:

Navigate to the extracted directory and compile the source:

bash
Copy
Edit
cd sqlite-autoconf-3490100
./configure
make
sudo make install
5. Verify the Installation:

Confirm that the latest version of SQLite is installed:

bash
Copy
Edit
sqlite3 --version
This should display 3.49.1, indicating a successful installation.

2. Reinstalling Python 3.12:

After uninstallation, you can reinstall Python 3.12:

bash
Copy
Edit
sudo dnf install python3.12
This command installs the python3.12 package, providing the Python 3.12 interpreter. Note that the unversioned python3 command typically points to the system's default Python version (e.g., Python 3.9). To use Python 3.12, you'll need to invoke it explicitly with python3.12.


