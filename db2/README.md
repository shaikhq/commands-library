__creating a database__
```shell
db2 create database tpcds
```
__adding db2 to shell__
```shell
. /home/db2inst1/sqllib/db2profile
```
__finding db2 fence id__
```shell
ls -l ~/sqllib/adm/.fenced
```

__export__
```shell
db2 "export to db2ml_blogs_data.csv of del modified by coldel, select * from shaikhq.DB2ML_BLOGS"
```

__db2look__
```shell
db2look -d sample -z shaikhq -t DB2ML_BLOGS -e -o db2ml_blogs_ddl.sql
```

__create a new db2 instace__
1. log in as root
2. cd to the following dir:
```shell
cd /opt/ibm/db2/V11.5/instance
```

using the same id for instance owner and fence id:
```shell
./db2icrt -u db2inst2 db2inst2
```

__drop an existing db2 instance__
```shell
/opt/ibm/db2/V11.5/instance/db2idrop db2inst1
```
