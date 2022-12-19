# Welcome to mongodb world
### Insert a Single Document

Use insertOne() to insert a document into a collection. Within the parentheses of insertOne(), include an object that contains the document data. Here's an example:

```javascript
db.grades.insertOne({
  student_id: 654321,
  products: [
    {
      type: "exam",
      score: 90,
    },
    {
      type: "homework",
      score: 59,
    },
    {
      type: "quiz",
      score: 75,
    },
    {
      type: "homework",
      score: 88,
    },
  ],
  class_id: 550,
})
```

### Insert Multiple Documents

Use insertMany() to insert multiple documents at once. Within insertMany(), include the documents within an array. Each document should be separated by a comma. Here's an example:

```javascript
db.grades.insertMany([
  {
    student_id: 546789,
    products: [
      {
        type: "quiz",
        score: 50,
      },
      {
        type: "homework",
        score: 70,
      },
      {
        type: "quiz",
        score: 66,
      },
      {
        type: "exam",
        score: 70,
      },
    ],
    class_id: 551,
  },
  {
    student_id: 777777,
    products: [
      {
        type: "exam",
        score: 83,
      },
      {
        type: "quiz",
        score: 59,
      },
      {
        type: "quiz",
        score: 72,
      },
      {
        type: "quiz",
        score: 67,
      },
    ],
    class_id: 550,
  },
  {
    student_id: 223344,
    products: [
      {
        type: "exam",
        score: 45,
      },
      {
        type: "homework",
        score: 39,
      },
      {
        type: "quiz",
        score: 40,
      },
      {
        type: "homework",
        score: 88,
      },
    ],
    class_id: 551,
  },
])
```

### Find a Document with Equality

When given equality with an _id field, the find() command will return the specified document that matches the _id. Here's an example:

```javascript 
db.zips.find({ _id: ObjectId("5c8eccc1caa187d17ca6ed16") })
```

### Find a Document by Using the $in Operator

Use the $in operator to select documents where the value of a field equals any value in the specified array. Here's an example:

```javascript
db.zips.find({ city: { $in: ["PHOENIX", "CHICAGO"] } })
```

###Finding Documents by Using Comparison Operators

- Review the following comparison operators: $gt, $lt, $lte, and $gte.
$gt

- Use the $gt operator to match documents with a field greater than the given value. For example:
```javascript
db.sales.find({ "items.price": { $gt: 50}})
```
$lt

- Use the $lt operator to match documents with a field less than the given value. For example:
```javascript
db.sales.find({ "items.price": { $lt: 50}})
```
$lte

- Use the $lte operator to match documents with a field less than or equal to the given value. For example:
```javascript
db.sales.find({ "customer.age": { $lte: 65}})
```
$gte

- Use the $gte operator to match documents with a field greater than or equal to the given value. For example:

```javascript
db.sales.find({ "customer.age": { $gte: 65}})
```


### Find Documents with an Array That Contains a Specified Value

In the following example, "InvestmentFund" is not enclosed in square brackets, so MongoDB returns all documents within the products array that contain the specified value.

```javascript
db.accounts.find({ products: "InvestmentFund"})
```

- Find a Document by Using the $elemMatch Operator

- Use the $elemMatch operator to find all documents that contain the specified subdocument. For example:

```javascript
db.sales.find({
  items: {
    $elemMatch: { name: "laptop", price: { $gt: 800 }, quantity: { $gte: 1 } },
  },
})
```

### Finding Documents by Using Logical Operators

Review the following logical operators: implicit $and, $or, and $and.
Find a Document by Using Implicit $and

Use implicit $and to select documents that match multiple expressions. For example:


```javascript
db.routes.find({ "airline.name": "Southwest Airlines", stops: { $gte: 1 } })
```

#### Find a Document by Using the $or Operator

Use the $or operator to select documents that match at least one of the included expressions. For example:


```javascript
db.routes.find({
  $or: [{ dst_airport: "SEA" }, { src_airport: "SEA" }],
})
```

#### Find a Document by Using the $and Operator

Use the $and operator to use multiple $or expressions in your query.


```javascript
db.routes.find({
  $and: [
    { $or: [{ dst_airport: "SEA" }, { src_airport: "SEA" }] },
    { $or: [{ "airline.name": "American Airlines" }, { airplane: 320 }] },
  ]
})
```






