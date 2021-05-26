# MongoDB - JSON vs. BSON

MongoDB data is:

- **stored in BSON** (Binary JSON) format internally and over the network, and

- **viewed in JSON** format.

## What is JSON?

- JavaScript Object Notation

- Text-based format (UTF-8 String encoding)

- Stored in key-value pair

  - String key

  - Value can be a string, number, boolean, array, function, or another object

- Used in APIs, configuration files, log messages, and database storage

- Human and machine readable

### Why JSON is not ideal for a database:

- JSON is text-based, and text parsing is very slow
- Human-readable format is not space-efficient
- Only supports a limited number of basic data types

## What is BSON?

- Binary JSON

- Binary structure and encoding allows data to be parsed much more quickly

- Able to store non-JSON-native data types such as dates and binary data

- Machine only readability

### Advantages of BSON over JSON:

- Optimized for speed, space, and flexibility

- High performance

- General purpose focused
