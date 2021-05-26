# MongoDB - Basics

## What is MongoDB?

MongoDB is a **NoSQL** database that uses documents to store data in an organized way.

It does not use related tables of data to store information (no rows or columns), instead, it uses _documents_.

## Database Structure

**Document** - a way to organize and store data as a set of _field-value pairs_

**Field** - a unique identifier for a datapoint

**Value** - data related to a given identifier

**Collection** - an organized store of documents in MongoDB, usually with common fields between documents

> Database > Collections > Documents > Fields && Values

## What is MongoDB Atlas?

The Atlas cloud database is a fully managed database built with MongoDB as its core for data storage and retrieval

Atlas can deploy _clusters_ which get configured in a _replicate set_.

**Cluster** - group of servers that store your data

**Replica Set** - a few connected machines that store the same data to ensure that if something happens to one of the machines, the data will remain intact

**Instance** - a single machine locally or in the cloud, running a certain software (eg: the MongoDB database in our case)
