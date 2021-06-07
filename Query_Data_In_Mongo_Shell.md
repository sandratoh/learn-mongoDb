# MongoDB - Query Data in Mongo Shell

Connect MongoDB CLI with Atlas cluster

```bash
$ mongo "mongodb+srv://<username>:<password>@<cluster>.mongodb.net/admin"
```

Show list of databases in cluster

```bash
$ show dbs
```

Use a specific database from a cluster

```bash
$ use sample_training
```

View collections in database

```bash
$ show collections
```

Query database with field-value pair

```bash
$ db.<collection name>.find({"field": "value"})

# don't need to specify database name since we already navigated inside
```

Querying with `find()` will display the first 20 queries results. To view more, use `it` command

- `it` - iterates through a `cursor`
- `cursor` - a `pointer` to a result set of a query
- `pointer` - a direct address of the memory location

Use `count()` to return the number of results matching the query

```bash
$ db.zips.find({"state": "NY"}).count()
```

Use `pretty()` to view data in more readable way

```bash
db.zips.find({"state": "NY", "city": "ALBANY"}).pretty()
```
