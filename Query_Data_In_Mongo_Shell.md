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

Use `findOne()` to find **one** result, use `find()` to find **all** matching results

Use `$exists` operator to find all documents that contain / not contain a field

- Syntax: `{ field: { $exists: <boolean> }}`

- When `<boolean>` is `true`, query returns all document that has the field including if the value is `null`

- When `<boolean>` is `false`, query returns only the doccuments that do not contain the field

```bash
# Find all documents in the `inspections` collection that has a `test` field
db.inspections.find({"test": {"exists": true}})
```
