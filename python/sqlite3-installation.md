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
