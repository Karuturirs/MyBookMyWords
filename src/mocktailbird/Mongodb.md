# MongoDB Learning

* Step-1:
    Need to Install MongoDB manually or run the mongo docker container using

* Step-2:
    start mongodb
    `mongod`
* Step-3: connect to mongo terminal
     ```cmd
     mongo  --port 27017 -u "adam"
     -p "adamjohn"
     --authenticationDatabase "admin"
     ```
* Step-4: use db
     ```use mocktail```
* Step-5: Create user
   ```js
    use admin;
    db.getUsers();
    db.createUser(
      {
        user: "adam",
        pwd: "adamjohn",
        roles: [ { role: "readWrite", db: "mocktail" },
                 { role: "read", db: "reporting" } ]
      }
    );
    db.auth("adam","adamjohn");
    ```
* Step-5: Insert record
  ```
  db.mock.insert({"body":{"s":"ddd"}})
  ```

* Step-6: Set expaireAt index for mock collection.
  ```
   db.mock.createIndex( { "expireAt": 1 }, { expireAfterSeconds: 0 } )
  ```

* Step-7:Document formatting
   ```
      db.mock.insert(
      {"body":"dsaffsd",
      "status_code":"200 OK",
      "content_type":"application/json",
      "encoding":"UTF-8",
      "createdTime": new Date(),
      "modifiedTime":new Date(),
      "custom_headers":["key":"value"]
      })
      ```

* Model: To remove  expire data in 1min
  ```
  var now = new Date();
  var expi = new Date(now.getDate()+1*60000)
  db.mock.insert({
  "expireAt" : expi,
	"body" : "{\"dr\":\"dfdfdf\"}",
	"status_code" : "200 OK",
	"content_type" : "application/json",
	"encoding" : "UTF-8",
	"createdTime" : now,
	"modifiedTime" : now,
	"custom_headers" : {
		"key" : "value",
    "key2" : "value2",
	}
   })
   ```

* Data to expire after 5 day
   ```
   var now = new Date();
   var expi = now;
   expi.setDate(expi.getDate()+5);
   db.mock.insert({
  "expireAt" : expi,
	"body" : "{\"dr\":\"dfdfdf\"}",
	"status_code" : "200 OK",
	"content_type" : "application/json",
	"encoding" : "UTF-8",
	"createdTime" : now,
	"modifiedTime" : now,
	"custom_headers" : {
		"key" : "value",
    "key2" : "value2",
	}
   })
  ```
