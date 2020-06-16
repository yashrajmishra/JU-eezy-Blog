---
title: "Get to know 🔥Firebase"
path: "/get-to-know-firebase"
date: "2020-06-16"
author: "Yashraj Mishra"
excerpt: '"Have you ever wanted to make a simple web app? Well, if you have..."'
tags: ["firebase", "database", "web development"]
---

Have you ever wanted to make a simple web app? Well, if you have, you will probably be aware of the fact that an app has normally a back-end which includes the logic and integration with a database, and a front-end which helps the user interact with our application.

So, returning to the previous question, If you want a simple app in which requires a small database and some users, Is there a need for a full back-end system? Well no, actually there is a really cool service from Google called Firebase which gives you a pretty good database and

**_I am going to teach you the following basics of 🔥 Firebase Cloud Firestore :-_**

1. Add/Create A Document To Cloud Firestore
1. Update A Document Data to Cloud Firestore
1. Delete Document from Cloud Firestore
1. Get Documents Data from Firestore Database
1. Get A Single Document Data
1. Get Data from Sub-collection in Firestore
1. Firestore Single/Multiple Where Query Filter
1. OrderBy and Limit Filters
1. Collection Group Queries
1. Firestore Pagination Queries using Query Cursors
1. Conclusion

## Add/Create A Document To Cloud Firestore

There are two ways to create/add a new document to the Cloud Firestore, which are:

- add()
- set()

Let’s take a look at `add()` method sample code.

```javascript
const db = firebase.firestore();
db.collection("users").add({
  name: "Yashraj Mishra",
  email: "mishra.yashrajs@email.com",
  age: 25,
});
```

