# notes
Miscellaneous Notes

* One-liner for running queries against CSV files with SQLite: https://til.simonwillison.net/sqlite/one-line-csv-operations

```
sqlite3 :memory: -cmd '.mode csv' -cmd '.import taxi.csv taxi' \
  'SELECT passenger_count, COUNT(*), AVG(total_amount) FROM taxi GROUP BY passenger_count'
```

This uses the special `:memory:` filename to open an in-memory database. Then it uses two `-cmd` options to turn on CSV mode and import the `taxi.csv` file into a table called `taxi`. Then it runs the SQL query.
