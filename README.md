Db Migration tool - Flyway
--------------------------

[Flyway config file Parameters](https://documentation.red-gate.com/fd/parameters-224919673.html)

[Flyway for Postgres url config](https://documentation.red-gate.com/fd/postgresql-database-235241807.html)

[Flyway callbacks](https://documentation.red-gate.com/fd/callback-concept-184127466.html)

----
## Create Baseline

- Dump 現在資料庫的狀態 
```
pg_dump -U postgres -h db -p 5432 -d postgres -F p -f V1__Baseline.sql
```

- Reset flyway baseline
```
flyway baseline -baselineVersion=1 -baselineDescription="Baseline"

flyway clean
flyway migrate
```

[Flyway baseline](https://documentation.red-gate.com/fd/command-line-baseline-184127411.html)