> _To run the sample code in your project, you will need to [add Firebase to your project](https://firebase.google.com/docs/web/setup)._

First, get a reference to the Firestore database using `firestore()` method and store it in `db`.

Then, obtain a reference to the users collection by invoking `collection()` method on the `db` object.

Finally, run `add()` method by passing new data as a JavaScript object.

That’s it.

Let’s take a look at `set()` method.

As you can see below, the `set()` method is very similar to `add()`.

```javascript
db.collection("users")
  .doc()
  .set({
    name: "Yashraj Mishra",
    email: "mishra.yashrajs@email.com",
    age: 25,
  });
```

The only difference is that you can add a document to a collection directly using `add()`method, but for the `set()` method you need to explicitly specify the document identifier by invoking `doc().`

If you do not specify a document identifier, it will be created.

> Under the hood, both `set()` and `add()` are working very similar according to the [Firestore Documentation](https://firebase.google.com/docs/firestore/manage-data/add-data).

I prefer to use `set()` over `add()` because I can use a single method to add or update data. 🙂

## Update A Document Data to Cloud Firestore

There are two options to update existing data.

- set()
- update()

**Overwriting A Document using set()**

When you want to overwrite or completely replace an existing document, you can easily do that by using the`set()` method by passing an existing auto-generated document identifier as an argument to the `doc()` method.

```javascript
db.collection("users")
  .doc("3P86VJxcpBK0D0lsAyYx")
  .set({ name: "Kim chuchu" });
```

**Overriding A Document using set() (BETTER)**

There are some cases where you will need to just update (override) one or more fields rather than replacing the whole document.

This can also be done by `set()` method as well.

```javascript
db.collection("users")
  .doc("3P86VJxcpBK0D0lsAyYx")
  .set(
    {
      name: "Yashraj Mishra",
      age: 25,
    },
    { merge: true }
  );
```

The above code is very similar to the previous one, with the only difference being it has a JavaScript object {merge: true} as a second argument to the `set()` method which will prevent overwriting an entire document.

At this stage, the `set()` method will only update with new values to the targetted document if the `name` and `age` fields exist.

Otherwise, the missing fields will be created.

**Overriding A Document using update()**

The `update()` method is very similar to `set()` without the second argument and is pretty straight forward.

```javascript
db.collection("users")
  .doc("3P86VJxcpBK0D0lsAyYx")
  .update({
    name: "Yashraj Mishra",
    email: "mishra.yashrajs@email.com",
  });
```

You must provide an auto-generated ID as an argument to the `doc()` when using `update()` method to have it work.

## Delete Document from Cloud Firestore

**Delete A Field From A Document on the Firestore Database**

You can delete an entire document from Cloud Firestore using `delete()` method by passing its auto-generated ID as an argument to the `doc()` method.

```javascript
db.collection("users")
  .doc("3P86VJxcpBK0D0lsAyYx")
  .delete()
  .then(function() {
    console.log("Document successfully deleted!");
  })
  .catch(function(error) {
    console.error("Error removing document: ", error);
  });
```

> _One more thing I want to point out here is that sub-collections won’t be deleted when you delete the parent document._

**Delete A Field From A Document on the Firestore Database**

To delete a specific field from a document, use `update()` method and inside it add the field that you want to delete as a javascript object and set **firebase.firestore.FieldValue.delete()** as a value of it.

```javascript
db.collection("users")
.doc("3P86VJxcpBK0D0lsAyYx")
.update({
email.firestore.FieldValue.delete()
})
```

Pretty straight forward.

Before getting into retrieving data from the Firestore Database, let’s add some data to the Firestore Database calling the following function once.

```javascript
addUsersToFirestore() {
  var users = [
    {
      name: "XYZ",
      email: "xyz@email.com",
      createdAt: new Date("2020-06-16 12:08:00"),
    },
    {
      name: "XYZ",
      email: "xyz@email.com",
      createdAt: new Date("2020-06-16 12:08:00"),
    },
    {
      name: "XYZ",
      email: "xyz@email.com",
      createdAt: new Date("2020-06-16 12:08:00"),
    }
  ];
  const db = firebase.firestore();
  users.forEach((user) => {
    db.collection("users").doc().set(user);
  });
}
```

If everything goes well, you should have a collection called `users` with five documents.

## Get Documents Data from Firestore Database

There are a couple of options for how you can get or retrieve data from the Cloud Firestore Database.

- **get():** This method will be invoked and get data only once until it’s called again.
- **onSnapShot():** Unlike `get()` method, this method will be triggered every time data changes in a location that it’s listening for.

In the code below, I use the `get()` method on the `users` collection reference to get all the documents data from it.

It will return a promise, and if the promise is full-filled the `then()` function will be called and the callback function will have a snapshot object `snap`.

```javascript
db.collection("users")
  .get()
  .then((snap) => {
    snap.forEach((doc) => {
      console.log(doc.data());
      console.log(doc.id);
    });
  });
```

The `snap` object contains all the user documents from the `users` collection with some other meta information.

You can get an individual document using `forEach()` by passing a callback function on each iteration.

On each iteration, you will get value named `doc`, which is also a firebase query snapshot, that contains each user document with some additional metadata.

Inside that loop, you can invoke `data()` method on the `doc` object to get an actual user document.

Also, you can get the auto-id of a user using `id` property on the `doc` object.

At this stage, if you make any changes on the users collection, you will have to refresh the page in order to see the change as the `get()` method will be called once.

To see a real-time change on the view, you will need to use **onSnapShot()** listener**.**

```javascript
db.collection("users")
  .onSnapshot()
  .then((snap) => {
    snap.forEach((doc) => {
      console.log(doc.data());
    });
  });
```

As you can see, the above code is almost identical to the previous one. The only change is replacing the `get()` to `onSnapShot()` method.

Using the **onSnapShot()** listener method, it will update the view automatically when data changes on the Firestore Database which is cool! 😎

## Get A Single Document Data

To get a specific document, call `doc()` method by passing the auto-generated document ID to it.

```javascript
db.collection("users")
  .doc("cAwTiq7IYKAbFGnhgKT3")
  .get()
  .then((doc) => {
    console.log(doc.data());
  });
```

> _Make sure that the `get()` method always gets run last._

## Get Data from Sub-collection in Firestore

Sub-collections are a great way to structure your data.

Firestore queries are shallow.

So, when you query to get all the user documents form `users` collection, you won’t get any sub-collections underneath them.

To get all documents from a sub-collection of a specific user, you can query like this:

```javascript
db.collection("users")
  .doc("cAwTiq7IYKAbFGnhgKT3")
  .collection("posts")
  .get()
  .then((snap) => {
    snap.forEach((doc) => {
      console.log(doc.data());
    });
  });
```

If you want to get a specific document from a sub-collection of a specific user, the query should be like this:

```javascript
db.collection("users")
  .doc("cAwTiq7IYKAbFGnhgKT3")
  .collection("posts")
  .doc("BjLZHiuQfVQVOu9nEG7k")
  .get()
  .then((snap) => {
    console.log(snap.data());
  });
```

The one restriction here is that there is no way to retrieve all documents from the users collection as well as orders collection all at once. If you’re trying to make a query like that, you might want to think about changing your data structure.

## Firestore Single/Multiple Where Query Filter

Querying Firestore with the `where` clause is one of the most common ways to filter documents using query operators `== <,`, `<=`, `>`, `>=`, etc.

Let’s see how to make a query with a single where clause.

For example, if I want to get users where their age is equal to or less than 30, my query will look like this:

```javascript
db.collection("users")
  .where("age", "<=", 30)
  .get()
  .then((snap) => {
    snap.forEach((doc) => {
      console.log(doc.data());
    });
  });
```

As you can see, the `where()` method takes three arguments which are a **field name**, relational **operator** and the **value** that you want to compare against to the field name. These arguments look very similar to an if condition block.

Now, let’s make a query with multiple where clauses.

For that, I want documents where the age is less than or equal to 30 but greater than or equal to 20.

```javascript
db.collection("users")
  .where("age", "<=", 30)
  .where("age", ">=", 20)
  .get()
  .then((snap) => {
    snap.forEach((doc) => {
      console.log(doc.data());
    });
  });
```

Sometimes, you will need to create a composite index to get the query working.

Let’s say you want to get the documents from users collection where each user age is greater than or equal to 20 and gender is equal to female.

```javascript
db.collection("users")
  .where("age", ">=", 20)
  .where("gender", "==", "fmale")
  .get()
  .then((snap) => {
    snap.forEach((doc) => {
      console.log(doc.data());
    });
  });
```

When you use **equal** **operator** and **range** **operator** in a single query, you will need to create a composite index.

The quickest way to create an index for this query is to go to the debug area on the browser and click the link that is provided by Firebase.

It will take you to your Firebase Console Dashboard -> Database -> Create A Composite Index.

And click Create Index.

This will take several minutes to complete the enabling process.

Once it’s done ✅, you should be able to see that the composite index is enabled by going to Firebase Console Dashboard -> Database -> Indexes Tab

## OrderBy and Limit Filters 

Let’s take a look at `orderBy()` method which takes two arguments, the first one is a field name, the second one is optional and it defaults to ascending order (asc).

Let’s combine `where` and`orderBy()` by retrieving documents where age is greater than or equal to 20 and organize documents in descending order by `age`.

```javascript
db.collection("users")
  .where("age", ">=", 20)
  .orderBy("age", "desc")
  .get()
  .then((snap) => {
    snap.forEach((doc) => {
      console.log(doc.data());
    });
  });
```

Nice!

Let’s add one more query filter called `limit()`.

By using the `limit()` method, you can restrict the number of documents count by passing an integer value.

```javascript
db.collection("users")
  .where("age", ">=", 20)
  .orderBy("age", "desc")
  .limit(2)
  .get()
  .then((snap) => {
    snap.forEach((doc) => {
      console.log(doc.data());
    });
  });
```

## Collection Group Queries

Collection Group Queries allow you to query data from different sub-collections that share the same name across the Firestore Database. It’s a new feature at the time the post was released at the [Google I/O Conference 2019](https://www.youtube.com/watch?v=lW7DWV2jST0).

As I have shown earlier, I have a collection called `users` which have sub-collections called `posts`.

```javascript
users / { userID } / posts / { postID };
```

Let’s say I want to get all the documents that were published in 2018 from posts sub-collections across the Firestore Database.

```javascript
db.collectionGroup("posts")
  .where("publishedAt", ">=", new Date("2018-01-01 00:00"))
  .where("publishedAt", "<=", new Date("2018-12-31 23:59"))
  .get()
  .then((snap) => {
    snap.forEach((doc) => {
      console.log(doc.data());
    });
  });
```

Sub-collections that share the same name can be targeted using `collectionGroup()` instead of `collection()`.

When you want to compare two dates, you will need to use `new Date()` and pass the `date` that you want to check against the `publishedAt` on the `posts` sub-collection.

If you get a `Missing or Insufficient Permission` error on the browser / app debug console when you run the collection group query, the security rules need to be changed.

To change the Security Rules, Go to **Firebase Console** → **Database→** **Rules** Tab and add the following code.

```javascript
service cloud.firestore {
 match /databases/{database}/documents {
    match /{document=**} {
   allow read, write;
      }
    }
}
```

Adding this code will allow users to read or write data to the Firestore database.

> _For demo purposes, I am allowing anyone to read or write data to the Firestore Database, but it’s not recommended. In a real-world scenario, you would have security rules targeting each collection or sub-collection to have different permissions based on your application behaviour._

Let’s run the collection group query one more time.

And, you will get another error on the browser/app debug console saying that the query requires a composite index.

This can be easily fixed by clicking the link provided by Firebase on the Debug console, which will then take you to the Firebase Dashboard Database Page.

Several minutes after, the composite index has been enabled.

Go back and try running the code one last time, and you will be able to see the results on the debug console.

Nice!

## Firestore Pagination Queries using Query Cursors

Imagine, you have a huge collection of documents about cities. It’s obvious to split them into batches (pagination) using query cursor methods so that users can have more control on the data consumption.

This will prevent users from getting overcharged for their data plans. As a developer, Firebase will bill you based on the number of document reads.

Let’ see how to paginate the cities collection, showing the first 10 items when the next button is pressed, then the next 10, and so on as shown below.

There are only four query cursor functions. These functions will work with `orderBy()` by passing the document field that you want to paginate based off of.

- **startAt():** You can pass any field value from documents which will be the starting point of your query including that field value.
- **startAfter()**: This is very similar to the startAt() with the only difference being the value that you passed inside startAfter() is excluded in the result dataset.
- **endAt():** You can pass any field value from documents which will be the ending point of your query including that field value.
- **endAfter()**: This is very similar to the endAt() and the only difference is the value that you passed inside endAfter() is excluded in the result dataset.

First, I am going to create three global variables.

```javascript
var cities = [];
const cityRef = firebase.firestore().collection("cities");
var lastVisibleCitySnapShot = {};
```

Then, declare and invoke a function called`getFirstTenCities()` which will get the first 10 cities from the Firestore Database.

```javascript
const query = await this.cityRef.orderBy("city").limit(10);
query.get().then((snap) => {
  snap.forEach((doc) => {
    this.cities.push(doc.data());
  });
  this.lastVisibleCitySnapShot = snap.docs[snap.docs.length - 1];
});
```

The initial query ordered by `city` field and `limit` to 10 items. Then, loop through the `snap` object that you receive from the call back function.

Append each city document to the `cities` global array that I declared earlier. After that, you can easily loop through the `cities` array in your HTML.

Finally, get the last document from the `snap` object using `snap.docs` array and assign it to `lastVisibleCitySnapShot` global variable.

I can get the next 10 items starting after the last city document stored in the `lastVisibleCitySnapShot.`

After that, add two simple next and previous buttons in your HTML and give a click event to them.

When a user clicks the next or next button, it invokes a function called `next()`.

```javascript
async next() {
  this.cities = [];

  const query = await this.cityRef
    .orderBy("city")
    .startAfter(this.lastVisibleCitySnapShot)
    .limit(10);

  query.get().then(snap => {
    snap.forEach(doc => {
      this.cities.push(doc.data());
    });
    this.lastVisibleCitySnapShot = snap.docs[snap.docs.length - 1];
  });
}
```

If you want to keep adding data to the cities array, keep scrolling down to see more data, you do not have reset it to an empty array [].

In my case, I want to reset it so that I can replace it with 10 new items. In the query, `startAfter()` method is used by passing the `lastVisibleCitySnapshot`. This will make sure to get only the next 10 items.

Similar to `next()` method, here is the `prev()` one.

```javascript
async prev() {
  this.cities = [];
  const query = await this.cityRef
    .orderBy("city")
    .endBefore(this.lastVisibleCitySnapShot)
    .limit(10);

  query.get().then(snap => {
    snap.forEach(doc => {
      this.cities.push(doc.data());
    });
    this.lastVisibleCitySnapShot = snap.docs[snap.docs.length - 1];
  });
},
```

There you go.

## Conclusion

You have learned how to do a simple CRUD operation type queries in Firestore. I have shown you how to filter data using WHERE, ORDERBY and LIMIT.

I have also taught you how to use Collection Group Queries and Pagination using Query Cursor Functions.

Now, I have a question for you…

What other queries would you like to know about which is not covered here?

Let me know in the comments section below so that I can add it here.
