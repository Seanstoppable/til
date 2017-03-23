Copy Command
====

Copying multiline queries does not actually work.

To get around this, easiest thing to do is to create a view (materialized or
otherwise) and then run the command.

```
create temporary view foo as select *
from large query;

\copy (select * from foo) to 'foo.csv' WITH CSV DELIMITER ',';
