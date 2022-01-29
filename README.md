# EwingDB

> a JSON database module

Examples

```js
const ewing = require("ewingdb")
const db = new ewing({
    "dbName": "test", // Our DB file name.
    "dbFolder": "database", // Our DB folder name.
    "noBlankData": true,
    "readable": true,
    "language": "en" // You can write "tr" or "en".
})

db.set("x.y.z", "abc") // abc

db.get("x") // {y: {z: "abc"}}
db.all() // {x: {y: {z: "abc"}}}

db.push("a", "hello") //  ["hello"]
db.push("a", "world") //  ["hello", "world"]
db.unpush("a", "hello") // ["world"]

db.push("b", {test: "ewingdb"}) // [{test: "ewingdb"}]
db.push("b", {test2: "ewingdb2"}) // [{test: "ewingdb"}, {test2: "ewingdb2"}]
db.delByPriority("b", 1) // [{test2: "ewingdb"}]
db.setByPriority("b", {newtest:"hey this is edited"} 1) // [{newtest:"hey this is edited"}]

db.delete("x") // true
db.deleteAll() // true
```

