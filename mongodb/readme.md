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
});
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
]);
```

### Find a Document with Equality

When given equality with an _id field, the find() command will return the specified document that matches the _id. Here's an example:

```javascript
db.zips.find({ _id: ObjectId("5c8eccc1caa187d17ca6ed16") });
```

### Find a Document by Using the $in Operator

Use the $in operator to select documents where the value of a field equals any value in the specified array. Here's an example:

```javascript
db.zips.find({ city: { $in: ["PHOENIX", "CHICAGO"] } });
```

###Finding Documents by Using Comparison Operators

- Review the following comparison operators: $gt, $lt, $lte, and $gte.
  $gt

- Use the $gt operator to match documents with a field greater than the given value. For example:

```javascript
db.sales.find({ "items.price": { $gt: 50 } });
```

$lt

- Use the $lt operator to match documents with a field less than the given value. For example:

```javascript
db.sales.find({ "items.price": { $lt: 50 } });
```

$lte

- Use the $lte operator to match documents with a field less than or equal to the given value. For example:

```javascript
db.sales.find({ "customer.age": { $lte: 65 } });
```

$gte

- Use the $gte operator to match documents with a field greater than or equal to the given value. For example:

```javascript
db.sales.find({ "customer.age": { $gte: 65 } });
```

### Find Documents with an Array That Contains a Specified Value

In the following example, "InvestmentFund" is not enclosed in square brackets, so MongoDB returns all documents within the products array that contain the specified value.

```javascript
db.accounts.find({ products: "InvestmentFund" });
```

- Find a Document by Using the $elemMatch Operator

- Use the $elemMatch operator to find all documents that contain the specified subdocument. For example:

```javascript
db.sales.find({
  items: {
    $elemMatch: { name: "laptop", price: { $gt: 800 }, quantity: { $gte: 1 } },
  },
});
```

### Finding Documents by Using Logical Operators

Review the following logical operators: implicit $and, $or, and $and.
Find a Document by Using Implicit $and

Use implicit $and to select documents that match multiple expressions. For example:

```javascript
db.routes.find({ "airline.name": "Southwest Airlines", stops: { $gte: 1 } });
```

#### Find a Document by Using the $or Operator

Use the $or operator to select documents that match at least one of the included expressions. For example:

```javascript
db.routes.find({
  $or: [{ dst_airport: "SEA" }, { src_airport: "SEA" }],
});
```

#### Find a Document by Using the $and Operator

Use the $and operator to use multiple $or expressions in your query.

```javascript
db.routes.find({
  $and: [
    { $or: [{ dst_airport: "SEA" }, { src_airport: "SEA" }] },
    { $or: [{ "airline.name": "American Airlines" }, { airplane: 320 }] },
  ],
});
```

### Replacing a Document in MongoDB

To replace documents in MongoDB, we use the replaceOne() method. The replaceOne() method takes the following parameters:

    filter: A query that matches the document to replace.
    replacement: The new document to replace the old one with.
    options: An object that specifies options for the update.

In the previous video, we use the \_id field to filter the document. In our replacement document, we provide the entire document that should be inserted in its place. Here's the example code from the video:

```javascript
db.books.replaceOne(
  {
    _id: ObjectId("6282afeb441a74a98dbbec4e"),
  },
  {
    title: "Data Science Fundamentals for Python and MongoDB",
    isbn: "1484235967",
    publishedDate: new Date("2018-5-10"),
    thumbnailUrl:
      "https://m.media-amazon.com/images/I/71opmUBc2wL._AC_UY218_.jpg",
    authors: ["David Paper"],
    categories: ["Data Science"],
  }
);
```

### Updating MongoDB Documents by Using updateOne()

The updateOne() method accepts a filter document, an update document, and an optional options object. MongoDB provides update operators and options to help you update documents. In this section, we'll cover three of them: $set, upsert, and $push.

$set

The $set operator replaces the value of a field with the specified value, as shown in the following code:

```javascript
db.podcasts.updateOne(
  {
    _id: ObjectId("5e8f8f8f8f8f8f8f8f8f8f8"),
  },

  {
    $set: {
      subscribers: 98562,
    },
  }
);
```

upsert

The upsert option creates a new document if no documents match the filtered criteria. Here's an example:

```javascript
db.podcasts.updateOne(
  { title: "The Developer Hub" },
  { $set: { topics: ["databases", "MongoDB"] } },
  { upsert: true }
);
```

$push

The $push operator adds a new value to the hosts array field. Here's an example:

```javascript
db.podcasts.updateOne(
  { _id: ObjectId("5e8f8f8f8f8f8f8f8f8f8f8") },
  { $push: { hosts: "Nic Raboy" } }
);
```

#### The $push operator is used to add a new element to an array field.

    Use the updateOne() method on the birds collection.

    Use the _id field of the document to specify the document to update.

    In the update specification, use the $push operator to add the new element to the diet array.

    Use the $each modifier to add multiple elements to the array.

```javascript
db.birds.updateOne(
  { _id: ObjectId("6268471e613e55b82d7065d7") },
  {
    $push: {
      diet: { $each: ["newts", "opossum", "skunks", "squirrels"] },
    },
  }
);
```

### Updating MongoDB Documents by Using findAndModify()

The findAndModify() method is used to find and replace a single document in MongoDB. It accepts a filter document, a replacement document, and an optional options object. The following code shows an example:

```javascript
db.podcasts.findAndModify({
  query: { _id: ObjectId("6261a92dfee1ff300dc80bf1") },
  update: { $inc: { subscribers: 1 } },
  new: true,
});
```

#### Updating MongoDB Documents by Using updateMany()



To update multiple documents, use the updateMany() method. This method accepts a filter document, an update document, and an optional options object. The following code shows an example:

   - Use the updateMany() method on the birds collection to update multiple documents.

   - The updateMany() method accepts a filter, an update, and an optional options object.

```javascript
db.collection.updateMany(filter, update, [options]);
```

   - In this example, our filter will look for the common_name values of Blue Jay and Grackle.

   - The $in operator is used to match documents that have a common_name field that is equal to one of the bird names provided in the filter.

   - In the update, we set the last_seen field to ISODate("2022-01-01").

   - The ISODate() function is used to convert the date string into a Date object that MongoDB can store.

```javascript
db.books.updateMany(
  { publishedDate: { $lt: new Date("2019-01-01") } },
  { $set: { status: "LEGACY" } }
);

