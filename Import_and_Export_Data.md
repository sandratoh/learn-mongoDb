# MongoDB - Importing and Exporting Data

There are four ways to import and export data depending on if you're working with JSON or BSON

| JSON          | BSON           |
| ------------- | -------------- |
| `mongoimport` | `mongorestore` |
| `mongoexport` | `mongodump`    |

## Export

Export data in BSON:

```bash
mongodump --uri "<Atlas Cluster URI>"
```

Export data in JSON:

```bash
mongoexport --uri "<Atlas Cluster URI>"
            --collection=<collection name>
            --out=<filename>.json
```

### URI string

- URI string = **Uniform Resource Identifier**

- Using `srv` to establish a `secure` connection between application and MongoDB instance

```bash
# Connection string
mongodb+srv://user:password@clusterURI.mongodb.net/database

# 1. Username and password
# 2. Use @ to access unique Atlas cluster
# 3. Target database name
```
