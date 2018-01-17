List Vacuum Status
====

Want to know when a table was last vacuumed and/or what dead rows it contains?

```
SELECT relname, last_autoanalyze, last_autovacuum, last_vacuum, n_dead_tup
FROM pg_stat_all_tables 
WHERE n_dead_tup > 0;
```