db.birds.updateMany(
  {
    common_name: {
      $in: ["Blue Jay", "Grackle"],
    },
  },
  {
    $set: {
      last_seen: ISODate("2022-01-01"),
    },
  }
);
```

### Deleting Documents in MongoDB

To delete documents, use the deleteOne() or deleteMany() methods. Both methods accept a filter document and an options object.
#### Delete One Document

The following code shows an example of the deleteOne() method:

```javascript
db.podcasts.deleteOne({ _id: Objectid("6282c9862acb966e76bbf20a") })
```

### Delete Many Documents

The following code shows an example of the deleteMany() method:

```javascript
db.podcasts.deleteMany({category: “crime”})
```


### Sorting and Limiting Query Results in MongoDB

##### Review the following code, which demonstrates how to sort and limit query results.
Sorting Results

Use cursor.sort() to return query results in a specified order. Within the parentheses of sort(), include an object that specifies the field(s) to sort by and the order of the sort. Use 1 for ascending order, and -1 for descending order.

Syntax:

```javascript
db.collection.find(<query>).sort(<sort>)
```

Example:

// Return data on all music companies, sorted alphabetically from A to Z.

```javascript
db.companies.find({ category_code: "music" }).sort({ name: 1 });
```
To ensure documents are returned in a consistent order, include a field that contains unique values in the sort. An easy way to do this is to include the _id field in the sort. Here's an example:

// Return data on all music companies, sorted alphabetically from A to Z. Ensure consistent sort order

```javascript
db.companies.find({ category_code: "music" }).sort({ name: 1, _id: 1 });
```
### Limiting Results

Use cursor.limit() to return query results in a specified order. Within the parentheses of limit(), specify the maximum number of documents to return.

Syntax:

```javascript
db.companies.find(<query>).limit(<number>)
```
Example:

// Return the three music companies with the highest number of employees. Ensure consistent sort order.

```javascript
db.companies
  .find({ category_code: "music" })
  .sort({ number_of_employees: -1, _id: 1 })
  .limit(3);
```


### Returning Specific Data from a Query in MongoDB

Review the following code, which demonstrates how to return selected fields from a query.
Add a Projection Document

To specify fields to include or exclude in the result set, add a projection document as the second parameter in the call to db.collection.find().

Syntax:

```javascript
db.collection.find( <query>, <projection> )
```
Include a Field

To include a field, set its value to 1 in the projection document.

Syntax:
```javascript
db.collection.find( <query>, { <field> : 1 })
```
Example:

// Return all restaurant inspections - business name, result, and _id fields only
```javascript
db.inspections.find(
  { sector: "Restaurant - 818" },
  { business_name: 1, result: 1 }
)
```

Exclude a Field

To exclude a field, set its value to 0 in the projection document.

Syntax:
```javascript
db.collection.find(query, { <field> : 0, <field>: 0 })
```
Example:

// Return all inspections with result of "Pass" or "Warning" - exclude date and zip code
```javascript
db.inspections.find(
  { result: { $in: ["Pass", "Warning"] } },
  { date: 0, "address.zip": 0 }
)
```

While the _id field is included by default, it can be suppressed by setting its value to 0 in any projection.

// Return all restaurant inspections - business name and result fields only

```javascript
db.inspections.find(
  { sector: "Restaurant - 818" },
  { business_name: 1, result: 1, _id: 0 }
)
```

