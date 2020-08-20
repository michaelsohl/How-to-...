# How to setup arangodb & how to use it

## Installation

### Homebrew
Latest arangodb from HomeBrew
```
brew install arangodb
```

Arangodb has a configuration file:
```
/usr/local/etc/arangodb3/arangod.conf
```

Open it to, for example change security level:
```
authentication = true
.
.
endpoint = tcp://127.0.0.1:8529
```

### Node
To run a server that uses arangodb we will install a node package:
```
npm install arangodb
```
The following code will start an existing database and make a query:
```javascript
var Database = require("arangojs").Database;
console.log(Database);
db = new Database("http://127.0.0.1:8529");
console.log(db);
var collection = db.collection("users");
collection.document("users/1027").then(doc) => {
  console.log("Name:", doc.name);
  console.log("Age:", JSON.stringify(doc.age, null, 2));
  },
  (err) => console.error("Failed to fetch document:", err)
);

collection.document("users/1293").then(
  (doc) => {
    console.log("Name:", doc.name);
    console.log("Age:", JSON.stringify(doc.age, null, 2));
  },
  (err) => console.error("Failed to fetch document:", err)
);
```

### Use arangodb admin page

Start arangodb in the terminal:
```
/usr/local/sbin/arangod &
```
Starts a webserver for admin control over arangodb on http//127.0.0.1:8529 (default)

Use query tab:
```
RETURN DOCUMENT("users/1027")
INSERT { name: "Sofie Svennberg", age: 28 } INTO users // Data modification query
RETURN DOCUMENT(["users/1027", "users/"])
```

Use https://www.arangodb.com/docs/ for fruther information


