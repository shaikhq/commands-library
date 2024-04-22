__create explain tables__
```sql
CALL SYSPROC.SYSINSTALLOBJECTS('EXPLAIN', 'C', '', CURRENT USER)
```
__drop explain tables__
```sql
CALL SYSPROC.SYSINSTALLOBJECTS('EXPLAIN', 'D', '', CURRENT USER)
```
