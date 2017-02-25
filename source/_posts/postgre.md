---
title: postgre
date: 2017-02-21 11:18:37
tags:
---

```
db.many(query, values); // expects one or more rows
db.one(query, values); // expects a single row
db.none(query, values); // expects no rows
db.any(query, values); // expects anything, same as `manyOrNone`
db.oneOrNone(query, values); // expects 1 or 0 rows
db.manyOrNone(query, values); // expects anything, same as `any`
```

The library supports named parameters in query formatting, with the syntax of $*propName*, where * is any of the following open-close pairs: {}, (), <>, [], //


```
db.query('SELECT * FROM users WHERE name=${name} AND active=$/active/', {
    name: 'John',
    active: true
});
```

this 的用法：
```
var doc = {
    id: 123,
    body: "some text"
};

db.none("INSERT INTO documents(id, doc) VALUES(${id}, ${this})", doc)
    .then(function () {
        // success;
    })
    .catch(function (error) {
        // error;
    });
```

which will execute:

INSERT INTO documents(id, doc) VALUES(123, '{"id":123,"body":"some text"}')


执行函数

And when you are not expecting any return results, call db.proc instead. Both methods return a Promise object, but db.proc doesn't take a qrm parameter, always assuming it is one|none.
```
db.func('findAudit', [123, new Date()])
    .then(function (data) {
        console.log(data); // printing the data returned 
    })
    .catch(function (error) {
        console.log(error); // printing the error 
    });
db.proc();
```

公用一个连接：

```
db.task(function (t) {
    // `t` and `this` here are the same;
    // execute a chain of queries;
})
    .then(function (data) {
        // success;
    })
    .catch(function (error) {
        // failed;    
    });
```

事物：其中可以嵌套事物

```
db.tx(function (t) {
    // t = this;
    return t.batch([
        t.one("insert into users(name) values($1) returning id", "John"),
        t.one("insert into events(code) values($1) returning id", 123)
    ]);
})
    .spread(function (user, event) {
        // print new user id + new event id;
        console.log("DATA:", user.id, event.id);
    })
    .catch(function (error) {
        console.log("ERROR:", error); // print the error;
    })
    .finally(function () {
    

        pgp.end(); // for immediate app exit, closing the connection pool.   关闭连接池，是的一般不需要
        
        If, however you normally exit your application by killing the NodeJS process, then you don't need to use it.

        
    });
```

设置隔离级别：

```
var TransactionMode = pgp.txMode.TransactionMode;
var isolationLevel = pgp.txMode.isolationLevel;

// Create a reusable transaction mode (serializable + read-only + deferrable):
var tmSRD = new TransactionMode({
    tiLevel: isolationLevel.serializable,
    readOnly: true,
    deferrable: true
});

function myTransaction() {
    return this.query('SELECT * FROM table');
}

myTransaction.txMode = tmSRD; // assign transaction mode;

db.tx(myTransaction)
    .then(function(){
        // success;
    });
```
重置promise：

```
var promise = require('bluebird');
var options = {
    promiseLib: promise
};
var pgp = require('pg-promise')(options);
```

