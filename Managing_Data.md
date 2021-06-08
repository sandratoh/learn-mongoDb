# MongoDB - Managing Data

## Inserting New Documents

Insertion error occcurs when `_id` field is not unique.

By default, `db.<collection-name>.insert()` is ordered and will halt insertion as soon as it detects an error.

Add ordered options to bypass insertion error halt and insert everything that doesn't have error: `{"ordered": false}` after the end of insertion array

```bash
db.inspections.insert([
                       { "_id": 1, "test": 1 },
                       { "_id": 1, "test": 2 },
                       { "_id": 3, "test": 3 }
                      ],
                       { "ordered": false })
```

Implicit creation of collecction in a database - if MongoDB can't find a collection, it will create one and insert document into it

## Updating Documents

Use `updateMany()` and `updateOne()` in mongo shell

Implicit creation of fields if you try to update a field value that is not found - basically, MongoDB will create a new field if it can't find it

### Update Operators

- `$inc` - increment field value by a specified amount

  ```bash
  # Update all documents in the zips collection where the city field is equal to "HUDSON" by adding 10 to the current value of the "pop" field.
  db.zips.updateMany({ "city": "HUDSON" }, { "$inc": { "pop": 10 } })
  ```

- `$set` - sets field value to a new specified value (implicit field creation)

  ```bash
  # Update a single document in the zips collection where the zip field is equal to "12534" by setting the value of the "popupation" field to 17630.
  db.zips.updateOne({ "zip": "12534" }, { "$set": { "population": 17630 } })

  # Creates a new pop field implicitly
  db.zips.updateOne({ "zip": "12534" }, { "$set": { "pop": 17630 } })
  ```

- `$push` - adds an element to an array field
  ```bash
  # Update one document in the grades collection where the student_id is ``250`` *, and the class_id field is 339 , by adding a document element to the "scores" array.
  db.grades.updateOne({ "student_id": 250, "class_id": 339 },
                      { "$push": { "scores": { "type": "extra credit",
                                               "score": 100 }
                                 }
                     })
  ```

## Deleting Documents and Collection

Can use `deleteOne()` and `deleteMany()` to remove data from documents

```bash
# Delete all documents that have test field equal to 1
db.inspections.deleteMany({ "test": 1 })

# Delete one document that has test field equal to 3
db.inspections.deleteOne({ "test": 3 })
```

Only use `deleteOne()` if you are querying by `_id` value - cannot guarantee that we aren't deleting other documents that fit our search query

Use `drop()` when deleting collection:

```bash
db.<collection-name>.drop()
```

When all collections from a database are dropped, the database will also be removed - database will no longer appear in the list of databases when you run `show dbs`
