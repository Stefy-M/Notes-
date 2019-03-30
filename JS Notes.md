## Variables 

- Can be assigned to functions


E.g:

```javascript
var name = function(){

	return ...

}
```



## Constructors 
----------------------
```javascript
function Person(firstName, lastName, age, eyeColor) {
  this.firstName = firstName; 
  this.lastName = lastName;
  this.age = age;
  this.eyeColor = eyeColor;
  this.changeName = function (name) {
    this.lastName = name;
  };
} 
```

## MongoDB w/ Nodejs

- Can insert an object straight into the db 
- Make sure to always check for err!

```javascript
var MongoClient = require('mongodb').MongoClient;
var url = "mongodb://localhost:27017/";

MongoClient.connect(url, function(err, db) {
  if (err) throw err;
  var dbo = db.db("mydb");
  var myobj = { name: "Company Inc", address: "Highway 37" };
  dbo.collection("customers").insertOne(myobj, function(err, res) {
    if (err) throw err;
    console.log("1 document inserted");
    db.close();
  });
});
```

## Functions

- Functions can be tested using function(err,res)
E.g

```javascript
player.find(p).toArray(function(err,res))

player.Add(newPlayer, function(err,res))
```


## Misc

- Can create a query that parses an object to find all of its keys 

```javascript
query = "SELECT * from speedgolfdb.courses WHERE ";
        for (const prop in testCourse) {
            query += prop + " = '" + testCourse[prop] + "' AND ";
        }
        query = query.substr(0,query.length-5);
```

- Route-Controller-Models Diagram

![Image of route-controller-model diagram](https://cdn-images-1.medium.com/max/1600/1*6naFm6YY5vYr1xxDz2qdzA.png)
