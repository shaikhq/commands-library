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
